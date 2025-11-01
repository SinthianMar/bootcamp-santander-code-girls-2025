### Code girls -AWS

---

# MÓDULO 3: Criando Recursos na AWS


## 1. Criando sua Primeira Instância Amazon EC2

### AWS Organizations
**O que fiz:**  
Visualizei a estrutura de contas na AWS Organizations e identifiquei a hierarquia de unidades organizacionais (OUs) no módulo:  
- Ambiente Desenvolvimento  
- Ambiente Produção  
- Ambiente Teste  

**Motivo:**  
Organizei as contas conforme solicitado no bootcamp, seguindo a estrutura de unidades organizacionais (OUs) para cada ambiente, de forma a praticar a gestão centralizada de contas, permissões e políticas na AWS.

**Problema/Erro:**  
Nenhum problema encontrado até agora.

**Aprendizado:**  
- Compreendi o conceito de Root e Unidades Organizacionais (OUs).  
- Entendi que cada OU pode representar um ambiente distinto (Desenvolvimento, Teste, Produção).  
- Percebi a importância de separar ambientes para garantir isolamento e segurança.  
- Aprendi que a AWS Organizations ajuda a gerenciar políticas e acessos de forma centralizada.  

---

### Criando minha 1ª Instância EC2
**O que fiz:**  
Criei uma instância EC2 Linux usando a AMI `al2023-ami-2023.9`, tipo `t2.nano`, configurada na VPC e sub-rede padrão.  
A instância está executando e recebeu:  
- **IP público:** 54.226.226.206  
- **IP privado:** 172.31.27.151  

**Motivo:**  
Escolhi o tipo `t2.nano` por ser econômico e suficiente para testes no bootcamp.  
Usei Linux/UNIX para praticar comandos básicos de servidor na nuvem.

**Problema/Erro:**  
Nenhum problema encontrado até agora.

**Aprendizado:**  
- Entendi a diferença entre IP público e IP privado.  
- Aprendi sobre AMIs e como elas definem o sistema operacional da instância.  
- Compreendi o papel da VPC e sub-rede na organização da rede AWS.  
- Reconheci a importância do tipo da instância para equilibrar custo e desempenho.  
- Observei a configuração de IMDSv2 e como ela aumenta a segurança.  

---

## Configurando o Acesso Local com MobaXterm

**Serviço:** EC2 – Instância Servidor01  
**ID da instância:** i-0536517ef4c6e7e3b  
**Tipo:** t2.micro  
**Sistema operacional:** Linux/UNIX (AMI `al2023-ami-2023.9.20251020.0-kernel-6.1-x86_64`)  
**Par de chaves:** ChavesLinux  

**O que fiz:**  
Criei a instância EC2 Servidor01 e configurei o acesso local com o MobaXterm.  
Identifiquei os endereços IP:  
- **IPv4 público:** 98.81.191.128  
- **IPv4 privado:** 172.31.29.114  

Verifiquei detalhes da instância, segurança, tags, armazenamento, monitoramento, status e opções de recuperação automática.

**Motivo:**  
Utilizei o tipo `t2.micro` por estar dentro do *free tier*.  
Mantive o monitoramento e as configurações padrão para testes iniciais.

**Problema/Erro:**  
Tive dificuldade para configurar o MobaXterm e compreender o processo completo de conexão.  
Assisti vídeos complementares para entender como vincular a chave `.pem` e definir o usuário correto para autenticação SSH.

**Resultado:**  
Após ajustar as configurações e refazer o passo a passo, consegui estabelecer a conexão com sucesso.  
O terminal confirmou a autenticação via chave pública, e a instância respondeu normalmente.  
Executei o comando `sudo yum update -y` para testar a comunicação, e o sistema retornou que estava totalmente atualizado.

**Observações adicionais:**  
- Endereço IPv4 público e DNS público estão acessíveis.  
- Monitoramento desativado e proteção contra encerramento desabilitada.  
- Configuração padrão de reinicialização e recuperação automática.  
- Instância usa virtualização HVM, modo de inicialização *legacy-bios*.  
- 1 vCPU e padrão de crédito *standard*.

**Dica pessoal:**  
Pretendo revisar novamente a aula sobre a instância `i-0536517ef4c6e7e3b` para reforçar a prática com o MobaXterm e consolidar o aprendizado.

---

## Configurando e Testando a Segunda Instância

**Serviço:** EC2 – Instância Servidor02  
**ID da instância:** i-0c559956ef671d16f  
**Tipo:** t2.nano  
**Sistema operacional:** Linux/UNIX  
**Par de chaves:** (mesmo usado na primeira instância)  

**O que fiz:**  
Criei a instância EC2 Servidor02 e conectei para verificação de configuração.  
Identifiquei os endereços IP:  
- **IPv4 público:** 107.23.174.233  
- **IPv4 privado:** 172.31.18.153  

Verifiquei detalhes da instância, segurança, tags, armazenamento, monitoramento, status e redes.  
Segui instruções do professor e interrompi a instância para não gerar cobrança.

**Motivo:**  
Praticar a criação e configuração de uma instância EC2 e reforçar o aprendizado da primeira instância.  
Tipo `t2.nano` usado por ser uma opção pequena e suficiente para testes.

**Problema/Erro:**  
Nenhum problema técnico, apenas a interrupção conforme orientação do professor.

**Resultado:**  
Instância criada corretamente, endereços IP atribuídos e detalhes verificados.  
Seguindo a instrução, a instância foi interrompida sem gerar custos.

**Observações adicionais:**  
- Endereço IPv4 público e DNS público acessíveis.  
- Instância interrompida para evitar cobranças.  
- Configuração padrão de virtualização HVM, 1 vCPU, sem endereços IP elásticos.

**Dica pessoal:**  
Pretendo revisar a prática com múltiplas instâncias EC2 e reforçar conceitos de rede, DNS e monitoramento.

---

## Comparando Servidores Linux e Windows na AWS

**Serviço:** EC2 – Instâncias Linux e Windows  
**Recursos:** Segurança, Acesso e Comunicação via SSH e RDP  

**O que fiz:**  
Analisei as diferenças entre servidores Linux e Windows dentro da AWS EC2.  
Observei como cada sistema utiliza métodos distintos de conexão e portas:  
- **Linux:** conexão via SSH (porta 22) utilizando chave privada (.pem).  
- **Windows:** conexão via RDP (porta 3389) também autenticada com chave privada.  

Entendi a função dos *Security Groups* na liberação de portas específicas para acesso remoto.  
Estudei o uso das chaves pública e privada para autenticação segura entre cliente e servidor.

**Motivo:**  
Compreender as diferenças práticas entre servidores EC2 com Linux e Windows.  
Aprender como cada um se conecta, suas portas padrão e a importância da segurança nas configurações de rede.

**Problema/Erro:**  
Nenhum problema técnico, apenas dúvidas iniciais sobre a função exata de cada porta e o fluxo de autenticação, sanadas durante a explicação.

**Resultado:**  
Entendimento claro sobre como ocorre o acesso remoto a instâncias Linux e Windows.  
Consolidação do conceito de chave pública e privada e controle de portas via *Security Group*.

**Observações adicionais:**  
- O Linux utiliza SSH e comandos via terminal.  
- O Windows usa RDP e acesso gráfico remoto.  
- Ambos exigem configuração adequada de segurança para evitar acessos indevidos.

**Dica pessoal:**  
Pretendo revisar os protocolos SSH e RDP, reforçando o entendimento sobre autenticação e portas padrão antes de iniciar a próxima prática.

---

## AWS EC2 (Servidor Windows)

**Serviço:** EC2 – Instância Servidor03  
**ID da instância:** i-0d1a135f91b4a2358  
**Tipo:** t2.micro  
**Sistema Operacional:** Microsoft Windows Server 2022 Datacenter (AMI: `ami-043cc489b5239c3de`)  
**Data de criação:** 25/10/2025  

**O que foi feito:**  
Criei um grupo de segurança chamado **Conexao-ServidorWindows** (ID: `sg-0d34271411bbc3daa`), configurado para permitir conexões RDP (porta 3389) a partir do IP `177.125.186.0/32`.  
Em seguida, utilizei essa configuração para iniciar uma instância Windows na VPC `vpc-096e87ac133287313`, com armazenamento de 30 GiB e par de chaves **ChaveWindows** para acesso remoto.

**Motivo:**  
O objetivo foi praticar o processo completo de criação de uma instância Windows na AWS, desde a configuração do grupo de segurança até o provisionamento da instância, entendendo melhor como o EC2 gerencia permissões, acesso e infraestrutura virtualizada.

**Resultado:**  
A instância foi criada com sucesso e está em execução, com:  
- **IPv4 público:** 3.91.17.243  
- **DNS público:** `ec2-3-91-17-243.compute-1.amazonaws.com`  
Permitindo conexão via RDP.

**Observações:**  
O grupo de segurança foi corretamente vinculado à instância.  
O monitoramento está desativado, mas a instância encontra-se ativa e funcional.  
Ainda preciso revisar o procedimento de conexão via RDP para garantir acesso e configurar as credenciais com a chave gerada.


---

### Conclusão  

Neste módulo, foi possível compreender de forma prática como criar, configurar e gerenciar instâncias EC2 na AWS, tanto em sistemas Linux quanto Windows.  
A atividade reforçou conceitos fundamentais de redes, segurança e autenticação, além de consolidar o uso de ferramentas como o MobaXterm para conexões seguras.  
A experiência demonstrou a importância do isolamento de ambientes e da configuração correta de *Security Groups*, consolidando os primeiros passos na administração de recursos em nuvem.  

---

### Referências  

- AWS EC2 Documentation - https://docs.aws.amazon.com/ec2/
- AWS Organizations Documentation - https://docs.aws.amazon.com/organizations/
- AWS Cloud Practitioner Essentials - https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/
- Amazon VPC Documentation - https://docs.aws.amazon.com/vpc/
- AWS Security Groups - https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html
- AWS Free Tier – EC2 - https://aws.amazon.com/free/ec2/

---