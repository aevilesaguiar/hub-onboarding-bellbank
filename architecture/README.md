# 🏦 Arquitetura do Hub de Onboarding BellBank

## 📌 Visão Geral

A arquitetura do Hub de Onboarding BellBank foi projetada como uma plataforma interna corporativa, com o objetivo de automatizar e integrar o processo de onboarding entre diferentes áreas da organização.

A solução adota um modelo híbrido, combinando um núcleo modular (monólito modular) com microsserviços desacoplados, permitindo equilibrar simplicidade operacional, governança e escalabilidade.

---

## 🖼️ Diagrama de Arquitetura

<img width="1567" height="1004" alt="ChatGPT Image 21 de abr  de 2026, 12_31_30" src="https://github.com/user-attachments/assets/7a5572f0-516e-405f-bf60-89d2ca9e8005" />

---

## 🧠 Decisões Arquiteturais

- **Arquitetura híbrida:** core modular para orquestração e microsserviços para domínios específicos  
- **Event-Driven Architecture:** comunicação assíncrona via Apache Kafka  
- **Resiliência:** uso de retry, idempotência e Dead Letter Queue (DLQ)  
- **API Gateway:** centralização de autenticação, autorização e roteamento  
- **DDD (Domain-Driven Design):** separação por bounded contexts  
- **BFF (Backend for Frontend):** adaptação para diferentes interfaces  
- **Integração corporativa:** conexão com sistemas internos como Entra ID, ServiceNow e ATS  

---

## 🔗 Componentes Principais

### Camada de Experiência
- Frontend Web / Mobile

### Camada de Entrada
- API Gateway

### Camada de Domínio
- Core Hub (monólito modular)
- Provisioning Service
- Notification Service
- Assets Service
- AI/Data Service

### Camada de Integração
- Apache Kafka (Event Bus)

### Camada de Dados
- PostgreSQL (dados transacionais)
- Data Lake (dados analíticos)

### Observabilidade
- Logs, métricas e tracing distribuído  
- Prometheus, Grafana, OpenTelemetry  

---

## 🔄 Fluxo Simplificado

1. O sistema de RH (ATS) envia os dados do colaborador via API Gateway  
2. O Core Hub inicia o processo de onboarding  
3. Eventos são publicados no Kafka  
4. Microsserviços consomem eventos e executam ações específicas  
5. Integrações externas são acionadas (Entra ID, ServiceNow)  
6. Dados são persistidos no PostgreSQL e enviados ao Data Lake  
7. Logs e métricas são coletados para monitoramento contínuo  

---

## 🛠️ Tecnologias Utilizadas

- Backend: (definir — ex: Java / Node.js)  
- Mensageria: Apache Kafka  
- Banco de dados: PostgreSQL  
- Data: Data Lake / BI  
- Segurança: RBAC, criptografia  
- DevOps: CI/CD, containers  
- Observabilidade: Prometheus, Grafana, OpenTelemetry  

---

## 🎯 Objetivo da Arquitetura

- Reduzir acoplamento entre sistemas  
- Permitir evolução independente dos serviços  
- Garantir resiliência e tolerância a falhas  
- Facilitar integração com sistemas corporativos  
- Suportar análise de dados e inteligência artificial  
- Manter governança técnica com baixa complexidade operacional  

---




