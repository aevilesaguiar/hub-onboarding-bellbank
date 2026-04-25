# Arquitetura Hexagonal: do conceito básico à compreensão do modelo

Quando começamos a estudar arquitetura de software, é comum encontrarmos sistemas organizados em **camadas tradicionais**, como apresentação, negócio e dados. Esse modelo foi amplamente utilizado por muitos anos, mas à medida que os sistemas evoluíram e se tornaram mais complexos, suas limitações ficaram evidentes.

É nesse contexto que surgem arquiteturas modernas, entre elas a **Arquitetura Hexagonal**, proposta por **Alistair Cockburn** como uma alternativa mais flexível, sustentável e alinhada aos princípios fundamentais da engenharia de software. Para compreendê-la corretamente, porém, é essencial entender primeiro um conceito central que sustenta toda a proposta: o **Separation of Concerns (SoC)**.

---

## Separation of Concerns (SoC)

O **Separation of Concerns (SoC)**, ou **Separação de Conceitos**, é um princípio da engenharia de software que defende a **modularização de um sistema**, garantindo que **cada parte esteja focada em resolver apenas um tipo de problema**.

Em um sistema de software, diferentes preocupações coexistem, como:
- regras de negócio;
- apresentação e interface com o usuário;
- persistência de dados;
- integrações externas;
- infraestrutura, frameworks e bibliotecas.

O SoC propõe que essas preocupações sejam **separadas em áreas, seções ou módulos bem definidos**, evitando que responsabilidades diferentes sejam misturadas em um mesmo componente. Quando essa separação não existe, mudanças simples passam a gerar efeitos colaterais imprevisíveis, dificultando a manutenção, os testes e a evolução do sistema.

Esse princípio é especialmente relevante em **softwares de grande porte** ou em projetos desenvolvidos **em mais de uma linguagem de programação**, nos quais a complexidade exige uma organização clara e consistente.

---

## Um exemplo clássico de SoC: o MVC

Um exemplo amplamente conhecido da aplicação do Separation of Concerns é o padrão arquitetural **Model-View-Controller (MVC)**. Nesse padrão, as responsabilidades do sistema são claramente divididas:

- **View**: responsável pela apresentação dos dados e pela interação com o usuário. Seu foco está exclusivamente na interface.
- **Model**: responsável pelo processamento dos dados e pelas regras de negócio. Representa a lógica de domínio e o estado da aplicação.
- **Controller**: atua como intermediário, recebendo as entradas do usuário e coordenando a comunicação entre View e Model.

Esse padrão demonstra como a separação de responsabilidades contribui para a criação de uma arquitetura **flexível, manutenível e sustentável**. A Arquitetura Hexagonal leva essa mesma ideia adiante, aplicando o SoC de forma mais profunda, especialmente no que diz respeito à proteção da lógica de negócio.

---

## O problema das arquiteturas tradicionais em camadas

Em arquiteturas tradicionais, é comum que a lógica de negócio acabe **dependendo diretamente de tecnologias específicas**, como frameworks web, bancos de dados ou mecanismos de integração. Na prática, isso faz com que decisões técnicas influenciem diretamente o núcleo do sistema.

Esse acoplamento excessivo traz diversos problemas:
- dificuldade para realizar testes automatizados;
- alto custo de manutenção;
- baixa capacidade de adaptação a mudanças tecnológicas.

A Arquitetura Hexagonal surge como uma resposta direta a esse cenário.

---

## O que é a Arquitetura Hexagonal

A **Arquitetura Hexagonal** organiza a aplicação de forma que **toda a lógica de negócio fique isolada no centro do sistema**, enquanto tecnologias externas são tratadas como detalhes periféricos.

Seu objetivo principal é garantir:
- alta coesão;
- baixo acoplamento;
- independência de tecnologia;
- facilidade de manutenção;
- facilidade de testes automatizados.

---

## Estrutura conceitual da Arquitetura Hexagonal

A arquitetura hexagonal se baseia em três conceitos centrais.

---

### O centro do hexágono: domínio e aplicação

No centro da arquitetura está a **aplicação**, também conhecida como **core** ou **domínio**. Essa camada representa o verdadeiro motivo da existência do software e concentra:
- regras de negócio;
- casos de uso;
- entidades e políticas de domínio.

É importante destacar que essa camada **não corresponde à camada “Application” da arquitetura em camadas tradicional**. Aqui, ela representa o **coração do sistema**, e não uma camada intermediária entre apresentação e dados.

O domínio não depende de:
- banco de dados;
- frameworks;
- APIs;
- interfaces gráficas.

---

### Portas (Ports)

As **portas** são interfaces que definem **como a aplicação se comunica com o mundo externo**. Elas representam contratos, não implementações.

Existem dois tipos principais:
- **Portas de entrada (Inbound Ports)**: representam as operações que o sistema oferece, normalmente associadas aos casos de uso.
- **Portas de saída (Outbound Ports)**: representam dependências que o domínio precisa consumir, como persistência de dados ou integrações externas.

Essas portas são **definidas pelo próprio domínio**, reforçando o princípio da inversão de dependência.

---

### Adaptadores (Adapters)

Os **adaptadores** são responsáveis por **implementar as portas**, conectando o domínio às tecnologias externas.

Exemplos de adaptadores incluem:
- controllers REST;
- interfaces web ou mobile;
- repositórios de banco de dados;
- integrações com APIs ou mensageria.

Eles funcionam como intermediários, traduzindo chamadas externas para o formato compreendido pelo domínio, sem que o domínio conheça os detalhes técnicos envolvidos.

---

## Por que o nome “hexagonal”?

Apesar do nome, a Arquitetura Hexagonal **não está limitada ao número seis**. O hexágono é apenas uma representação geométrica que simboliza que o sistema pode possuir **diversos pontos de comunicação com o mundo externo**.

Cada face representa um motivo diferente pelo qual o sistema se comunica com usuários, sistemas ou tecnologias. Isso reforça a ideia de que o domínio é único, mas pode ser exposto por múltiplas interfaces, como aplicações web, mobile ou APIs, sem que sua lógica central precise mudar.

Em 2005, Alistair Cockburn tentou renomear essa arquitetura para **“Arquitetura baseada em Portas e Adaptadores”**, por considerar o nome mais explicativo. Ainda assim, o termo **Arquitetura Hexagonal** acabou se consolidando.

---

## Testabilidade como motivador da Arquitetura Hexagonal

Um dos grandes benefícios da Arquitetura Hexagonal é a **facilidade para testes automatizados**. Como a lógica de negócio está isolada no centro do sistema, ela pode ser testada sem dependência de banco de dados, frameworks ou infraestrutura externa.

Isso permite uma aplicação mais eficaz da **pirâmide de testes**, com forte foco em testes unitários, seguidos por testes de integração e testes end-to-end.

---

## Conclusão

A Arquitetura Hexagonal vai muito além de uma simples organização de código. Ela é uma consequência direta da aplicação rigorosa do **Separation of Concerns**, com o objetivo de proteger aquilo que realmente importa: as regras de negócio.

Ao tratar tecnologias como detalhes externos e manter o domínio no centro da solução, esse modelo contribui para a construção de sistemas mais robustos, testáveis e preparados para evoluir ao longo do tempo.



## Infógrafo
<img width="500" height="331" alt="image" src="https://github.com/user-attachments/assets/b6ba1a40-ac7f-410d-bc14-e6974cc5bb95" />

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c0abb35a-e440-427a-9865-d1a822c1386a" />
