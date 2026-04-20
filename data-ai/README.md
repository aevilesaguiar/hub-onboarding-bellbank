# Dados e Inteligência Artificial

## 📌 Visão Geral

A estratégia de dados do Hub de Onboarding BellBank foi desenhada para suportar tanto operações transacionais quanto análises estratégicas, permitindo melhoria contínua do processo de onboarding.

---

## 🏗️ Arquitetura de Dados

![Arquitetura de Dados](arquitetura-dados.png)

A arquitetura é composta por:

- **PostgreSQL**: armazenamento de dados operacionais  
- **Apache Kafka**: ingestão e distribuição de eventos  
- **Data Lake**: consolidação de dados históricos  
- **Camada analítica (BI)**: geração de insights  

---

## 🤖 Uso de Inteligência Artificial

A camada de IA foi projetada para apoiar decisões e otimizar a experiência do colaborador.

Principais aplicações:

- Recomendação de trilhas de onboarding  
- Previsão de atrasos no processo  
- Identificação de gargalos operacionais  
- Análise de engajamento  

---

## 📊 Pipeline de Dados

1. Eventos são gerados pelos serviços (Kafka)  
2. Dados são persistidos em banco transacional  
3. Eventos são enviados para o Data Lake  
4. Dados são processados para análise e IA  
5. Insights são disponibilizados para o negócio  

---

## 🔐 Governança de Dados

- Classificação de dados (sensíveis e não sensíveis)  
- Controle de acesso baseado em perfil  
- Criptografia em trânsito e em repouso  
- Conformidade com LGPD  

---

## 🎯 Objetivos

- Melhorar a experiência de onboarding  
- Aumentar eficiência operacional  
- Apoiar decisões baseadas em dados  
- Garantir segurança e conformidade  
