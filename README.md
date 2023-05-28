# Mongo

## Introdução

O MongoDB é um banco de dados NoSQL (Não Relacional) orientado a documentos, projetado para armazenar, recuperar e gerenciar dados de maneira flexível e escalável. Ao contrário dos bancos de dados relacionais tradicionais, que usam tabelas e linhas para representar os dados, o MongoDB armazena os dados em formato de documentos BSON (Binary JSON) dentro de coleções.

## Primeiros passos

Caso deseje testar os comandos e não possua o mongo instalado em sua máquina faça o download [aqui](https://www.mongodb.com/docs/manual/installation/).

Mas caso queira testar o mongo sem baixá-lo em sua máquina, experimente utilizar um container, para mais informações veja este [repositório](https://github.com/Guilherme-07062002/MongoContainer.git).

Depois que tiver acesso ao mongo em seu computador você poderá realizar comandos por meio de linha de comando, escreva isso no terminal:

```bash
mongo
```

E o ambiente de linha de comando do mongo estará disponivel.

Vamos começar criando um database:

```bash
use exemplo
```

Este irá dar uma 'switch' para um novo database chamado exemplo.

Para listas as bases de dados disponiveis, digite:

```bash
show dbs
```

No entanto você irá perceber que o db recém criado 'exemplo', não é exibido, isso porque não inserimos nada nele ainda.

No mongodb, diferente do SQL, não existem tabelas para o armazenamento de dados, existem **collections**.

### Inserindo dados

Após o comando use 'exemplo', ele é o banco de dados atual, podemos acessá-lo por meio do 'db.[comando]', no exemplo abaixo criaremos na base de dados exemplo uma collection pessoas:

```mongo
db.pessoas.insertOne()
```

Dentro do parâmetro do método informamos um **document**, que é o dado que desejamos inserir.

```mongo
db.pessoas.insertOne({nome: "Pessoa1", idade: 20, email: "pessoa1@email.com"})
```

Conforme podemos observar acima a estrutura de um document é muito semelhante a um objeto javascript, e a própria forma que chamamos os métodos remetem muito ao paradigma de orientação a objetos.

Esta será a saída do comando insertOne:

![print1](imgs-readme/print1.png)

Podemos ver que ele cria um *ObjectId*, que fazendo uma comparação com SQL seria o identificador do seu documento, então mesmo que dois documentos possuam os mesmos dados ou sejam inseridos ao mesmo tempo eles terão identificadores diferentes.
