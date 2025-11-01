### Code girls -AWS

---

## 2. Criando seu Primeiro Bucket no Amazon S3

### Integração com Lambda e S3

Hoje explorei na prática o uso do **Amazon S3** integrado à **AWS Lambda** para criar um fluxo automatizado de processamento de arquivos.  
O processo começa com a exportação de um arquivo posicional do banco de dados, que é enviado ao **S3**. Assim que o arquivo chega, uma **função Lambda** é acionada para processá-lo e movê-lo automaticamente para outra pasta dentro do mesmo bucket.

Essa arquitetura mostra como é possível construir uma automação **serverless** eficiente, segura e escalável. ⚙️

---

### Aula Handson S3

Na aula prática (*Handson S3*), criei o bucket `aulahandson` e explorei as seções de **Objetos**, **Metadados**, **Propriedades** e **Permissões**.  
Aprendi que, para permitir o acesso de outros usuários, é preciso definir **permissões explícitas** — o que reforça a importância do controle de acesso.  
Também configurei as pastas `Entrada/` e `Processado/` com sucesso. 📁

---

### Hospedagem de Website no S3

Por fim, realizei a **hospedagem de um site estático no S3**.  
Clonei o repositório do professor, editei o arquivo `index.html` com minhas informações e criei o bucket `desafioawsdiome` com **política de acesso público**.

Configurei ainda um **Access Point** chamado `acess-webs3` para gerenciar acessos de forma personalizada.  
Depois de enviar as pastas do projeto para o S3, meu site ficou **online** e acessível pela web — pronto para as próximas etapas do desenvolvimento. 🌐

---

### Conclusão

O estudo prático com o **Amazon S3** e a **AWS Lambda** proporcionou uma compreensão sólida sobre como implementar soluções **serverless** e **automatizadas** na nuvem.  
Foi possível perceber na prática como o **S3** facilita o **armazenamento**, o **versionamento** e o **controle de acesso** a dados, enquanto a **Lambda** complementa esse processo com **execução automatizada** e **escalável**.

Além disso, a experiência de **hospedar um site estático** reforçou a versatilidade do S3, permitindo unir conceitos de **armazenamento**, **segurança** e **distribuição de conteúdo** em um único ambiente.  
Essas práticas são fundamentais para o desenvolvimento de **aplicações modernas, seguras e de baixo custo** na nuvem. ☁️

---

### Referências

- Documentação do Amazon - https://docs.aws.amazon.com/pt_br/s3
- Documentação da AWS Lambda - https://docs.aws.amazon.com/pt_br/lambda 

---