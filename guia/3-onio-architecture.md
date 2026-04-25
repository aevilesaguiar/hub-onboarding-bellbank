# Onion Architecture: protegendo o domínio por camadas concêntricas

Com a evolução dos sistemas de software, tornou-se cada vez mais evidente que arquiteturas tradicionais em camadas apresentam limitações importantes, principalmente no que se refere ao **acoplamento entre regras de negócio e infraestrutura**. Pequenas mudanças tecnológicas — como a troca de um banco de dados ou de um framework — acabam impactando diretamente o núcleo do sistema.

Nesse contexto, **Jeffrey Palermo**, em 2008, propôs a **Onion Architecture** como uma resposta direta a essas limitações, com o objetivo principal de **proteger o domínio da aplicação contra mudanças tecnológicas**.

---

## Motivação da Onion Architecture

A principal motivação da Onion Architecture é garantir que o **domínio da aplicação permaneça estável e isolado**, independentemente das tecnologias utilizadas ao seu redor.

Para isso, a arquitetura organiza o sistema de forma que **as dependências sempre apontem para o centro**, e nunca para fora. Em outras palavras:

> O domínio não depende da infraestrutura.  
> A infraestrutura depende do domínio.

Essa inversão de dependência é um dos pilares da Onion Architecture e está diretamente ligada a princípios fundamentais da engenharia de software, como **Separation of Concerns** e **Dependency Inversion**.

---

## A metáfora da cebola (onion)

Palermo utiliza a analogia da **cebola** para representar visualmente sua arquitetura. Assim como uma cebola possui camadas concêntricas, a Onion Architecture organiza o sistema em **anéis**, onde:

- o **núcleo interno** representa o domínio puro;
- as **camadas externas** representam partes do sistema com maior dependência tecnológica.

Quanto mais distante do centro, maior é a dependência de infraestrutura e frameworks.

---

## Estrutura da Onion Architecture

Visualmente e conceitualmente, a Onion Architecture pode ser entendida a partir de quatro camadas principais.

### Núcleo – Domínio

O núcleo da Onion Architecture contém o **domínio puro**, que representa o coração da aplicação. Aqui encontramos:

- entidades;
- regras de negócio;
- políticas de domínio.

Essa camada:
- não conhece frameworks;
- não conhece banco de dados;
- não conhece APIs externas;
- não possui dependências tecnológicas.

O domínio existe de forma **independente**, refletindo exclusivamente o conhecimento do negócio.

---

### Serviços de Aplicação

A camada de **serviços de aplicação** é responsável por:

- definir os casos de uso;
- orquestrar a lógica de negócio;
- coordenar entidades e regras do domínio.

Ela não contém regras de negócio complexas em si, mas **coordena o fluxo de execução**, aplicando o domínio de forma organizada.

---

### Interfaces (Ports)

A camada de interfaces define os **contratos de entrada e saída** do sistema. Esses contratos estabelecem como o mundo externo se comunica com a aplicação.

Aqui encontramos:
- interfaces de repositórios;
- interfaces de serviços externos;
- contratos de entrada (casos de uso).

Essas interfaces pertencem às camadas internas e **são implementadas externamente**, reforçando a inversão de dependência.

---

### Infraestrutura (Adapters)

A camada mais externa da Onion Architecture é a de **infraestrutura**, onde ficam as implementações concretas, como:

- controladores REST;
- repositórios de banco de dados;
- integrações com APIs externas;
- filas, mensageria e serviços externos;
- frameworks e bibliotecas.

Essa camada pode mudar com o tempo sem afetar o domínio, justamente por depender apenas dos contratos definidos internamente.

---

## Inversão de Dependência na prática

Assim como na Arquitetura Hexagonal, a Onion Architecture utiliza fortemente o **princípio da inversão de dependência**.

Por exemplo:
- o domínio define a interface de um repositório;
- a infraestrutura implementa esse repositório usando PostgreSQL, MySQL ou qualquer outra tecnologia.

Se a tecnologia de persistência mudar, apenas a camada de infraestrutura é impactada. O domínio permanece intacto.

---

## Benefícios da Onion Architecture

Ao organizar o sistema em camadas concêntricas, a Onion Architecture promove:

- **proteção do domínio**;
- **baixo acoplamento**;
- **alta coesão**;
- **facilidade de manutenção**;
- **evolução tecnológica segura**;
- **alta testabilidade**, especialmente de regras de negócio.

Alterações em camadas externas, como troca de ORM ou de mensageria, **não impactam o núcleo da aplicação**, tornando o sistema mais resiliente a mudanças.

---

## Considerações finais

A Onion Architecture incentiva o desenvolvimento de aplicações **robustas, testáveis e evolutivas**, colocando o domínio no centro da solução e tratando infraestrutura como um detalhe externo.

Mais do que uma simples organização de código, ela representa uma **postura arquitetural consciente**, voltada à sustentabilidade do software ao longo do tempo. Sua semelhança com a Arquitetura Hexagonal não é coincidência — ambas compartilham os mesmos princípios fundamentais e o mesmo objetivo: **proteger as regras de negócio**.

---

``
<img width="295" height="214" alt="image" src="https://github.com/user-attachments/assets/fe3ac433-d897-48c8-b954-3029b728c62f" />

