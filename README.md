# Hub de Onboarding BellBank

Projeto desenvolvido como parte do Tech Challenge 4 (FIAP – Pós-Tech Management), com foco na evolução técnica de uma solução interna voltada à integração de colaboradores no ambiente corporativo.

---

## 📖 Sobre o Projeto

O Hub de Onboarding BellBank é uma plataforma interna criada para organizar e integrar o processo de admissão de novos colaboradores, conectando áreas como RH, TI e Facilities.

O processo de onboarding, quando descentralizado, tende a gerar atrasos, retrabalho e falta de visibilidade entre equipes. A proposta do Hub é atuar como um orquestrador central, estruturando esse fluxo de ponta a ponta e reduzindo a dependência de processos manuais.

A solução permite automatizar etapas críticas, como provisionamento de acessos, acompanhamento da jornada inicial e comunicação entre áreas, garantindo maior eficiência operacional e melhor experiência para o colaborador.

Por se tratar de um sistema interno, a arquitetura foi pensada priorizando confiabilidade, segurança e integração com sistemas corporativos já existentes no BellBank.

---

## 🏗️ Arquitetura

A arquitetura segue um modelo híbrido, combinando um núcleo modular com serviços desacoplados.

O core do sistema é responsável pela orquestração do processo de onboarding, enquanto funcionalidades específicas são tratadas como microsserviços independentes. Essa divisão permite equilibrar simplicidade operacional e escalabilidade.

A comunicação entre os componentes ocorre de forma assíncrona, utilizando Apache Kafka, garantindo desacoplamento e maior resiliência. O acesso ao sistema é organizado por meio de um API Gateway, centralizando as requisições e facilitando a governança.

Essa abordagem reduz a complexidade do domínio principal sem comprometer a capacidade de evolução do sistema.

---

## 🔐 Segurança e Governança

A segurança da informação é tratada como um elemento central da solução, considerando o alto grau de sensibilidade dos dados corporativos.

O projeto adota controle de acesso baseado em funções (RBAC), criptografia de dados em repouso e em trânsito (AES-256 e TLS), além de mecanismos de auditoria e rastreabilidade das operações.

A governança técnica define responsabilidades claras entre os papéis envolvidos, garantindo consistência nas decisões e evolução controlada da arquitetura.

---

## 📊 Dados e Inteligência Artificial

Os dados gerados pelo processo de onboarding são tratados como ativos estratégicos.

A arquitetura de dados separa claramente o contexto transacional do analítico, utilizando PostgreSQL para operações do dia a dia e um Data Lake para consolidação e análise de informações.

O Apache Kafka atua como intermediador dos eventos, permitindo que diferentes serviços consumam dados de forma assíncrona.

A camada de inteligência artificial utiliza esses dados para apoiar o processo de onboarding, permitindo recomendações, identificação de gargalos e análise de desempenho.

Todo o uso de IA segue diretrizes de ética, transparência e conformidade com a LGPD.

---

## ⚙️ DevOps e DevSecOps

O ciclo de desenvolvimento foi estruturado com base em práticas de DevOps, garantindo automação e consistência nas entregas.

O pipeline inclui etapas de build, testes automatizados e validações de segurança, reduzindo riscos e aumentando a qualidade do software.

A abordagem DevSecOps integra a segurança desde o início do desenvolvimento, com uso de ferramentas de análise de código, verificação de dependências e análise de containers.

Além disso, práticas de monitoramento e observabilidade permitem acompanhar o comportamento do sistema em tempo real.

---

## 🔗 Integrações

O Hub atua como um orquestrador interno, conectando diferentes sistemas corporativos do BellBank.

Entre as principais integrações estão:

- Microsoft Entra ID, para gestão de identidade e acessos  
- ServiceNow, para controle de ativos e serviços  
- Sistemas de recrutamento (ATS)  
- Plataformas de treinamento e capacitação  

A comunicação ocorre por meio de APIs seguras e eventos, garantindo flexibilidade e desacoplamento entre os sistemas.

---

## 📎 Diagramas

Os diagramas deste projeto foram desenvolvidos no Draw.io e estão organizados neste repositório, separados por domínio:

- Arquitetura  
- Governança e riscos  
- Dados e IA  
- DevSecOps  

---

## 🎯 Objetivos

- Reduzir o tempo de adaptação de novos colaboradores  
- Automatizar etapas críticas do onboarding  
- Melhorar a integração entre áreas  
- Garantir segurança e conformidade no uso de dados  
- Estruturar o onboarding como um processo digital integrado  

---

## 👤 Autor

Aeviles de Aguiar Silva  
FIAP – Pós-Tech Management
