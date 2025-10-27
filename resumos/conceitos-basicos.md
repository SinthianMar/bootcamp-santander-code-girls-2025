### Code girls - AWS

---

# MÓDULO 1: Introdução à AWS e Conceitos Básicos

---

## 1. Introdução à AWS e ao Universo da Computação em Nuvem

A computação em nuvem revolucionou a forma como as empresas usam tecnologia. Em vez
de comprar computadores caros e guardar em data centers próprios, você aluga recursos da
internet quando precisa. A AWS é a maior provedora de computação em nuvem do mundo.

---

### Sumário

- A História da Amazon
- A Criação da AWS
- Serviço em Nuvem
- Questões
- Conclusão
- Referências

---

## História da Amazon

A Amazon foi fundada pelo Jeff Bezos, estava na moda a criação de sites pela internet e então ele teve uma grande ideia, uma <ins>livraria online!</ins>
Logo, iniciou o projeto de livraria online em 1994. O escritório era em sua garagem, localizada em Seattle, Washington. O site foi lançado oficialmente em 1995!

<p align="center">
  <img src="../imagens/amazon.png" width="540" height="360" alt="Amazon">
</p>

<p align="center">
    A loja de tudo: Jeff Bezos e a era da Amazon
</p>

### 🔹 Curiosidades!

> - O nome inicial da Amazon foi Cadabra. Fazendo uma associação com abracadabra por ter uma magia nos livros!
> - O nome da Amazon foi inspirado no Rio Amazonas, sim esse mesmo. Um dos maiores rios do mundo em extensão e cuja grande parte fica localizada no Brasil! No início, esse nome não pegou muito, os gringos não conheciam muito sobre a nossa cultura, mas o Jeff usou o marketing "Esse rio supera todos os outros de longe" dando a entender que ele superaria tudo e todos!

---

## História da AWS

A Amazon começou desenvolvendo soluções de tecnologia para gerenciar seus próprios recursos de computação durante os anos 2000. Percebendo que essas ferramentas internas poderiam ser úteis para outras empresas, a companhia decidiu transformar essa expertise em um serviço comercial. Em 2006, lançou oficialmente a AWS com serviços como o S3 para armazenamento de dados e o EC2 para processamento, criando assim uma plataforma completa de computação em nuvem. O grande diferencial foi o modelo de pagamento por uso, onde os clientes só desembolsam pelo que realmente consomem, o que representou uma inovação importante no mercado da época.

---

### Os 3 Modelos de Serviço em Nuvem

Existem 3 formas diferentes de usar nuvem. Cada uma tem um nível de responsabilidade
diferente:

<p align="center">
    <img src="../imagens/servicos-em-nuvem.png" width="590" height="408" alt="servicos-em-nuvem">
</p>

#### **IaaS - Infrastructure as a Service (Infraestrutura como Serviço)**

Você aluga os computadores. Você cuida do resto.

- O que a AWS cuida: Máquinas físicas, energia, rede básica
- O que **você** cuida: Sistema operacional, aplicativos, dados, segurança de aplicação

**Exemplo real:** Instâncias EC2 (um computador virtual que você aluga)
**Analogia:** É como alugar um terreno vazio. Você constrói o que quer em cima dele.

---

#### **PaaS - Platform as a Service (Plataforma como Serviço)**

Você coloca seu código. A AWS cuida de quase tudo.

- O que a AWS cuida: Infraestrutura + Sistema Operacional + Banco de Dados
- O que **você** cuida: Seu código/aplicação

**Exemplo real:** SQL Server pronto para usar na AWS.
**Analogia:** É como alugar um apartamento mobiliado. Você só traz suas coisas e mora.

---

#### **SaaS - Software as a Service (Software como Serviço)**

Pronto para usar. Sem instalar nada.

- O que a AWS cuida: Absolutely everything!
- O que **você** cuida: Nada! Só usar e pagar

**Exemplos:** Gmail, Netflix, Spotify, sistemas de CRM
**Analogia:** É como ir para um hotel. Tudo está pronto, você só aproveita.

---

### A Analogia do Churrasco

Imagine que você quer fazer um churrasco

<p align="center">
    <img src="../imagens/churras.png" width="690" height="508" alt="servicos-em-nuvem">
</p>


|              Modelo              |                                 Responsabilidade                                 |
| :-------------------------------: | :-------------------------------------------------------------------------------: |
| **On Premise (servidor em casa)** | Você cuida de tudo: compra o terreno, a churrasqueira, a carne, prepara e limpa |
|             **IaaS**             |     A AWS oferece o terreno e a churrasqueira. Você compra a carne e prepara     |
|             **PaaS**             | A AWS oferece terreno, churrasqueira**e** a carne já comprada. Você só prepara |
|             **SaaS**             |            A AWS oferece o churrasco**pronto**. Você só come e paga            |

---

### Por que a AWS é a Preferida?

A AWS não apenas oferece infraestrutura, ela inova constantemente.

> Comentário do professor: “Todas as clouds estão atentas ao mercado, mas a AWS sempre está um passo à frente.”

**3 Formas de Crescer com AWS:**

1. Aumentar recursos: sua empresa cresceu? Expanda seus servidores na nuvem
2. Migrar aplicativos: traga sistemas antigos para a nuvem
3. Criar novos negócios: desenvolva aplicativos inovadores direto na AWS

**Meu comentário:**
Apesar de haver outras clouds (Google Cloud, Azure), a AWS é preferida porque tem sempre soluções novas conforme o mercado evolui.

---

### Questões

1. Qual foi a ideia inicial de Jeff Bezos?

   - [ ]  Criar uma empresa de tecnologia
   - [X]  Uma livraria online
   - [ ]  Vender computadores
   - [ ]  Fornecer serviços de nuvem
2. Em que ano a AWS foi criada?

   - [ ]  1994
   - [ ]  1995
   - [X]  2006
   - [ ]  2010
3. Qual é a principal vantagem do modelo de pagamento da AWS?

   - [ ]  Você paga um valor fixo todo mês
   - [X]  Você paga só pelo que usa
   - [ ]  Você não paga nada
   - [ ]  Você paga antecipado por 10 anos
4. Na analogia do churrasco, o modelo SaaS é:

   - [ ]  Você compra tudo e prepara
   - [ ]  Você compra a carne e prepara
   - [X]  O churrasco já vem pronto, você só come
   - [ ]  Você aluga a churrasqueira
5. Qual é o diferencial da AWS em relação a outras clouds?

   - [ ]  É a mais barata
   - [ ]  Tem os piores serviços
   - [X]  Inova constantemente conforme evolução do mercado
   - [ ]  Funciona só nos EUA

---

### Conclusão

A AWS começou como uma solução interna da Amazon e se transformou na maior provedora
de nuvem do mundo. Entender sua história ajuda a entender por que ela é tão poderosa.

---

### Referências

- [Site AWS](https://aws.amazon.com/pt/)
- [Blog oficial](https://aws.amazon.com/pt/blogs/)

Documento: [introducao-a-aws-e-conceitos-basicos.pdf](../materiais-de-apoio/introducao-a-aws-e-conceitos-basicos.pdf)
