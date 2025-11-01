### Code girls - AWS

---

## 2. Amazon Subnet

A Amazon Subnet é um componente essencial do Amazon Virtual Private Cloud (VPC). Ela permite segmentar a rede virtual em partes menores, chamadas sub-redes, que organizam e controlam o tráfego entre recursos dentro da nuvem AWS. Cada sub-rede é associada a uma zona de disponibilidade (Availability Zone), garantindo isolamento e alta disponibilidade.

### Tópicos Principais

#### 1. Conceito e Função das Subnets
- **Sub-rede (Subnet):** uma faixa específica do bloco de endereços IP (CIDR) da VPC.
- Facilita a organização lógica da rede e o controle do tráfego interno e externo.
- Pode ser **pública** (com acesso à Internet) ou **privada** (restrita a redes internas).

#### 2. Tipos de Subnets

- **Sub-rede Pública:**
    - Associada a um Internet Gateway (IGW).
    - Permite que instâncias dentro dela tenham endereços IP públicos e acesso direto à Internet.

- **Sub-rede Privada:**
    - Não tem ligação direta com a Internet.
    - Pode usar um NAT Gateway ou NAT Instance para acessar serviços externos de forma segura.

- **Sub-rede Isolada:**
    - Não tem conexão com a Internet nem com outras redes.
    - Usada para segurança máxima (por exemplo, bancos de dados sensíveis).

#### 3. Configuração e Componentes Relacionados
- **CIDR Block:** define o intervalo de IPs da sub-rede.
- **Tabelas de Roteamento (Route Tables):** determinam o fluxo de tráfego entre sub-redes e com redes externas.
- **Security Groups e Network ACLs:** aplicam regras de segurança no nível de instância e sub-rede.
- **Availability Zone (AZ):** cada sub-rede pertence a uma única AZ, permitindo redundância ao distribuir recursos entre múltiplas zonas.

#### 4. Boas Práticas de Design
- Usar sub-redes separadas por função (web, aplicação, banco de dados).
- Criar sub-redes privadas para dados críticos e públicas apenas para componentes de front-end.
- Distribuir sub-redes entre várias zonas de disponibilidade para garantir tolerância a falhas.
- Controlar rotas e ACLs de forma centralizada para evitar conflitos de tráfego.

### Análise Crítica

**Pontos Fortes:**
- Alta flexibilidade e segurança.
- Suporte a arquitetura distribuída e redundante.
- Controle detalhado de tráfego entre camadas.

**Limitações:**
- Exige planejamento cuidadoso de endereçamento IP.
- Configurações incorretas podem causar perda de conectividade ou falhas de segurança.
- Complexidade aumenta com múltiplas zonas e contas AWS.

### Conclusões
As subnets são fundamentais para a segmentação, segurança e eficiência de uma VPC na AWS.  
Elas permitem estruturar ambientes de rede de forma modular, com controle granular sobre tráfego e acesso.  
O uso correto de sub-redes bem definidas é uma prática indispensável para qualquer arquitetura em nuvem segura e escalável.

### Referência
- Amazon VPC Subnets - https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html

---
