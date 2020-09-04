![68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f676f6c64656e2d77696e642f626f6f7463616d702d676f737461636b2f6865616465722d6465736166696f732e706e67](https://user-images.githubusercontent.com/59901617/84070940-4e800e80-a9a3-11ea-87ae-7f60234e9493.png)

# Desafio-Fundamentos-Node.Js
Desafio-Fundamentos-Node.Js / GoStack 11

<h3> 🚀 Sobre o desafio </h3>

Este desafio tem a intenção de criar uma aplicação para continuar a treinar o que eu aprendi até agora com **Node.js** já usando **TypeScript**, utilizando o conceito de models, repositories e services!

### Funcionalidades da aplicação

# Rotas da aplicação

<b>```✔ POST / Transactions```</b>: A rota deve receber ```title```, ```value``` e ```type``` dentro do corpo da requisição, sendo ```type``` o tipo da transação, que deve ser ```income``` para entradas(depósitos) e ```outcome``` para saídas(retiradas). AO cadastrar uma nova transação, ela deve ser armazenada dentro de um objeto com a seguinte formato:
 
```
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

