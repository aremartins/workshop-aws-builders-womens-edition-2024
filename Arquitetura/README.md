# Arquitetura

Neste workshop, utilizamos uma arquitetura de dados moderna e escalável para criar uma visão de 360 graus do cliente. Abaixo está uma descrição detalhada da arquitetura e do fluxo de dados.

## Diagrama de Arquitetura

![Diagrama de Arquitetura](https://github.com/aremartins/workshop-aws-builders-womens-edition-2024/blob/main/Arquitetura/Imagens/architeture-01.svg)

## Descrição da Arquitetura

1. **Amazon S3**: Utilizado como a camada de armazenamento persistente, com buckets para dados brutos (RawDataS3Bucket), estágio (StageDataS3Bucket) e analíticos (AnalyticsDataS3Bucket).

2. **AWS Glue**:
    - **Glue Crawlers**: Utilizados para escanear os conjuntos de dados e popular o Catálogo de Dados do Glue.
    - **Glue Jobs**: Utilizados para transformar e agregar dados utilizando Spark e Python.

3. **Amazon RDS**: Instância de banco de dados Aurora PostgreSQL para simular o banco de dados de transações.

4. **AWS Lambda**:
    - Funções Lambda utilizadas para gerar dados de diferentes fontes (simulando aplicações).
    - Integração com fontes externas, como Google Analytics.

5. **Amazon EMR**: Utilizado para processamento de Big Data, integrando-se com o Data Lake no Amazon S3 e executando tarefas utilizando Spark e Hive.

6. **Amazon Athena**: Utilizado para consultas interativas sobre os dados armazenados no Amazon S3, permitindo análise rápida e eficiente.

7. **Amazon DynamoDB**: Utilizado para fornecer acesso rápido e escalável aos dados processados.

8. **AWS Step Functions**: Orquestração de fluxos de trabalho envolvendo várias funções AWS Lambda e serviços como Athena.

## Fluxo de Dados

1. **Ingestão de Dados**:
    - Os dados são extraídos de diversas fontes (CRM, mainframe, Google Analytics) e carregados no Amazon S3.
    - Os Glue Crawlers escaneiam os dados no S3 e populam o Catálogo de Dados do Glue.

2. **Transformação de Dados**:
    - Utilizamos Glue Jobs e Amazon EMR para transformar e agregar os dados, preparando-os para análise.

3. **Análise de Dados**:
    - Utilizamos Amazon Athena para realizar consultas interativas sobre os dados transformados.
    - Os resultados das análises podem ser visualizados utilizando Amazon QuickSight.

## Benefícios da Arquitetura

- **Escalabilidade**: Capacidade de escalar o armazenamento e processamento de dados conforme necessário.
- **Flexibilidade**: Integração com diversas fontes de dados e utilização de múltiplas ferramentas de análise.
- **Eficiência**: Processamento rápido e eficiente de grandes volumes de dados.

## Recursos Utilizados

- **Buckets do Amazon S3**: RawDataS3Bucket, StageDataS3Bucket, AnalyticsDataS3Bucket, LogDataS3Bucket.
- **Instância RDS**: Aurora PostgreSQL.
- **Funções Lambda**: c360viewCRMApi, c360viewGetCRMApi, c360viewGetGaTables, c360viewMFgenAccount, c360viewMFgenCard, c360viewMFgenGBank.
- **Cluster Amazon EMR**.
- **Ferramentas de análise**: Amazon Athena, Amazon QuickSight.

---

Este documento fornece uma visão geral da arquitetura utilizada no workshop do AWS Builders Women's Edition 2024, destacando as principais tecnologias e processos envolvidos. Para mais detalhes, consulte os outros documentos neste repositório.

