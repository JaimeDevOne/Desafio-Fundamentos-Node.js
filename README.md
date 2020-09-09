![68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f676f6c64656e2d77696e642f626f6f7463616d702d676f737461636b2f6865616465722d6465736166696f732e706e67](https://user-images.githubusercontent.com/59901617/84070940-4e800e80-a9a3-11ea-87ae-7f60234e9493.png)

# Desafio-Fundamentos-Node.Js
Desafio-Fundamentos-Node.Js / GoStack 11

<h3> 🚀 Sobre o desafio </h3>

Este desafio tem a intenção de criar uma aplicação para continuar a treinar o que eu aprendi até agora com **Node.js** já usando **TypeScript**, utilizando o conceito de models, repositories e services!

### Funcionalidades da aplicação

# Rotas da aplicação

<b>```✔ POST / Transactions```</b>: A rota deve receber ```title```, ```value``` e ```type``` dentro do corpo da requisição, sendo ```type``` o tipo da transação, que deve ser ```income``` para entradas(depósitos) e ```outcome``` para saídas(retiradas). Ao cadastrar uma nova transação, ela deve ser armazenada dentro de um objeto com a seguinte formato:
```
{ 
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income"
}
```

<b>```✔ GET / Transactions```</b>: Essa rota deve retornar uma listagem com todas as transações cadastradas até agora, junto com o valor de soma de entradas, retiradas e total de crédito. Essa rota deve retornar um objeto com o formato a seguir:
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
<b>Detalhe</b>: Dentro de balance, o **income** é a soma de todos os valores das transações com ```type``` income. O **outcome** é a soma de todos os valores das transações com ```type``` outcome, e o total é valor de ```income - outcome```. Para fazer a soma dos valores, foi utilizado a função <a href="https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce" target="blank"> reduce</a> para agrupar as transações pela propriedade ```type```, assim foi possível conseguir somar todos os valores com facilidade e obter o retorno do ```balance```.

# Especificação dos testes

Em cada teste, tem uma breve descrição no que a aplicação deve cumprir para que o teste passe.

Para essse desafio temos os seguintes testes:

<ul>
  <li><p><strong><code>Should be able to creat a new transaction</code></strong>: Para que esse teste passe, a aplicação deve permitir que uma transação seja criada, e retorne um <b>json</b> com a transação criada.</P></li>
</ul>

<ul>
  <li><p><strong><code>Should be able to list the transactions</code></strong>:Para que esse teste passe, a aplicação deve permitir que seja retornado um objeto contendo todas as trasnsações junto ao balanço de <b>income</b>, <b>outcome</b> e total das transações que foram criadas até o momento.</P></li>
</ul>

<ul>
  <li><p><strong><code>Should not able to creat outcome transaction without a valid balance</code></strong>: Para que esse teste passe, a aplicação não deve permitir que uma transação do tipo <code>outcome</code> extrapole o valor total que o usuário tem em caixa, retornando uma resposta com código HTTP 400 e uma mensagem de erro no seguinte formato: <code>{error: string}</code>.</P></li>
</ul>

🤷‍♂️Caso tenha alguma dúvida quanto ao que são os testes e como interpretá-los, dé uma olhada em <strong> <a href="https://github.com/Rocketseat/bootcamp-gostack-desafios/tree/master/faq-desafios">neste FAQ 💜🚀</a></strong>.

<h2>
<g-emoji class="g-emoji" alias="memo" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f4dd.png">📝</g-emoji> Licença
</h2>
<p> Esse projeto está sob a licença MIT. </p>
