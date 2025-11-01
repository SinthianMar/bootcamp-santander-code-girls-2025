### Code girls - AWS

---

# Introdução ao Amazon DynamoDB

O Amazon DynamoDB é um banco de dados NoSQL distribuído, serverless e totalmente gerenciado pela AWS, projetado para oferecer desempenho em milissegundos de um dígito em qualquer escala.  
Ele funciona como um banco de dados chave-valor rápido, ideal para aplicações de alto desempenho que lidam com grandes volumes de dados e tráfego.

## Principais Recursos
- **Gerenciamento Zero de Infraestrutura:**  
  Elimina a necessidade de gerenciar servidores, incluindo manutenção sem downtime, sem upgrades de versão ou janelas de manutenção. Cuida de backups, segurança, conformidade e monitoramento automaticamente.

- **Escalabilidade Instantânea e Desempenho:**  
  Suporta escalabilidade imediata para atender demandas de aplicações, com até mais de 500 mil solicitações por segundo e tamanhos de tabelas superiores a 200 TB. Oferece latência de milissegundos e throughput praticamente ilimitado.

- **Tabelas Globais:**  
  Banco de dados multi-região e multi-ativo com disponibilidade de até 99,999%, permitindo consistência forte entre regiões. Facilita aplicações com leitura e escrita de qualquer região, mantendo dados sempre atualizados, ideal para cenários com objetivo de recuperação zero (RPO zero).

- **Segurança e Conformidade:**  
  Inclui controles de segurança amplos e conformidade com padrões como SOC 1/2/3, PCI, FINMA e ISO, atendendo a requisitos de governos, bancos globais e organizações sensíveis.

- **Modelo de Cobrança:**  
  Cobrança por solicitação para eficiência de custos, relatada como 25% mais barata em comparação a ambientes equivalentes.

## Benefícios
O DynamoDB remove a sobrecarga operacional, permitindo que as equipes foquem em inovação em vez de gerenciamento de banco de dados.  
Ele garante alta disponibilidade, resiliência e desempenho para aplicações distribuídas globalmente, suportando eventos de escala extrema e mantendo fidelidade de dados.  
Com mais de 1 milhão de clientes, é amplamente adotado para aplicações de internet-scale com milhões de usuários e solicitações por segundo.

## Casos de Uso
- **Aplicações de Escala Internet:** Metadados de conteúdo de usuário e caches que exigem alta concorrência para milhões de usuários.
- **Mídia e Entretenimento:** Streaming de vídeo em tempo real, conteúdo interativo e criação de humanos digitais para transmissões ao vivo.
- **Varejo e Atacado:** Carrinhos de compras, engines de workflow, rastreamento de estoque e perfis de clientes, lidando com picos de tráfego.
- **Jogos:** Plataformas com dados de jogadores, histórico de sessões e leaderboards para milhões de usuários simultâneos.
- **Serviços Financeiros e Processamento de Pagamentos:** Detecção de fraudes, fluxos de mensagens, onboarding digital e aplicações sempre disponíveis com RPO zero.
- **Publicidade e Marketing:** Armazenamento de perfis de usuários, eventos e cliques para lances em tempo real, segmentação de anúncios e monetização de ativos de publicação.

## Conclusão
DynamoDB é uma potência para apps de alta escala, como e-commerce ou IoT, com throughput provisionado que roda milhões de requests por segundo sem dor de cabeça.  
Mas cuidado: o custo pode explodir se não otimizar as partições, e a falta de joins nativos exige modelagem criativa.  
No fim, é ideal para quem prioriza performance e serverless, mas teste bem antes de mergulhar de cabeça.

## Referência
- Amazon DynamoDB - https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html

---
