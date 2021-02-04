# API Rest - Integração entre as plataformas Pipedrive e Bling utilizando Node.js

Desafio técnico proposto pela [LinkApi](https://linkapi.gupy.io/).

## Requisitos:

- [x] Criar contas testes nas plataformas Pipedrive e Bling.

- [x] Criar uma integração entre as plataformas Pipedrive e Bling. (A integração deve buscar as oportunidades com status igual a ganho no Pipedrive, depois inseri-las como pedido no Bling).

- [x] Criar banco de dados mongo, existem serviços como MongoDB Atlas para criar de graça

- [x] Criar uma collection no banco de dados MongoDB agregando as oportunidades inseridas no Bling por dia e valor total.

- [x] Criar endpoint para trazer os dados consolidados da collection do MongoDB.

## Setup

### Contas

É necessário criar uma conta nas plataformas Pipedrive e Bling.

- [Pipedrive](https://www.pipedrive.com/pt)
- [Bling](https://www.bling.com.br/home)

### Dependências

- [Node.js v12.20.1](https://nodejs.org/en/blog/release/v12.20.1/)
- [yarn](https://yarnpkg.com/)

Clone este repositório e na pasta raiz execute o seguinte comando:

`yarn install`

### Variáveis de ambiente

Crie um arquivo .env e preencha com suas credenciais. Use o arquivo .env.example como referência.

### Executar

Pronto, basta executar o seguinte comando para iniciar o serviço:

`yarn start` ou `yarn dev`

## Endpoints

### GET /deals

Endpoint opcional que retorna uma lista de objetos json com status igual a ganho.

#### Request

`curl -X GET "http://localhost:3000/deals"`

##### Success

###### HTTP Status

200

##### Body

Exemplo de resposta com os principais atributos.

```json
[
    {
        ...
        "id": "id da oportunidade",
        "person_name": "nome do cliente",
        "title": "título da oportunidade",
        "value": "valor da oportunidade",
        "currency": "moeda",
        "wonDate": "data que a oportunidade mudou o status para ganho"
        ...
    }
]
```

##### Internal Error

###### HTTP Status

500

##### Body

Internal Error.

### GET /orders

Endpoint que retorna uma lista de objetos json com os dados agrupados por dia da ordem pedido e o seu valor total.

#### Request

`curl -X GET "http://localhost:3000/orders"`

##### Success

###### HTTP Status

200

##### Body

```json
[
    {
        "date": "2021-02-03",
        "totalAmount": "10000"
    }
]
```

##### Internal Error

###### HTTP Status

500

##### Body

Internal Error.