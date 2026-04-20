# Arquitetura do Sistema

## 📌 Visão Geral

A arquitetura do Hub de Onboarding BellBank foi projetada para suportar um processo de onboarding corporativo eficiente, seguro e integrado entre diferentes áreas da organização.

A solução adota um modelo híbrido, combinando um núcleo modular com microsserviços desacoplados, garantindo equilíbrio entre simplicidade operacional e escalabilidade.

---

## 🖼️ Diagrama de Arquitetura

![Diagrama de Arquitetura](arquitetura.png)

---

## 🧠 Decisões Arquiteturais

- **Arquitetura híbrida**: utilização de um core modular para orquestração e microsserviços para domínios específicos  
- **Event-driven architecture**: comunicação assíncrona via Apache Kafka  
- **API Gateway**: centralização de acesso, segurança e roteamento  
- **Separação por domínios (DDD)**: organização em bounded contexts  
- **Integração com sistemas corporativos**: Entra ID, ServiceNow e plataformas internas  

---

## 🔗 Componentes Principais

- **Frontend Web/Mobile**: interface de acesso ao sistema  
- **API Gateway**: ponto único de entrada  
- **Core Hub**: orquestração do processo de onboarding  
- **Microsserviços**:
  - Provisioning Service  
  - Notification Service  
  - Assets Service  
  - AI/Data Service  
- **Kafka**: barramento de eventos  
- **Data Layer**:
  - PostgreSQL (transacional)  
  - Data Lake (analítico)  

---

## 🔄 Fluxo Simplificado

1. O colaborador é cadastrado no sistema (via RH/ATS)  
2. O Core Hub inicia o processo de onboarding  
3. Eventos são publicados no Kafka  
4. Serviços consomem eventos e executam ações específicas  
5. Integrações externas são acionadas (Entra ID, ServiceNow)  
6. Dados são armazenados para análise e melhoria contínua  

---

## 🎯 Objetivo da Arquitetura

- Reduzir acoplamento entre sistemas  
- Permitir evolução independente dos serviços  
- Garantir resiliência e escalabilidade  
- Facilitar integração com sistemas corporativos  
- Suportar análise de dados e inteligência artificial  

---

## 📂 Arquivos

- `arquitetura.drawio` → versão editável do diagrama

- <img width="1631" height="991" alt="arquitetura_hub_onboarding drawio" src="https://github.com/user-attachments/assets/4d54975d-8ac3-4e7c-87f3-9922309bf40a" />


