# Buckets do Amazon S3

Neste workshop, utilizamos vários buckets do Amazon S3 para armazenar e organizar os dados em diferentes estágios do processamento. Abaixo está uma descrição dos buckets utilizados e suas respectivas finalidades.

## Buckets Utilizados

### 1. RawDataS3Bucket

**Descrição:**  
Este bucket é utilizado para armazenar os dados brutos que são extraídos de diversas fontes. Esses dados estão no seu formato original e ainda não passaram por nenhum tipo de processamento ou transformação.

**Finalidade:**  
- Armazenar dados brutos para posterior processamento.
- Manter uma cópia original dos dados para referência.

### 2. StageDataS3Bucket

**Descrição:**  
Este bucket é utilizado para armazenar dados que estão em estágio intermediário de processamento. Os dados aqui são geralmente limpos e transformados, mas ainda não estão prontos para análise final.

**Finalidade:**  
- Armazenar dados que foram transformados e limpos.
- Servir como uma área intermediária antes dos dados serem movidos para o bucket de análises.

### 3. AnalyticsDataS3Bucket

**Descrição:**  
Este bucket é utilizado para armazenar dados que estão prontos para análise. Esses dados foram totalmente processados e transformados, e estão preparados para serem consultados e analisados utilizando ferramentas como o Amazon Athena.

**Finalidade:**  
- Armazenar dados prontos para análise.
- Facilitar consultas e análises eficientes utilizando ferramentas como o Amazon Athena.

### 4. LogDataS3Bucket

**Descrição:**  
Este bucket é utilizado para armazenar logs de atividades e processamento. Manter registros detalhados das operações realizadas é crucial para monitoramento, auditoria e depuração.

**Finalidade:**  
- Armazenar logs de atividades e processamento.
- Facilitar o monitoramento e a auditoria das operações realizadas.

## Diagrama de Transformação de Dados

Abaixo está um diagrama que ilustra as etapas de transformação de dados que ocorrem entre os diferentes buckets S3:

![Diagrama de Transformação de Dados](../Imagens/adv-trans.svg)

---

Este documento fornece uma visão geral dos buckets do Amazon S3 utilizados no workshop do AWS Builders Women's Edition 2024, destacando suas finalidades e como eles se encaixam na arquitetura geral.
