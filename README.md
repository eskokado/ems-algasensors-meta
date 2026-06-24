# AlgaSensors - Sistema de Monitoramento de Sensores

Este projeto é uma solução baseada em microserviços para o monitoramento e processamento de dados de sensores (especificamente temperatura), desenvolvida com foco em escalabilidade, manutenibilidade e boas práticas de engenharia de software utilizando o ecossistema Spring Boot.

## 🏗️ Arquitetura do Projeto

O ecossistema **AlgaSensors** é estruturado através de microserviços especializados que se comunicam para gerenciar dispositivos e processar dados ambientais:

- **[Device Management](./microservices/device-management)**: Gerencia o ciclo de vida dos dispositivos e sensores.
- **[Temperature Monitoring](./microservices/temperature-monitoring)**: Captura telemetria, registra logs de temperatura e gerencia alertas críticos.
- **[Temperature Processing](./microservices/temperature-processing)**: Processa e analisa dados brutos de temperatura para geração de insights e logs processados.

## 🛠️ Stack Tecnológico

- **Linguagem**: Java 21
- **Framework**: Spring Boot 3.4.0
- **Gerenciador de Dependências**: Gradle
- **Banco de Dados**: H2 (In-memory para desenvolvimento rápido)
- **Identificadores**: TSID (Time-Sorted Unique Identifiers) - mais performáticos que UUIDs para índices de banco de dados.
- **Diferenciais**:
  - Uso de **Hypersistence TSID** para IDs ordenáveis no tempo.
  - Princípios de **Clean Code** e separação de responsabilidades.
  - Configuração de **SonarQube** para análise de qualidade contínua.

## 🚀 Como Executar

### 1. Infraestrutura (Docker)

Suba os serviços de suporte (Banco de Dados Postgres e SonarQube):

```bash
docker compose up -d
```

### 2. Rodando os Microserviços

Cada serviço pode ser iniciado individualmente. Navegue até a pasta do microserviço e execute:

```bash
./gradlew bootRun
```

| Microserviço           | Porta Padrão |
| :--------------------- | :----------- |
| Device Management      | `8080`       |
| Temperature Processing | `8081`       |
| Temperature Monitoring | `8082`       |

## 📊 Qualidade de Código

Acesse o dashboard do SonarQube em [http://localhost:9000](http://localhost:9000) para visualizar as métricas de qualidade do projeto.

---

Desenvolvido como parte do aprendizado em arquitetura de microserviços.
