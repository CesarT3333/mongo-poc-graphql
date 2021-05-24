# Criar um arquivo com o nome `.env` na raiz do diretório com as seguintes variáveis:

```
MONGO_ROOT_USERNAME=root
MONGO_ROOT_PASSWORD=example
```

---

## Para rodar:

```sh
docker-compose -f docker-compose up
```

---

## Mongo Express

Disponível em:  `http://localhost:8081`

---

## Dados gerados a partir de um ![gerador de dados](https://www.json-generator.com/)

```JSON
[
  '{{repeat(10000)}}',
  {
    "identificador": '{{guid()}}',
    "identificadorUnidade": '{{guid()}}',
    "origem": function (tags) {
      var fruits = ['norte', 'sul', 'leste', 'oeste'];
      return fruits[tags.integer(0, fruits.length - 1)];
    },
    "unidade": function (tags) {
      var fruits = ['alfa', 'bravo', 'golf'];
      return fruits[tags.integer(0, fruits.length - 1)];
    },
    "dados": {
      "taxa": '{{floating(1000, 4000, 2, "000,00")}}',
      "valor": '{{floating(1000, 4000, 2, "000,00")}}',
      "prazo": '{{integer(100, 10000)}} d',
      "data_aquisicao": '{{date(new Date(2014, 0, 1), new Date(), "dd/MM/YYYY")}}'
    }
  }
]
```


