### Code girls - AWS

---

# Entendendo o que é o Amazon RDS

Amazon RDS (Relational Database Service) é um serviço gerenciado de banco de dados relacional oferecido pela AWS.

## O que é e qual problema resolve
Imagine que você precise de um banco de dados para sua aplicação. Tradicionalmente, você teria que instalar o software do banco de dados em um servidor, configurar backups, aplicar patches de segurança, monitorar o desempenho e lidar com falhas de hardware.  
O RDS automatiza essas tarefas operacionais, permitindo que você foque na sua aplicação em vez de gerenciar infraestrutura.

## Motores de banco de dados suportados
O RDS não é um banco de dados próprio, mas sim uma plataforma que executa diferentes motores conhecidos.  
Ele suporta:
- MySQL
- PostgreSQL
- MariaDB
- Oracle
- Microsoft SQL Server
- Amazon Aurora (versão otimizada pela AWS compatível com MySQL e PostgreSQL)

Cada motor mantém suas características e compatibilidade com versões tradicionais.

## Principais benefícios
- **Automação:** backups diários, aplicação de patches de segurança e atualizações de software.
- **Janelas de manutenção configuráveis:** atividades programadas em horários de menor movimento.
- **Réplica de leitura:** distribuição de carga e aumento de performance.
- **Escalabilidade:** aumento de capacidade computacional ou de armazenamento com poucos cliques.
- **Alta disponibilidade:** configuração Multi-AZ, com réplica síncrona em outra zona de disponibilidade e failover automático.

## Como funciona na prática
Quando você cria uma instância RDS, está essencialmente provisionando um banco de dados completo e pronto para uso.  
Você recebe um endpoint (endereço) para conectar suas aplicações, como faria com qualquer banco de dados tradicional.  
Toda a infraestrutura subjacente é gerenciada pela AWS, incluindo:
- Sistema operacional
- Software do banco
- Camada de armazenamento

## Aspectos importantes a considerar
- **Dimensionamento da instância:** impacta diretamente custo e performance.
- **Single-AZ vs Multi-AZ:** depende das necessidades de disponibilidade.
- **Políticas de retenção de backups:** devem ser definidas e testadas para recuperação.

O RDS é particularmente valioso quando você quer os benefícios de um banco de dados relacional sem a sobrecarga operacional, tornando-o uma escolha popular tanto para startups quanto para grandes empresas.

## Conclusão
O Amazon RDS elimina a complexidade operacional de bancos de dados relacionais, automatizando backups, manutenção e alta disponibilidade.  
Isso permite que equipes foquem no desenvolvimento de aplicações em vez de gerenciar infraestrutura.

Suportando diversos motores de banco de dados com escalabilidade simples, o RDS democratiza recursos empresariais para organizações de qualquer tamanho, exemplificando como a nuvem reduz barreiras técnicas e acelera a inovação.

## Referências
- Amazon RDS - https://aws.amazon.com/rds/ - https://docs.aws.amazon.com/rds/
- Amazon RDS Features - https://aws.amazon.com/rds/features/](https://aws.amazon.com/rds/features/
- Amazon Aurora - https://aws.amazon.com/rds/aurora/](https://aws.amazon.com/rds/aurora/

---
