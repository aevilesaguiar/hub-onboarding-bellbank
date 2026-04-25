# Vertical Slice Architecture: organizando o sistema por funcionalidade

Com o crescimento da complexidade dos sistemas de software, muitos projetos passaram a sofrer com estruturas rígidas e difíceis de evoluir. Um dos principais problemas observados em arquiteturas tradicionais é a organização do código **por tipo técnico** — controllers, services, repositories, models — em vez de **por funcionalidade de negócio**.

A **Vertical Slice Architecture** surge como uma resposta direta a esse problema, propondo uma organização mais alinhada ao fluxo real de valor do sistema.

---

## Origem e contexto da Vertical Slice Architecture

A Vertical Slice Architecture começou a ganhar força por volta de **2014**, especialmente com a popularização de dois conceitos importantes:

- **CQRS (Command Query Responsibility Segregation)**  
- **Feature-based design**  

Na comunidade .NET, **Jimmy Bogard** foi um dos principais responsáveis por difundir e aplicar essa abordagem de forma prática, mostrando como ela melhora a organização, a testabilidade e a evolução dos sistemas.

---

## A crítica ao modelo em camadas tradicionais

Em arquiteturas em camadas, é comum encontrarmos estruturas como:

- Controllers  
- Services  
- Repositories  
- Models  

Esse modelo, apesar de organizado tecnicamente, cria alguns problemas frequentes:

- funcionalidades espalhadas por várias pastas;
- alto acoplamento entre componentes;
- dificuldade para entender o fluxo completo de uma feature;
- mudanças simples exigindo alterações em vários pontos do código.

A Vertical Slice Architecture parte da crítica de que **o sistema deveria ser organizado em torno das funcionalidades reais de negócio**, e não dos tipos de artefatos técnicos.

---

## O que é Vertical Slice Architecture

A Vertical Slice Architecture propõe organizar o sistema em **fatias verticais independentes**, onde cada *slice* representa uma **funcionalidade completa**.

Cada slice contém tudo o que é necessário para funcionar:
- entrada (input),
- processamento (caso de uso),
- saída (output).

Em vez de atravessar várias camadas horizontais, uma funcionalidade percorre **uma fatia vertical do sistema**, do início ao fim.

---

## O papel do CQRS na Vertical Slice Architecture

O **CQRS (Command Query Responsibility Segregation)** é um padrão fortemente associado à Vertical Slice Architecture. Ele propõe a separação clara entre:

- **Commands**: operações de escrita;
- **Queries**: operações de leitura.

Essa separação permite que leitura e escrita evoluam de forma independente, tanto em estrutura quanto em tecnologia.

---

## Como o CQRS funciona

O funcionamento do CQRS pode ser entendido em etapas claras:

### Escrita (Command)

- A aplicação executa um **Command**.
- O command grava os dados em um **Write Database**.
- Esse banco é otimizado para escrita, sendo normalmente normalizado e com foco em consistência e validações de negócio.

---

### Propagação de eventos

- Após a escrita ser concluída com sucesso, **eventos** são publicados.
- Esses eventos representam fatos que ocorreram no domínio.
- Eles permitem a sincronização entre diferentes modelos de dados.

---

### Leitura (Query)

- Os eventos atualizam o **Read Database**.
- Esse banco é otimizado para leitura, geralmente desnormalizado e com índices específicos.
- Podem existir múltiplas projeções dos mesmos dados, de acordo com a necessidade das consultas.

---

### APIs de leitura

- As **Read APIs** realizam consultas diretas ao banco de leitura.
- As queries tornam-se simples e performáticas, sem joins complexos.

---

## Benefícios do CQRS

A adoção do CQRS traz vantagens importantes:

- **Performance**, com otimização independente de leitura e escrita;
- **Escalabilidade**, permitindo escalar modelos de leitura e escrita separadamente;
- **Flexibilidade**, com uso de diferentes tecnologias conforme a necessidade;
- **Simplicidade nas queries**, graças a dados desnormalizados.

---

## Estrutura de código na Vertical Slice Architecture

Em vez de estruturas genéricas por tipo técnico, a Vertical Slice organiza o código por funcionalidade. Por exemplo:

/Features
/CreateOrder
CreateOrderCommand.cs
CreateOrderHandler.cs
CreateOrderValidator.cs
OrderCreatedEvent.cs
/GetOrder
GetOrderQuery.cs
GetOrderHandler.cs

Cada funcionalidade fica:
- isolada;
- fácil de entender;
- altamente testável;
- com baixa dependência das demais.

---

## Vertical Slice em APIs e aplicações modernas

Em sistemas REST, é comum que **cada endpoint HTTP represente uma slice**.  
Em aplicações que utilizam **MediatR**, a abordagem se encaixa naturalmente com **Handlers** para Commands e Queries.

Isso cria uma estrutura que reflete diretamente o comportamento do sistema, facilitando manutenção e evolução.

---

## Benefícios da Vertical Slice Architecture

Ao adotar a Vertical Slice Architecture, o sistema passa a apresentar:

- organização centrada em funcionalidade;
- menor acoplamento entre features;
- maior clareza do fluxo de negócio;
- facilidade de testes;
- maior velocidade de entrega.

---

## Considerações finais

A Vertical Slice Architecture representa uma mudança de mentalidade: sair de uma visão técnica centrada em camadas e adotar uma organização orientada ao **valor de negócio**.

Combinada com CQRS, essa abordagem se mostra especialmente eficaz em **APIs modernas, microsserviços e sistemas que demandam rápida evolução**, permitindo que cada funcionalidade seja tratada como uma unidade independente e bem definida.

---

<img width="259" height="206" alt="image" src="https://github.com/user-attachments/assets/8e60f54e-3ba5-40a2-acca-d70550aa1fce" />

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/43a2eb00-5e35-4aff-8aeb-d83be8cc65a4" />


