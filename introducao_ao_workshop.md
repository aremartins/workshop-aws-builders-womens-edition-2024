# Introdução ao Workshop

Um caso de uso muito comum em organizações é a necessidade de analisar clientes sob diferentes perspectivas, como fidelização (anos de história, frequência de interação) ou demografia (estágio de vida, renda). Chamamos isso de dimensões e combinamos várias dimensões sobre o cliente para fornecer uma visão completa de várias perspectivas ao mesmo tempo.

Os desafios incluem:
- Dados em vários sistemas de origem
- Caos e fragmentação dos dados
- Governança de dados
- Crescimento e mudança dos dados

![Visão 360](https://github.com/aremartins/workshop-aws-builders-womens-edition-2024/blob/main/customer-360.png)

  

Neste workshop, exploramos uma empresa hipotética com dimensões comuns ao setor e outras válidas para qualquer setor de serviços, como marketing e comunicações, histórico do cliente ou dimensão demográfica.

## Diagrama de Arquitetura da Oficina

Usamos o AWS Glue para extrair dados do banco de dados relacional para o Amazon S3, utilizando o conector AWS Glue e trabalhos do Glue. Abaixo temos a camada persistente no Amazon S3, que é a base da nossa estratégia de Data Lake, com buckets Raw, Stage e Analytics. Para processamento, usamos Step Functions orquestrando AWS Lambda com Athena no topo, além de AWS Glue Jobs e Amazon EMR para transformar e agregar dados. Para consumir os dados, utilizamos o console e a API do mecanismo de consulta do Amazon Athena e do Amazon DynamoDB.

## Domínios e Fontes de Dados

- **Informação do Cliente:** CRM (API - JSON)
- **Transações:** Fontes de mainframe (Banco de dados relacional)
- **Cartão de Crédito:** Sistema de originação de cartões (Arquivo de texto)
- **Conta:** Sistema de originação de conta (Arquivo de texto)
- **Banco Geral:** Banco de Dados de Disposições (Arquivo de texto)
- **Web Analytics:** Google Analytics (JSON com campos aninhados)
- **Histórico de Compras:** Vendas no Varejo (Arquivo CSV)

## Recursos Provisionados

- 4 buckets do Amazon S3: RawDataS3Bucket, StageDataS3Bucket, AnalyticsDataS3Bucket, LogDataS3Bucket
- 1 instância RDS com banco de dados Aurora PostgreSQL
- Funções Lambda para gerar dados de diferentes fontes (simulando uma aplicação)
- Regras do Eventbridge para acionar as funções do Lambda
- Grupo de segurança e firewalls
- 1 cluster do Amazon EMR
