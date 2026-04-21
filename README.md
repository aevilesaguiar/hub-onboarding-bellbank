# Hub de Onboarding BellBank

Projeto desenvolvido como parte do Tech Challenge 4 (FIAP – Pós-Tech Management), com foco na evolução técnica de uma solução interna voltada à integração de colaboradores no ambiente corporativo.

# 🏦 Hub de Onboarding BellBank

## 📌 Visão Geral

O Hub de Onboarding BellBank é uma plataforma interna corporativa desenvolvida para automatizar e integrar o processo de admissão de colaboradores, promovendo maior eficiência operacional, redução de retrabalho e melhoria da experiência do colaborador.

A solução foi projetada para atuar como um orquestrador central, conectando diferentes áreas do banco — como Recursos Humanos, Tecnologia da Informação e Facilities — por meio de uma arquitetura moderna, segura e orientada a eventos.

---

## 🎯 Objetivo do Projeto

- Automatizar o processo de onboarding corporativo  
- Integrar sistemas internos do BellBank  
- Reduzir tempo e erros operacionais  
- Garantir segurança e conformidade (LGPD)  
- Suportar decisões baseadas em dados e IA  

---

## 🏗️ Arquitetura da Solução

A arquitetura adota um modelo **híbrido**, combinando:

- Core modular (monólito modular) para orquestração  
- Microsserviços desacoplados para domínios específicos  
- Comunicação assíncrona via Apache Kafka (Event-Driven Architecture)  

### Principais componentes:

- API Gateway  
- Core Hub  
- Microsserviços (Provisioning, Notification, Assets, AI/Data)  
- Kafka (event bus)  
- PostgreSQL (dados transacionais)  
- Data Lake (dados analíticos)  

📌 Detalhes completos:  
👉 [`/arquitetura`](./arquitetura)

---

## 🏛️ Governança de Tecnologia

A governança foi estruturada para garantir controle, consistência e alinhamento com o negócio.

Inclui:

- Definição de papéis (Tech Manager, Arquiteto, Segurança, Dados/IA)  
- Fluxo de decisão técnica  
- Matriz RACI  
- Gestão de riscos  
- Conformidade com LGPD  

📌 Detalhes completos:  
👉 [`/governanca`](./governanca)

---

## 📊 Dados & Inteligência Artificial

A estratégia de dados transforma o Hub em uma plataforma orientada a dados.

Inclui:

- Arquitetura em camadas (PostgreSQL + Kafka + Data Lake)  
- OCR para validação de documentos  
- Modelos de IA para análise e recomendação  
- KPI de precisão ≥ 98%  
- Governança de dados e IA  
- Human-in-the-loop  

📌 Detalhes completos:  
👉 [`/data-ai`](./data-ai)

---

## 🔐 DevOps & DevSecOps

O projeto adota práticas modernas de automação e segurança:

- Pipeline CI/CD automatizado  
- Segurança integrada (Shift-Left)  
- SAST, SCA e scanning de containers  
- Monitoramento contínuo  
- Red Team, Blue Team e Purple Team  

📌 Detalhes completos:  
👉 [`/devsecops`](./devsecops)

---

## 🔗 Integração com Ecossistema

O Hub atua como integrador central de sistemas corporativos:

- Microsoft Entra ID (identidade)  
- ServiceNow (gestão de serviços)  
- ATS (sistema de recrutamento)  
- LMS (treinamento)  

A integração ocorre via:

- APIs REST (comunicação síncrona)  
- Kafka (comunicação assíncrona)  

---

## 🔄 Fluxo do Onboarding

1. ATS envia dados do colaborador  
2. Core Hub inicia o onboarding  
3. Eventos são publicados no Kafka  
4. Microsserviços executam ações específicas  
5. Sistemas externos são acionados  
6. Dados são armazenados e analisados  
7. Monitoramento contínuo da operação  

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

## 📈 Roadmap Técnico

- **Curto prazo:** automação inicial do onboarding  
- **Médio prazo:** integração com sistemas corporativos  
- **Longo prazo:** uso avançado de dados e inteligência artificial  

---

## 🔐 Segurança e Conformidade

- Conformidade com LGPD  
- Criptografia de dados  
- Controle de acesso (RBAC)  
- Auditoria e rastreabilidade  
- Monitoramento contínuo  

---

## 📂 Estrutura do Repositório
