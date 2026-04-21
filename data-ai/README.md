# 📊 Data & AI – Hub de Onboarding BellBank

## 📌 Visão Geral

A estratégia de Dados e Inteligência Artificial do Hub de Onboarding BellBank foi projetada para transformar dados operacionais em ativos estratégicos, apoiando decisões e aumentando a eficiência do processo de onboarding.

Por se tratar de uma plataforma interna corporativa, a solução prioriza segurança, governança de dados e uso responsável da inteligência artificial, garantindo conformidade com a LGPD e confiabilidade das informações.

---

## 🏗️ Arquitetura de Dados

A arquitetura de dados foi estruturada em camadas, separando processamento operacional e analítico:

<img width="1536" height="1024" alt="arquitetura_dedados" src="https://github.com/user-attachments/assets/1499e29e-de1c-4632-ab3d-f24a20fdafef" />


### 🔹 Camada Transacional (Operational Data)
- Armazena dados operacionais do onboarding  
- Tecnologia: PostgreSQL  
- Exemplos: colaboradores, admissões, status, acessos e ativos  

### 🔹 Camada de Integração (Event Streaming)
- Comunicação e distribuição de dados entre serviços  
- Tecnologia: Apache Kafka  
- Função: desacoplamento, integração assíncrona e processamento de eventos  

### 🔹 Camada Analítica (Data Lake / BI)
- Armazena dados históricos e eventos processados  
- Utilizada para dashboards, métricas e relatórios  
- Suporte à tomada de decisão  

---

## 🔄 Fluxo de Dados

1. Dados são gerados no Core Hub e microsserviços  
2. Eventos são publicados no Kafka  
3. Dados são consumidos por serviços e enviados ao Data Lake  
4. Informações são consolidadas para análise e indicadores  
5. Dados alimentam modelos de inteligência artificial  

---

## 🧠 Estratégia de Inteligência Artificial

A camada de IA foi definida para apoiar a automação e melhoria contínua do onboarding.

### Principais casos de uso:
- OCR para validação de documentos  
- Identificação de inconsistências  
- Análise de desempenho do onboarding  
- Geração de insights e recomendações  

---

## 🎯 Modelo de IA e Qualidade

- Uso de OCR para extração de dados  
- KPI principal: **≥ 98% de precisão**  
- Monitoramento contínuo da acurácia  
- Validação de baixa confiança direcionada para revisão humana  

---

## 🧑‍⚖️ Governança de IA

A estratégia de IA segue princípios de uso responsável:

- Human-in-the-loop (validação humana em casos críticos)  
- Auditoria de decisões automatizadas  
- Monitoramento de viés  
- Transparência no uso dos modelos  
- Proibição de decisões totalmente automatizadas em processos sensíveis  

---

## 🔐 Governança de Dados

- Controle de acesso baseado em papéis (RBAC)  
- Criptografia de dados em trânsito e em repouso  
- Auditoria e rastreabilidade de acessos  
- Validação e padronização de dados  
- Monitoramento da qualidade da informação  
- Políticas de retenção e descarte  

---

## 📊 Indicadores (KPIs)

- Precisão do OCR (≥ 98%)  
- Tempo médio de onboarding  
- Taxa de erro no processo  
- Número de validações humanas  
- Performance dos modelos de IA  
- Qualidade e integridade dos dados  

---

## 🔐 Segurança e Conformidade

- Conformidade com LGPD  
- Proteção de dados sensíveis  
- Monitoramento contínuo  
- Auditoria de acessos e operações  

---

## 🛠️ Tecnologias Utilizadas

- Banco de dados: PostgreSQL  
- Mensageria: Apache Kafka  
- Data: Data Lake / BI  
- IA: OCR / modelos preditivos  
- Segurança: RBAC, criptografia  

---

## 🎯 Objetivo da Estratégia

- Transformar dados operacionais em insights estratégicos  
- Apoiar decisões baseadas em dados  
- Automatizar etapas do onboarding com IA  
- Garantir uso ético e seguro da tecnologia  
- Melhorar continuamente a experiência do colaborador  

---

## 📂 Arquivos

- `data-architecture.drawio` → diagrama de dados  
- `data-architecture.png` → visualização  
- `ai-flow.png` → fluxo de IA  
