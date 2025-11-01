### Code girls - AWS

---

## MÓDULO 4: Redes na AWS

### Amazon VPC (Virtual Private Cloud)

A Amazon VPC é fundamentalmente um espaço de rede isolado dentro da AWS onde você constrói sua infraestrutura. Pense nela como seu próprio datacenter virtual, mas com a flexibilidade da nuvem. Você controla completamente o ambiente de rede: escolhe os endereços IP, define como o tráfego flui, estabelece regras de segurança e decide o que se comunica com a Internet e o que permanece completamente privado.

### Componentes essenciais para entender

A estrutura de uma VPC se organiza em camadas. No nível mais básico, você define um **bloco CIDR** que estabelece todos os endereços IP disponíveis. Dentro desse espaço, você cria **sub-redes** que segmentam sua rede em zonas **públicas** (acessíveis da Internet) e **privadas** (isoladas). O tráfego é direcionado por **tabelas de roteamento**, enquanto a segurança opera em dois níveis:

* **Security Groups**: funcionam como firewalls para instâncias individuais.
* **Network ACLs**: controlam o tráfego no nível da sub-rede inteira.

Para conectividade, você usa **gateways**:

* **Internet Gateway**: permite comunicação com a Internet pública.
* **NAT Gateway**: possibilita que instâncias privadas acessem a Internet sem ficarem expostas diretamente.
* **VPC Peering**: conecta múltiplas VPCs diretamente.
* **Transit Gateway**: gerencia topologias mais complexas com várias redes interconectadas.

### Recursos que expandem as possibilidades

Dois recursos merecem atenção especial:

* **PrivateLink**: permite que serviços se comuniquem entre VPCs de forma privada, sem que o tráfego passe pela Internet pública.
* **Flow Logs**: capturam metadados sobre o tráfego de rede, criando um registro valioso para auditoria, troubleshooting e análise de segurança.

### Aplicações práticas

As VPCs brilham em cenários específicos:

* Hospedagem de aplicações web com bancos de dados protegidos: aplicação em sub-redes públicas, banco em sub-redes privadas.
* Arquiteturas híbridas: conecta servidores locais à nuvem via VPN ou Direct Connect, criando uma extensão do datacenter.
* Empresas com múltiplas contas AWS: mantém isolamento entre ambientes enquanto compartilha recursos de forma controlada.

### Considerações importantes

A flexibilidade da VPC vem acompanhada de complexidade. Você tem controle granular sobre cada aspecto da rede, permitindo atender requisitos rigorosos de segurança e conformidade. Porém, essa mesma flexibilidade exige **conhecimento sólido de conceitos de rede e planejamento cuidadoso**. Topologias grandes podem se tornar difíceis de gerenciar, e recursos como NAT Gateways e Transit Gateways adicionam custos que precisam ser considerados no orçamento.

### Por que isso importa

A VPC não é apenas mais um serviço da AWS – ela é a **fundação sobre a qual praticamente toda infraestrutura profissional na nuvem é construída**. Sem entender VPCs, não é possível implementar arquiteturas seguras, cumprir requisitos regulatórios ou criar ambientes verdadeiramente isolados. É o ponto de partida para qualquer solução séria na AWS.

**Referência:**  
- Amazon Virtual Private Cloud (VPC) - https://docs.aws.amazon.com/vpc/](https://docs.aws.amazon.com/vpc/

---
