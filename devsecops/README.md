# 🔐 DevSecOps – Hub de Onboarding BellBank

## 📌 Visão Geral

A estratégia de DevOps e segurança integrada (DevSecOps) do Hub de Onboarding BellBank foi definida para garantir automação, qualidade e segurança ao longo de todo o ciclo de desenvolvimento.

Por se tratar de uma plataforma interna corporativa, a abordagem prioriza confiabilidade operacional, controle de mudanças e proteção de dados sensíveis, assegurando entregas seguras e consistentes.

---

## 🔄 Pipeline DevOps

O pipeline foi estruturado para automatizar o ciclo completo de desenvolvimento e entrega.

<img width="1536" height="1024" alt="devsecops" src="https://github.com/user-attachments/assets/4cddb2be-e4b6-4b73-9cad-509de59d7a02" />



### Fluxo do Pipeline

1. Desenvolvedor realiza commit no repositório  
2. Pipeline executa build automatizado  
3. Execução de testes unitários e de integração  
4. Análises de segurança (SAST, SCA e scanning de containers)  
5. Validação do artefato  
6. Deploy automatizado em ambiente controlado  
7. Monitoramento contínuo da aplicação  

---

## 🧪 Etapas do Pipeline

### 🔹 Versionamento e Controle
- Uso de repositório Git  
- Controle de branches  
- Pull Request com revisão de código  

### 🔹 Integração Contínua (CI)
- Build automatizado  
- Validação de dependências  
- Empacotamento da aplicação  

### 🔹 Testes Automatizados
- Testes unitários  
- Testes de integração  
- Validação de contratos entre serviços  

### 🔹 Segurança Shift-Left
- SAST (análise estática de código)  
- SCA (análise de dependências)  
- Scanning de containers  
- Identificação precoce de vulnerabilidades  

### 🔹 Entrega Contínua (CD)
- Deploy automatizado  
- Ambientes controlados  
- Rollback automático em caso de falha  

### 🔹 Monitoramento
- Logs e métricas  
- Alertas automatizados  
- Tracing distribuído  

---

## 🔐 Estratégia DevSecOps

A segurança é integrada ao ciclo de desenvolvimento desde o início, reduzindo riscos e vulnerabilidades.

### Controles de Segurança

- Criptografia de dados em trânsito e em repouso  
- Controle de acesso baseado em papéis (RBAC)  
- Gestão segura de credenciais e segredos  
- Auditoria e rastreabilidade de ações  
- Monitoramento contínuo de segurança  

---

## 🛡️ Práticas de Segurança

- Revisão de código obrigatória  
- Segregação de funções  
- Análise contínua de vulnerabilidades  
- Monitoramento de incidentes  
- Resposta rápida a falhas  

---

## ⚔️ Abordagem de Times

### 🔴 Red Team
- Simulação de ataques  
- Identificação de vulnerabilidades  

### 🔵 Blue Team
- Monitoramento e resposta a incidentes  
- Detecção de comportamentos suspeitos  

### 🟣 Purple Team
- Integração entre ataque e defesa  
- Melhoria contínua dos controles de segurança  

---

## 📊 Indicadores (KPIs)

- Taxa de sucesso dos pipelines  
- Tempo médio de deploy  
- Número de falhas em produção  
- MTTR (tempo médio de recuperação)  
- Vulnerabilidades identificadas  
- Percentual de correções antes da produção  
- Disponibilidade dos serviços  

---

## 🔐 Segurança na Arquitetura

A estratégia DevSecOps está integrada à arquitetura do sistema:

- API Gateway com controle de acesso  
- Kafka com resiliência (retry, DLQ)  
- Observabilidade com métricas e tracing  
- Integração segura com sistemas corporativos  

---

## 🛠️ Tecnologias Utilizadas

- CI/CD: GitHub Actions / GitLab CI / Jenkins  
- Containers: Docker  
- Segurança: SAST, SCA, scanning de imagens  
- Monitoramento: Prometheus, Grafana, OpenTelemetry  
- Versionamento: Git  

---

## 🎯 Objetivo da Estratégia

- Automatizar o ciclo de desenvolvimento e entrega  
- Garantir segurança desde a concepção (Shift-Left)  
- Reduzir falhas em produção  
- Aumentar confiabilidade e previsibilidade  
- Proteger dados sensíveis  
- Sustentar a operação em ambiente corporativo crítico  

---

