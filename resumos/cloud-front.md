### Code girls - AWS

---

## 5. Amazon CloudFront

O Amazon CloudFront é o serviço de rede de distribuição de conteúdo (Content Delivery Network CDN) da Amazon Web Services (AWS).  
Ele tem como principal objetivo entregar dados, vídeos, aplicações e APIs aos usuários com baixa latência e alta velocidade de transferência.  
O serviço utiliza uma rede global de pontos de presença (edge locations), que armazenam cópias do conteúdo mais próximo dos usuários finais, garantindo melhor desempenho e menor tempo de resposta.

### Conceito e Funcionamento
O CloudFront atua como uma camada intermediária entre os usuários e o servidor de origem.  
Quando um usuário solicita um arquivo, o serviço verifica se ele está disponível no ponto de presença mais próximo.  
Caso esteja, o conteúdo é entregue imediatamente.  
Se não estiver, o CloudFront busca o arquivo no servidor de origem, que pode ser um bucket S3, um Elastic Load Balancer ou um servidor HTTP externo, e armazena uma cópia temporária para futuras solicitações.  
Esse processo melhora o desempenho e reduz o consumo de largura de banda.

### Principais Recursos
- Baixa latência, alta disponibilidade e distribuição global.
- Integração com outros serviços da AWS: Amazon S3, EC2, Elastic Load Balancing e Route 53.
- Recursos avançados de segurança: suporte a HTTPS, AWS Shield, AWS WAF e URLs assinadas para controle de acesso.
- Cache personalizado, suporte a conteúdo estático e dinâmico e monitoração contínua por meio do Amazon CloudWatch.

### Boas Práticas
- Uso de certificados SSL ou TLS para proteger o tráfego.
- Configuração de políticas de cache adequadas para cada tipo de conteúdo.
- Integração com o AWS WAF para prevenir ataques.
- Utilização do Origin Access Control (OAC) para restringir o acesso direto aos buckets S3.
- Monitorar métricas de desempenho e ajustar parâmetros conforme o comportamento dos usuários.

### Conclusão
O Amazon CloudFront é uma ferramenta essencial para organizações que buscam alto desempenho, segurança e disponibilidade global na entrega de conteúdo.  
Ele melhora significativamente a experiência dos usuários, reduz custos de transferência de dados e aumenta a eficiência operacional das aplicações hospedadas na nuvem.  
Por sua integração com os demais serviços da AWS, o CloudFront se destaca como uma das soluções mais completas para distribuição e aceleração de conteúdo em escala global.

### Referência
- Amazon CloudFront - https://docs.aws.amazon.com/AmazonCloudFront/

---
