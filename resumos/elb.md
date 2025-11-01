### Code girls - AWS

---

## 6. Amazon Elastic Load Balancer (ELB)

O Amazon Elastic Load Balancer é um serviço gerenciado da AWS que distribui automaticamente o tráfego de entrada de aplicações entre múltiplos destinos, como instâncias EC2, contêineres, endereços IP e funções Lambda.

### Tipos de Load Balancers
A AWS oferece quatro tipos de ELB:

- **Application Load Balancer (ALB) - Camada 7 (HTTP/HTTPS)**
    - Ideal para aplicações web modernas
    - Suporta roteamento baseado em conteúdo (URL, host, headers)
    - Integração nativa com contêineres e microsserviços

- **Network Load Balancer (NLB) - Camada 4 (TCP/UDP/TLS)**
    - Projetado para alta performance e baixa latência
    - Capaz de lidar com milhões de requisições por segundo
    - Mantém endereços IP estáticos

- **Gateway Load Balancer (GWLB) - Camada 3**
    - Para implantação de appliances virtuais de terceiros
    - Útil para firewalls, sistemas de detecção de intrusão

- **Classic Load Balancer (CLB) - Legado**
    - Suporta camadas 4 e 7
    - Mantido para aplicações antigas na EC2-Classic

### Benefícios Principais
- **Alta disponibilidade:** Distribui tráfego entre múltiplas zonas de disponibilidade
- **Escalabilidade automática:** Ajusta capacidade conforme demanda
- **Segurança:** Integração com AWS Certificate Manager, Security Groups e WAF
- **Health checks:** Monitora constantemente a saúde dos destinos
- **Gerenciamento simplificado:** Totalmente gerenciado pela AWS

### Conclusão
O Amazon Elastic Load Balancer é um componente fundamental para construir aplicações robustas e escaláveis na AWS.  
Ao escolher o tipo adequado de load balancer para suas necessidades específicas, você garante não apenas a distribuição eficiente do tráfego, mas também melhora significativamente a disponibilidade, performance e segurança de suas aplicações na nuvem.  
Sua natureza totalmente gerenciada reduz a complexidade operacional, permitindo que as equipes foquem no desenvolvimento de suas aplicações ao invés de gerenciar infraestrutura.

---

### Referências 

- Amazon VPC / Subnet - https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html
- Amazon Security Group - https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html
- Amazon Route 53 https://docs.aws.amazon.com/Route53/
- Amazon CloudFront - https://docs.aws.amazon.com/AmazonCloudFront/
- Amazon Elastic Load Balancer (ELB) - https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html

---
