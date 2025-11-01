### Code girls - AWS

---

## 3. Amazon Security Group

O Amazon Security Group (SG) é um firewall virtual usado para controlar o tráfego de rede de entrada e saída em instâncias dentro da Amazon Virtual Private Cloud (VPC). Ele é um dos principais mecanismos de segurança da Amazon Web Services (AWS), garantindo isolamento e controle preciso sobre as comunicações de rede entre recursos na nuvem.

### Conceito e Funcionamento
O Security Group atua em nível de instância, definindo regras que determinam quais conexões são permitidas. Por padrão, todo o tráfego é bloqueado até que regras específicas sejam criadas.  
As regras são **stateful**, ou seja, se o tráfego de entrada é permitido, o de saída correspondente é automaticamente autorizado, e vice-versa. Isso simplifica a configuração e reduz a chance de falhas de segurança.

### Regras e Configuração
Existem dois tipos principais de regras:

- **Regras de Entrada (Inbound):** controlam o tráfego que chega à instância.
- **Regras de Saída (Outbound):** controlam o tráfego que sai da instância.

Essas regras especificam protocolos (como TCP ou UDP), portas (por exemplo, 22 para SSH ou 443 para HTTPS) e endereços de origem ou destino (como blocos CIDR ou outros Security Groups).  
As alterações feitas são aplicadas imediatamente, sem necessidade de reinicializar os recursos.

### Boas Práticas
- Aplicar o **princípio do menor privilégio**, permitindo apenas o tráfego estritamente necessário.
- Separar os Security Groups por função, criando grupos distintos para camadas web, aplicação e banco de dados.
- Evitar o uso de endereços públicos abertos (como 0.0.0.0/0).
- Realizar auditorias periódicas para garantir conformidade e segurança.

### Conclusão
Os Amazon Security Groups constituem a primeira camada de defesa das aplicações em nuvem na AWS.  
Seu uso correto assegura proteção lógica, flexibilidade e controle granular do tráfego de rede.  
Apesar de sua simplicidade operacional, exigem atenção e planejamento estratégico para garantir ambientes escaláveis e seguros.

### Referência
- Amazon EC2 Security Groups - https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html

---