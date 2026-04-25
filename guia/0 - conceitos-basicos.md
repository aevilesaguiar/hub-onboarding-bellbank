# Entendendo a documentação: Controllers, Services, Repositories e Models

Em muitos sistemas (principalmente arquiteturas tradicionais em camadas), o código é organizado **por tipo técnico**. É daí que surgem pastas e conceitos como:

*   Controllers
*   Services
*   Repositories
*   Models

Vamos entender **o que cada um representa**, **qual problema resolve** e **onde costuma aparecer na arquitetura**.

***

## 1️⃣ Controller

### O que é

O **Controller** é o ponto de **entrada do sistema**.

Ele recebe uma requisição externa, por exemplo:

*   uma chamada HTTP (API),
*   uma ação do usuário,
*   um request vindo do frontend.

### O que ele faz

*   Recebe dados de entrada
*   Valida o básico (formato, campos obrigatórios)
*   Encaminha a requisição para outra parte do sistema

### O que ele **não deveria fazer**

*   Não deveria conter regra de negócio
*   Não deveria acessar banco de dados diretamente

### Em documentação, leia assim:

> “Controller = quem recebe pedidos de fora e encaminha”

***

## 2️⃣ Service

### O que é

O **Service** normalmente representa a **lógica de negócio** ou a **orquestração de regras**.

É comum encontrar Services como:

*   `OrderService`
*   `PaymentService`
*   `UserService`

### O que ele faz

*   Aplica regras de negócio
*   Coordena chamadas entre partes do sistema
*   Decide *o que* deve acontecer

### Problema comum em documentações

Em arquiteturas antigas, o Service acaba virando um **“Deus Service”**, com:

*   regra de negócio,
*   acesso a banco,
*   integração,
*   validação,
    tudo misturado.

### Em documentação, leia assim:

> “Service = onde normalmente vivem as regras do sistema”

***

## 3️⃣ Repository

### O que é

O **Repository** é responsável por **acessar dados**.

Ele faz a ponte entre o sistema e o banco de dados.

### O que ele faz

*   Buscar dados
*   Salvar dados
*   Atualizar dados
*   Remover dados

Sempre lidando com **persistência**.

### O que ele **não deveria fazer**

*   Não deveria conter regra de negócio
*   Não deveria decidir fluxos

### Em documentação, leia assim:

> “Repository = fala com o banco de dados”

***

## 4️⃣ Model

Esse é um termo que **muda de significado dependendo da arquitetura**, por isso gera confusão.

### Em MVC tradicional

O **Model** representa:

*   dados
*   estado
*   às vezes regras simples

Exemplo:

*   `User`
*   `Order`
*   `Contract`

### Em arquiteturas mais modernas

O termo “Model” pode significar:

*   entidade de domínio
*   DTO
*   objeto de persistência

Por isso, sempre vale observar **o contexto**.

### Em documentação, leia assim:

> “Model = representação de dados ou conceito do domínio”

***

# Como tudo isso se encaixa (modelo tradicional em camadas)

Em uma arquitetura **em camadas**, o fluxo costuma ser:

```text
Controller
   ↓
Service
   ↓
Repository
   ↓
Banco de Dados
```

Cada camada chama a próxima.

✅ Fácil de entender  
❌ Difícil de manter quando cresce  
❌ Forte acoplamento

***

# Por que isso começa a dar problema?

Esse modelo organiza o código:

*   ✅ por tipo técnico
*   ❌ mas não por funcionalidade real

Uma simples funcionalidade pode estar espalhada em:

*   1 controller
*   1 service
*   vários repositories
*   vários models

👉 É isso que a **Vertical Slice critica**  
👉 É isso que **Hexagonal, Onion e Clean tentam resolver de formas diferentes**

***

# Outros conceitos que você vai ver na documentação

### Use Case (Caso de Uso)

*   Representa **uma ação que o sistema executa**
*   Ex: `CriarPedido`, `BuscarContrato`

📌 Em Clean Architecture, ele substitui o “Service”.

***

### DTO (Data Transfer Object)

*   Objeto usado **só para trafegar dados**
*   Não tem regra de negócio

📌 Muito comum entre Controller ↔ Service.

***

### Adapter

*   Classe que **adapta** o mundo externo para o interno
*   Muito usada em Hexagonal e Clean

📌 Ex: adaptar uma API externa para o formato do domínio.

***

### Handler

*   Classe que executa **um caso específico**
*   Muito comum com Vertical Slice + CQRS

📌 Ex: `CreateOrderHandler`.

***

# Tradução mental rápida (guarda isso)

| Termo      | Pense assim            |
| ---------- | ---------------------- |
| Controller | Porta de entrada       |
| Service    | Regra / orquestração   |
| Repository | Acesso a dados         |
| Model      | Representação de dados |
| Use Case   | O que o sistema faz    |
| Adapter    | Ponte entre mundos     |
| Handler    | Executa uma ação       |

***

## Conclusão importante

Quando você lê uma documentação e vê:

*   Controllers
*   Services
*   Repositories
*   Models

👉 **não pense em código**, pense em **responsabilidades**.

Arquitetura não é sobre classes —  
é sobre **quem faz o quê e por quê**.

***


Esse entendimento é o que te faz **ler arquitetura com segurança**.

O que é básico para entender Arquitetura, APIs e REST
1️⃣ O que é uma API (Application Programming Interface)
Uma API é um contrato de comunicação entre sistemas.
Em termos simples:

um sistema oferece funcionalidades
outro sistema consome essas funcionalidades
a API define como pedir e como responder

Uma API:

não é a interface visual
não é o banco de dados
é o meio de comunicação entre sistemas [redhat.com]

Na documentação, leia assim:

“API = como sistemas conversam entre si”


2️⃣ O que é REST
REST não é tecnologia nem framework.
REST é um estilo arquitetural, criado por Roy Fielding, que define boas práticas para construir APIs escaláveis e simples.
Uma API que segue REST é chamada de RESTful. [ibm.com]
REST se baseia em:

uso do protocolo HTTP
comunicação sem estado (stateless)
acesso a recursos (e não ações)


3️⃣ Recursos (conceito chave em REST)
Em REST, tudo é um recurso:

usuário
pedido
contrato
produto

Cada recurso é acessado por uma URL (endpoint), por exemplo:
/users
/orders
/contracts

Na documentação:

“Quando você vê URLs bem definidas, está vendo recursos REST” [cloud.google.com]


4️⃣ Métodos HTTP (verbo importa)
Os métodos HTTP indicam o que você quer fazer com um recurso:

























MétodoSignificadoGETBuscarPOSTCriarPUTAtualizarDELETERemover
Exemplo:

GET /orders → buscar pedidos
POST /orders → criar pedido [programado...brasil.com]


5️⃣ Request e Response
Toda API REST funciona no modelo:
Request  →  Processamento  →  Response


Request: pedido do cliente
Response: resposta do servidor

Respostas vêm com:

código de status HTTP
dados (normalmente em JSON) [cloud.google.com]


6️⃣ Status HTTP (linguagem da resposta)
Os status HTTP indicam o resultado da operação:





























CódigoSignificado200Sucesso201Criado400Erro do cliente404Não encontrado500Erro do servidor
Na documentação:

“Status HTTP explicam o resultado sem ler o corpo” [redhat.com]


7️⃣ JSON (formato básico de dados)
JSON é o formato mais comum de обмен de dados em APIs REST.
Exemplo simples:
JSON{  "id": 1,  "name": "Pedido",  "status": "Criado"}Mostrar mais linhas
JSON é:

leve
legível
independente de linguagem [cloud.google.com]


8️⃣ Camadas básicas de um sistema (visão geral)
Quase todo sistema moderno tem, conceitualmente:

Frontend → interface com o usuário
Backend → regras e processamento
Banco de dados → persistência

As arquiteturas que você estudou organizam isso de formas diferentes.

9️⃣ Conceitos que você já viu (tradução rápida)





































ConceitoO que significaControllerPorta de entrada da APIService / Use CaseRegras e fluxoRepositoryAcesso à base de dadosDomain / CoreRegras do negócioAdapterPonte com tecnologiaEndpointURL da APIStatelessCada request é independente

🔟 Como tudo se conecta com Arquitetura
Agora o ponto mais importante 👇
Arquitetura define:

onde cada coisa deve ficar
quem pode depender de quem
como sistemas conversam

REST e APIs são meios de comunicação.
Arquitetura define como organizar o software por dentro.

✅ Resumo mental para você guardar

API = comunicação
REST = estilo dessa comunicação
Arquitetura = organização interna do sistema
