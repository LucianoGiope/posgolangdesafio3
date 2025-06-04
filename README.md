# TERCEIRO desafio proposto pelo curso.

# DESAFIO DO CLEAN ARCHITECTURE

# Texto descritivo do desafio

Olá devs!
Agora é a hora de botar a mão na massa. Para este desafio, você precisará criar o usecase de listagem das orders.
Esta listagem precisa ser feita com:
- Endpoint REST (GET /order)
- Service ListOrders com GRPC
- Query ListOrders GraphQL
Não esqueça de criar as migrações necessárias e o arquivo api.http com a request para criar e listar as orders.

Para a criação do banco de dados, utilize o Docker (Dockerfile / docker-compose.yaml), com isso ao rodar o comando docker compose up tudo deverá subir, preparando o banco de dados.
Inclua um README.md com os passos a serem executados no desafio e a porta em que a aplicação deverá responder em cada serviço.


### BUILDAR A IMAGEM DO DOCKER

> docker-compose up --build -d

### EXECUTAR NO MÉTODO REST

Usar as urls do http que estão na pasta api.

- CreateOrder
- ListOrders

### EXECUTAR NO MÉTODO GRPC

- OrderService/CreateOrder
{"id": "aaaaaaaaa","price": 5.99,"tax": 3}

- OrderService/ListOrders
{}

### EXECUTAR NO MÉTODO GraphQL

`http://localhost:8080/`

- CreateOrder
mutation createOrder {
  createOrder(input: {Id: "graphql1", Price:250.99, Tax:3.75}) {
    Id
    Price
    Tax
    FinalPrice
  }
}

- ListOrders
query listOrders {
  listOrders{
    Id
    Price
    Tax
    FinalPrice
  }
}

### AVALIAR AS MENSAGEM NO HABBITMQ
`http://localhost:15672/`