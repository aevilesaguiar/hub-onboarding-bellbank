# Hub de Onboarding BellBank

Projeto desenvolvido como parte do Tech Challenge 4 (FIAP – Pós-Tech Management), com foco na evolução técnica de uma solução interna de onboarding corporativo.

---

## 📖 Sobre o Projeto

O Hub de Onboarding BellBank é uma plataforma interna criada para integrar o processo de admissão de novos colaboradores, conectando áreas como RH, TI e Facilities.

A solução centraliza o fluxo de onboarding, reduzindo a fragmentação de processos e permitindo automação de tarefas críticas, como provisionamento de acessos e acompanhamento da jornada inicial do colaborador.

Diferentemente de soluções comerciais, este sistema foi projetado exclusivamente para uso interno, priorizando confiabilidade, segurança e integração com sistemas corporativos existentes.

---

## 🏗️ Arquitetura

A arquitetura adotada segue um modelo híbrido, combinando:

- Core modular responsável pela orquestração do onboarding  
- Microsserviços para funcionalidades específicas  
- Comunicação orientada a eventos com Apache Kafka  
- API Gateway como ponto de entrada  

Essa abordagem permite reduzir complexidade no domínio principal e manter escalabilidade nos serviços que exigem maior autonomia.

---

## 🔐 Segurança e Governança

O projeto incorpora práticas de segurança e governança, incluindo:

- Controle de acesso baseado em funções (RBAC)  
- Criptografia de dados (AES-256 e TLS)  
- Auditoria e rastreabilidade  
- Gestão segura de credenciais  

A governança técnica define papéis claros e garante evolução controlada do sistema.

---

## 📊 Dados e Inteligência Artificial

A arquitetura de dados é composta por:

- PostgreSQL (dados transacionais)  
- Apache Kafka (eventos)  
- Data Lake (dados analíticos)  

A camada de IA permite:

- recomendação de trilhas de onboarding  
- previsão de atrasos  
- análise de desempenho  

O uso de IA segue princípios de ética, transparência e conformidade com a LGPD.

---

## ⚙️ DevOps e DevSecOps

O pipeline foi estruturado com práticas de integração contínua e segurança integrada:

- Build e testes automatizados  
- Análise de segurança (SAST, dependency scan, container scan)  
- Deploy contínuo  
- Monitoramento e observabilidade  

A abordagem DevSecOps garante segurança em todo o ciclo de desenvolvimento.

---

## 🔗 Integrações

O Hub atua como orquestrador interno, integrando:

- Microsoft Entra ID (identidade e acessos)  
- ServiceNow (gestão de serviços e ativos)  
- Sistemas de recrutamento (ATS)  
- Plataformas de treinamento  

---

## 📎 Diagramas

Os diagramas foram desenvolvidos no Draw.io e estão disponíveis neste repositório.

---

## 🎯 Objetivos

- Reduzir o tempo de ramp-up de novos colaboradores  
- Automatizar o onboarding  
- Melhorar a integração entre áreas  
- Garantir segurança e conformidade  

---

## 👤 Autor

Aeviles de Aguiar Silva  
FIAP – Pós-Tech Management
