# Documentação de Arquitetura com o Modelo C4

Documentar arquitetura de software vai muito além de criar um único diagrama genérico que “mostra tudo”.

Na prática, esse tipo de documentação costuma gerar artefatos superficiais, difíceis de manter e que não cumprem seu papel principal: **comunicar de forma clara como o sistema funciona, como está estruturado e como se relaciona com o seu ambiente**.

Neste post rápido, vou demonstrar **o que é o Modelo C4** e como ele oferece uma forma simples e eficiente de documentar arquiteturas de software.

---

## O que é o Modelo C4?

O **Modelo C4**, criado por **Simon Brown**, é uma abordagem que combina um **método** com uma **linguagem visual** para representar arquiteturas de software.

Ele pode ser usado tanto na **concepção** quanto na **documentação** de sistemas, ajudando times técnicos e não técnicos a compreenderem a arquitetura no nível certo de detalhe.

O nome **C4** refere-se aos **quatro níveis de diagrama** propostos pelo modelo, que permitem visualizar o sistema de forma **incremental**, indo do mais alto nível até os detalhes de implementação.

---

## Os quatro níveis do Modelo C4

A ideia central do C4 é simples:  
**começar pelo todo e ir aprofundando aos poucos**, conforme a necessidade.

### 1️⃣ Contexto (System Context Diagram)

O diagrama de **Contexto** é o ponto de partida para entender um sistema.

Ele apresenta uma visão de alto nível, mostrando:
- o sistema como um todo;
- quem interage com ele (usuários);
- outros sistemas externos com os quais ele se integra.

Esse nível ajuda a responder perguntas como:
- **o que faz o sistema?**
- **quem interage com ele?**

O foco aqui é **negócio**, não tecnologia.

---

### 2️⃣ Contêineres (Container Diagram)

O diagrama de **Contêineres** aprofunda o detalhe da arquitetura.

Aqui mostramos as principais partes executáveis do sistema, como:
- aplicações web;
- APIs;
- bancos de dados;
- microsserviços;
- filas ou mensageria.

Esse nível ajuda a responder:
- **como o sistema está dividido logicamente?**
- **como essas partes se comunicam entre si?**

---

### 3️⃣ Componentes (Component Diagram)

No nível de **Componentes**, entramos dentro de um contêiner específico.

O objetivo é mostrar:
- os principais módulos internos;
- seus papéis e responsabilidades;
- como eles interagem.

Esse nível responde à pergunta:
- **quais são as peças principais dentro de cada contêiner e como elas se relacionam?**

---

### 4️⃣ Código (Code Diagram)

O nível de **Código** é o mais detalhado e geralmente opcional.

Aqui são representados:
- classes;
- arquivos;
- estrutura interna de implementação.

Esse nível é útil quando há necessidade de análise profunda do código, mas **nem sempre é necessário** para documentação arquitetural.

---

## Por que usar o Modelo C4?

O grande valor do C4 está em:
- melhorar a comunicação entre times;
- evitar diagramas confusos e genéricos;
- facilitar onboarding;
- permitir que cada público veja a arquitetura no nível adequado.

Em vez de um único diagrama tentando “explicar tudo”, o C4 organiza a documentação em **camadas de entendimento**.

---

## Conclusão

O Modelo C4 é uma forma simples, visual e incremental de documentar arquiteturas de software.

Referencias;

c https://c4model.com/introduction
https://zup.com.br/blog/c4-model/

https://medium.com/cajudevs/entendendo-o-c4-model-uma-abordagem-para-arquitetura-de-software-3ed0f007ae66

https://programadriano.medium.com/dica-r%C3%A1pida-o-que-%C3%A9-o-c4-model-ea7278c437cf
