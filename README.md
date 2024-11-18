# 📊 Pipeline para Análise de Dados de Chatbots (Telegram)

Este projeto implementa um **pipeline de ETL** utilizando **AWS** para extrair insights a partir de dados de conversas de chatbots no **Telegram**.

---

## 🎯 Objetivo
Transformar dados brutos de conversas em informações acionáveis para **otimizar o desempenho do chatbot** e **personalizar a experiência do usuário**.

---

## 🏗️ Arquitetura do Pipeline

### 1. **Ingestão**
- Um **bot no Telegram** captura mensagens e as envia via **webhook** para o **AWS API Gateway**.
- O **API Gateway** aciona uma **função AWS Lambda**, que armazena as mensagens em arquivos **JSON** no **AWS S3**, particionados por dia.

### 2. **ETL (Extração, Transformação e Carregamento)**
- O **AWS EventBridge** é configurado para acionar diariamente uma **função Lambda** que processa os dados do dia anterior.
- A função Lambda executa as seguintes etapas:
  - **Extração**: coleta dos arquivos JSON armazenados no S3.
  - **Transformação**: limpeza, denormalização e enriquecimento dos dados.
  - **Carregamento**: exportação dos dados transformados em formato **Parquet** para o S3.

### 3. **Análise**
- Uma tabela no **AWS Athena** é criada para referenciar os dados em formato Parquet no S3.
- Consultas **SQL** são utilizadas para explorar os dados e **extrair insights**.

---

## 💻 Tecnologias Utilizadas
- **Telegram Bot API**
- **AWS API Gateway**
- **AWS Lambda**
- **AWS S3**
- **AWS EventBridge**
- **AWS Athena**
- **Apache Parquet**

---

## 🚀 Benefícios
- **Escalabilidade** e **eficiência** com arquitetura serverless.
- **Análise de dados otimizada** utilizando Parquet e Athena.
- **Redução de custos** operacionais ao aproveitar recursos sob demanda.

---



