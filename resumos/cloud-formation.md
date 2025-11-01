### Code girls -AWS

---

## Implementando sua Primeira Stack com AWS CloudFormation

A aula abordou o AWS CloudFormation, ferramenta nativa da AWS voltada à automação da criação e gerenciamento de recursos em nuvem. O instrutor apresentou o conceito de Infraestrutura como Código (IaC), destacando como o CloudFormation permite construir e versionar infraestruturas complexas por meio de templates JSON ou YAML.

Durante a prática, explorei o funcionamento do serviço e criei minha própria automação, aplicando os conceitos vistos na aula anterior sobre CloudWatch e CloudTrail.

### O que é CloudFormation?

O AWS CloudFormation permite que desenvolvedores e administradores definam, provisionem e gerenciem recursos AWS de forma automatizada, sem depender exclusivamente do console gráfico.

**Principais pontos da aula:**

- **Templates JSON/YAML:** arquivos de definição que descrevem todos os recursos (EC2, S3, IAM, VPC etc.) e suas propriedades.
- **Stacks:** cada execução de template cria uma stack, um conjunto de recursos gerenciado como uma única unidade.
- **Automação e versionamento:** o mesmo template pode ser reutilizado, ajustado e compartilhado entre equipes.
- **Integração com outras ferramentas:** a AWS suporta também uso de Terraform, Ansible e PowerShell, mas o CloudFormation é a solução oficial.

**Na prática, criei automações reais:**

- Um template para instâncias EC2 (máquina virtual Linux).
- Um template para servidor Apache acessível via HTTP.
- Um template de Firewall, com regras de segurança liberando apenas a porta 80.
- E por fim, um template mais robusto, que cria um EC2, um bucket S3 e um usuário IAM, todos automaticamente.

O processo de automação foi fluido e empolgante, e consegui ver claramente os recursos sendo criados na minha conta AWS.

![cloudformation.png](../imagens/cloudformation.png)

---

### Erros e Soluções

Este documento descreve os erros encontrados durante a criação de uma stack CloudFormation na AWS e as soluções aplicadas para corrigi-los. O template final tinha como objetivo criar uma instância EC2, bucket S3, usuário IAM e grupo IAM de forma automatizada.

---

### Erro 1: Bucket S3 Com Letras Maiúsculas

### Mensagem de Erro

```
The resource S3Bucket is in a CREATE_FAILED state
This AWS::S3::Bucket resource is in a CREATE_FAILED state.
Resource handler returned message: "Bucket name should not contain uppercase characters"
(RequestToken: 75422385-78dd-6ad3-3836-ecb060a5d3ee, HandlerErrorCode: GeneralServiceException)
```

### Causa

Os nomes de buckets S3 não podem conter letras maiúsculas. A AWS exige que todos os nomes de buckets sejam escritos em letras minúsculas, seguindo as convenções de nomenclatura do DNS.

### Solução Aplicada

Alterei o BucketName para utilizar apenas letras minúsculas.

```yaml
# Antes:
BucketName: S3-Foundation-AWS

# Depois:
BucketName: s3-foundation-aws
```
![erros.png](../imagens/erros.png)
---

### Erro 2: Nome Do Bucket S3 Indisponível

### Mensagem de Erro

```
The requested bucket name is not available. The bucket namespace is shared by all users of the system.
```

### Causa

O nome do bucket `s3-foundation-aws` já estava sendo utilizado por outra conta AWS. Os nomes de buckets S3 precisam ser únicos globalmente em toda a plataforma AWS, não apenas dentro da conta.

### Código Original

```yaml
S3Bucket:
  Type: 'AWS::S3::Bucket'
  Properties:
    BucketName: s3-foundation-aws
```

### Solução Aplicada

```yaml
S3Bucket:
  Type: 'AWS::S3::Bucket'
  Properties:
    BucketName: !Sub 's3-foundation-aws-${AWS::AccountId}-${AWS::Region}'
```

### Resultado

Adicionei variáveis dinâmicas ao nome do bucket utilizando a função `!Sub`:

- **AWS::AccountId:** ID único da conta AWS (12 dígitos)
- **AWS::Region:** Região onde o bucket está sendo criado

Exemplo de nome gerado: `s3-foundation-aws-123456789012-us-east-1`

---

### Erro 3: Ami Desatualizada

### Mensagem de Erro

```
The image id '[ami-0c55b159cbfafe1f0]' does not exist
```

### Causa

As Amazon Machine Images (AMIs) são atualizadas regularmente. A AMI especificada no template original estava desatualizada ou não estava disponível na região us-east-1.

### Código Original

```yaml
Mappings:
  UbuntuMap:
    us-east-1:
      UbuntuAMI: ami-0c55b159cbfafe1f0
```

### Solução Aplicada

```yaml
Mappings:
  UbuntuMap:
    us-east-1:
      UbuntuAMI: ami-0866a3c8686eaeeba
```

### Resultado

Consultei o console da AWS EC2 para identificar a AMI mais recente do Ubuntu disponível para a região us-east-1 e atualizei o Mapping no template.

---

### Erro 4: Usuário Iam Já Existe

### Mensagem de Erro

```
Resource handler returned message: "Resource of type 'AWS::IAM::User' with identifier 'ADM' already exists."
```

### Causa

O usuário IAM com o nome "ADM" já existia na conta AWS. O CloudFormation não permite criar recursos com nomes duplicados e retorna erro quando tenta criar um recurso que já existe.

### Código Original

```yaml
IAMUser:
  Type: 'AWS::IAM::User'
  Properties:
    UserName: ADM
    Groups:
      - !Ref IAMGroup
```

### Solução Aplicada

```yaml
Parameters:
  IAMUserName:
    Type: String
    Default: ADM-Lab
    Description: Nome do usuario IAM

Resources:
  IAMUser:
    Type: 'AWS::IAM::User'
    Properties:
      UserName: !Ref IAMUserName
      Groups:
        - !Ref IAMGroup
  
  IAMGroup:
    Type: 'AWS::IAM::Group'
    Properties:
      GroupName: !Sub 'GPO-ADMIN-LAB-${AWS::StackName}'
```

### Resultado

- Alterei o nome do usuário IAM de "ADM" para "ADM-Lab"
- Criei um parâmetro configurável para o nome do usuário
- Adicionei o nome da stack ao grupo IAM para evitar conflitos futuros
- Isso permite criar múltiplas stacks sem conflitos de nomenclatura

---

### Lições Aprendidas

#### 1. Convenções de Nomenclatura S3

Nomes de buckets S3 devem seguir regras específicas:

- Apenas letras minúsculas, números e hífens
- Não pode começar ou terminar com hífen
- Deve ter entre 3 e 63 caracteres

#### 2. Nomes de Buckets S3

Sempre utilizar sufixos dinâmicos (AccountId, Region, timestamps) para garantir unicidade global dos nomes de buckets.

#### 3. AMIs

Sempre verificar as AMIs mais recentes diretamente no console AWS para a região específica antes de criar ou atualizar templates CloudFormation.

#### 4. Recursos IAM

Nomes de usuários e grupos IAM precisam ser únicos dentro da conta AWS. Utilizar parametrização ou adicionar sufixos únicos ajuda a evitar conflitos.

#### 5. Gerenciamento de Stacks

Sempre deletar completamente uma stack com falha antes de tentar recriar com as correções aplicadas.

#### 6. Indentação e Sintaxe

A configuração YAML/JSON exige atenção especial com indentação e parâmetros, pois erros de sintaxe podem impedir a criação da stack.

---

### Análise Da Experiência

A experiência de criar automações com o CloudFormation foi muito positiva e enriquecedora. A ferramenta se mostrou poderosa, flexível e intuitiva para quem busca eficiência e padronização em ambientes em nuvem.

#### Pontos Positivos

- Facilidade na criação de infraestrutura completa a partir de código
- Reutilização de templates e possibilidade de versionamento colaborativo
- Integração com IDEs como o VS Code, otimizando o fluxo de trabalho
- Automação completa de recursos complexos

#### Desafios Encontrados

- Exige atenção com indentação e parâmetros YAML/JSON, o que pode gerar erros de sintaxe
- A configuração de rede (VPC, subnets e segurança) ainda é considerada complexa e demanda prática
- Necessidade de conhecer convenções específicas de cada serviço AWS

De modo geral, gostei muito da atividade e do resultado alcançado com as automações criadas.

---

### Conclusão

O AWS CloudFormation representa um avanço essencial na governança e automação de ambientes AWS. Através dele, é possível transformar o processo manual de criação de recursos em um sistema inteligente, padronizado e reproduzível.

Após aplicar todas as correções descritas neste documento, o template CloudFormation foi executado com sucesso, criando todos os recursos necessários: bucket S3 com nome único, instância EC2 com AMI atualizada, usuário IAM e grupo IAM sem conflitos de nomenclatura.

A experiência prática de construir templates e ver as instâncias e serviços surgirem automaticamente reforçou o aprendizado e despertou grande interesse pessoal na automação de infraestrutura.

Os aprendizados obtidos servirão como base para evitar erros semelhantes em projetos futuros. Posso afirmar que criei a automação com sucesso e gostei muito da ferramenta, reconhecendo seu valor para o trabalho em nuvem moderna.

---

### Referências

AWS CloudFormation Documentation — https://docs.aws.amazon.com/cloudformation/  
AWS Well-Architected Framework — https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html  
AWS Identity and Access Management (IAM) Documentation — https://docs.aws.amazon.com/iam/  
Amazon S3 Documentation — https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html  
Amazon EC2 Documentation — https://docs.aws.amazon.com/ec2/  
 
---