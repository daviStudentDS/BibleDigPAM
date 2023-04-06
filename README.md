# BibleDigPAM
Repositório Elaboração 

<a href="https://imgbb.com/"><img src="https://i.ibb.co/bXLx4sF/jesus-cristo.jpg" alt="jesus-cristo" border="0" display="flex"></a>

<h1>VS</h1>

<a href="https://gifyu.com/image/SdNQD"><img src="https://s2.gifyu.com/images/diabo.gif" alt="diabo.gif" border="0" display="flex" /></a>


<h1></h1>

<iframe src="https://www.veed.io/embed/692b7016-168b-4ec6-9af3-1d9bdae1a82d" width="744" height="504" frameborder="0" title="Snaptik.app_7137976248919133446.mp4" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

Esta é uma documentação da API para uma plataforma de Bíblia digital. A API fornece vários endpoints para acessar livros, capítulos e versículos da Bíblia. Existem endpoints para recuperar uma lista de todos os livros da Bíblia, detalhes do livro, capítulos, versículos e pesquisa por palavra-chave. Além disso, a API suporta a criação, recuperação, atualização e exclusão de contas de usuário para a plataforma.

Os endpoints da API são acessíveis por meio de solicitações HTTP GET e POST. A URL do endpoint e os parâmetros necessários são listados para cada solicitação. Alguns endpoints exigem autenticação, que é realizada usando um token de acesso obtido ao criar uma conta de usuário. A API fornece acesso autenticado e não autenticado aos usuários.

Os endpoints da API incluem:

*Get Books* - retorna uma lista de todos os livros da Bíblia disponíveis na plataforma, incluindo abreviações, autores e número de capítulos.
*Get Book *- retorna detalhes de um livro específico da Bíblia, incluindo o nome do livro, autor, número de capítulos, etc.
*Get Chapter* - retorna todos os versículos e detalhes de um capítulo específico, incluindo o livro, número do capítulo e texto do versículo.
*Get Verse* - retorna um versículo específico de um capítulo, incluindo o livro, capítulo, número do versículo e texto do versículo.
Get Random Verse* - retorna um versículo aleatório de um capítulo específico.
*Get Random Verse Book* - retorna um versículo aleatório de um livro específico.
*Search by word* - retorna versículos contendo uma palavra-chave específica.
*Get Version*s - retorna todas as versões da Bíblia disponíveis na plataforma.
*Create User* - cria uma nova conta de usuário para a plataforma.
*Get User* - retorna detalhes de uma conta de usuário específica.
*Get User Stats* - retorna estatísticas para uma conta de usuário específica, como a data do último login e o número de solicitações feitas por mês.
*Update Token* - atualiza o token de acesso de uma conta de usuário específica.
*Delete User *- exclui uma conta de usuário específica da plataforma.

{
"book": {
"abbrev":{"pt":"gn","en":"gn"},
"name":"Gênesis",
"author":"Moisés",
"group":"Pentateuco",
"version":"nvi"
},
"chapter": {
"number":1,
"verses":31
},
"verses": [
{"number": 1,"text":"No princípio Deus criou os céus e a terra."},
{"number": 2,"text":"Era a terra sem forma e vazia; trevas cobriam a face do abismo, e o Espírito de Deus se movia sobre a face das águas."}
...
]
}


URL: https://www.abibliadigital.com.br/api/books

Parâmetros: Nenhum

Autenticação: Não autenticado

Resposta: Retorna um array de objetos JSON contendo informações sobre os livros da Bíblia disponíveis na plataforma:

json
Copy code
[
{
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi",
"chapters": 50
},
{
"abbrev": {"pt": "ex", "en": "ex"},
"name": "Êxodo",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi",
"chapters": 40
},
...
]

Exemplo de uso:

ruby
Copy code
GET https://www.abibliadigital.com.br/api/books
Retorna o seguinte array de objetos JSON:

json
Copy code
[
{
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi",
"chapters": 50
},
{
"abbrev": {"pt": "ex", "en": "ex"},
"name": "Êxodo",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi",
"chapters": 40
},
...
]

Método: GET

URL: https://www.abibliadigital.com.br/api/versions

Parâmetros: Nenhum

Autenticação: Não autenticado

Resposta: Retorna um array de strings contendo os nomes de todas as versões da Bíblia disponíveis na plataforma:

json
Copy code
[
"nvi",
"arc",
...
]

Exemplo de uso:

ruby
Copy code
GET https://www.abibliadigital.com.br/api/versions
Retorna o seguinte array de strings:

json
Copy code
[
"nvi",
"arc",
...
]

Método: GET

URL: https://www.abibliadigital.com.br/api/search/:versão/:palavra

Parâmetros:

versão: string (obrigatório) - a versão da Bíblia desejada, por exemplo "nvi", "arc", etc.
palavra: string (obrigatório) - a palavra-chave que se deseja buscar.

Autenticação: Não autenticado

Resposta: Retorna um array de objetos JSON contendo informações sobre os versículos que contêm a palavra-chave buscada:

json
Copy code
[
{
"book": {
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi"
},
"chapter": 1,
"number": 1,
"text": "No princípio Deus criou os céus e a terra."
},
{
"book": {
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author":

Get Verse - retorna um versículo específico de um capítulo

Este endpoint retorna um versículo específico de um capítulo da Bíblia em uma determinada versão e livro.

Método: GET

URL: https://www.abibliadigital.com.br/api/verses/:versão/:abreviação/:capítulo/:número

Parâmetros:

versão: string (obrigatório) - a versão da Bíblia desejada, por exemplo "nvi", "arc", etc.
abreviação: string (obrigatório) - a abreviação do livro da Bíblia, por exemplo "gn" para Gênesis, "ex" para Êxodo, etc.
capítulo: integer (obrigatório) - o número do capítulo desejado.
número: integer (obrigatório) - o número do versículo desejado.
Autenticação:

Não autenticado: limite de taxa de 20 solicitações por hora.
Autenticado: sem limite de taxa.
Resposta:
Retorna um objeto JSON contendo informações sobre o livro, capítulo e versículo especificado:

json
Copy code
{
  "book": {
    "abbrev":{"pt":"gn","en":"gn"},
    "name":"Gênesis",
    "author":"Moisés",
    "group":"Pentateuco",
    "version":"nvi"
  },
  "chapter": 1,
  "number": 1,
  "text": "No princípio Deus criou os céus e a terra."
}
Exemplo de uso:

ruby
Copy code
GET https://www.abibliadigital.com.br/api/verses/nvi/gn/1/1
Retorna o seguinte objeto JSON:

json
Copy code
{
  "book": {
    "abbrev":{"pt":"gn","en":"gn"},
    "name":"Gênesis",
    "author":"Moisés",
    "group":"Pentateuco",
    "version":"nvi"
  },
  "chapter": 1,
  "number": 1,
  "text": "No princípio Deus criou os céus e a terra."
}
  'Content-Type': 'application/json'
}

Body:
{
  "name": "Name",
  "email
  {
"book": {
"abbrev":{"pt":"gn","en":"gn"},
"name":"Gênesis",
"author":"Moisés",
"group":"Pentateuco",
"version":"nvi"
},
"chapter": {
"number":1,
"verses":31
},
"verses": [
{"number": 1,"text":"No princípio Deus criou os céus e a terra."},
{"number": 2,"text":"Era a terra sem forma e vazia; trevas cobriam a face do abismo, e o Espírito de Deus se movia sobre a face das águas."}
...
]
}

Get Verse - retorna um versículo específico de um capítulo

Este endpoint retorna um versículo específico de um capítulo da Bíblia em uma determinada versão e livro.

Método: GET

URL: https://www.abibliadigital.com.br/api/verses/:versão/:abreviação/:capítulo/:número

Parâmetros:

versão: string (obrigatório) - a versão da Bíblia desejada, por exemplo "nvi", "arc", etc.
abreviação: string (obrigatório) - a abreviação do livro da Bíblia, por exemplo "gn" para Gênesis, "ex" para Êxodo, etc.
capítulo: integer (obrigatório) - o número do capítulo desejado.
número: integer (obrigatório) - o número do versículo desejado.
Autenticação:

Não autenticado: limite de taxa de 20 solicitações por hora.
Autenticado: sem limite de taxa.
Resposta:
Retorna um objeto JSON contendo informações sobre o livro, capítulo e versículo especificado:

json
Copy code
{
  "book": {
    "abbrev":{"pt":"gn","en":"gn"},
    "name":"Gênesis",
    "author":"Moisés",
    "group":"Pentateuco",
    "version":"nvi"
  },
  "chapter": 1,
  "number": 1,
  "text": "No princípio Deus criou os céus e a terra."
}
Exemplo de uso:

ruby
Copy code
GET https://www.abibliadigital.com.br/api/verses/nvi/gn/1/1
Retorna o seguinte objeto JSON:

json
Copy code
{
  "book": {
    "abbrev":{"pt":"gn","en":"gn"},
    "name":"Gênesis",
    "author":"Moisés",
    "group":"Pentateuco",
    "version":"nvi"
  },
  "chapter": 1,
  "number": 1,
  "text": "No princípio Deus criou os céus e a terra."
}
Além do endpoint anterior, a API também oferece o endpoint Get Chapter, que retorna todos os versículos de um capítulo específico de um livro da Bíblia em uma determinada versão.

Get Chapter - retorna todos os versículos de um capítulo

Este endpoint retorna todos os versículos de um capítulo de um livro da Bíblia em uma determinada versão.

Método: GET

URL: https://www.abibliadigital.com.br/api/chapters/:versão/:abreviação/:capítulo

Parâmetros:

versão: string (obrigatório) - a versão da Bíblia desejada, por exemplo "nvi", "arc", etc.
abreviação: string (obrigatório) - a abreviação do livro da Bíblia, por exemplo "gn" para Gênesis, "ex" para Êxodo, etc.
capítulo: integer (obrigatório) - o número do capítulo desejado.
Autenticação:

Não autenticado: limite de taxa de 20 solicitações por hora.
Autenticado: sem limite de taxa.
Resposta:

Retorna um array de objetos JSON, onde cada objeto representa um versículo do capítulo especificado. Cada objeto contém informações sobre o livro, capítulo e número do versículo, além do texto do versículo em si.

Exemplo de resposta:

json
Copy code
[
{
"book": {
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi"
},
"chapter": 1,
"number": 1,
"text": "No princípio Deus criou os céus e a terra."
},
{
"book": {
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi"
},
"chapter": 1,
"number": 2,
"text": "Era a terra sem forma e vazia; trevas cobriam a face do abismo, e o Espírito de Deus se movia sobre a face das águas."
},
// mais versículos aqui...
]

O uso deste endpoint é semelhante ao do Get Verse, porém é necessário especificar apenas o número do capítulo e não do versículo. Por exemplo:

ruby
Copy code
GET https://www.abibliadigital.com.br/api/chapters/nvi/gn/1
Retorna todos os versículos do primeiro capítulo de Gênesis na versão NVI.

Além do endpoint anterior, a API também oferece o endpoint Get Chapter, que retorna todos os versículos de um capítulo específico de um livro da Bíblia em uma determinada versão.

Get Chapter - retorna todos os versículos de um capítulo

Este endpoint retorna todos os versículos de um capítulo de um livro da Bíblia em uma determinada versão.

Método: GET

URL: https://www.abibliadigital.com.br/api/chapters/:versão/:abreviação/:capítulo

Parâmetros:

versão: string (obrigatório) - a versão da Bíblia desejada, por exemplo "nvi", "arc", etc.
abreviação: string (obrigatório) - a abreviação do livro da Bíblia, por exemplo "gn" para Gênesis, "ex" para Êxodo, etc.
capítulo: integer (obrigatório) - o número do capítulo desejado.
Autenticação:

Não autenticado: limite de taxa de 20 solicitações por hora.
Autenticado: sem limite de taxa.
Resposta:

Retorna um array de objetos JSON, onde cada objeto representa um versículo do capítulo especificado. Cada objeto contém informações sobre o livro, capítulo e número do versículo, além do texto do versículo em si.

Exemplo de resposta:

json
Copy code
[
{
"book": {
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi"
},
"chapter": 1,
"number": 1,
"text": "No princípio Deus criou os céus e a terra."
},
{
"book": {
"abbrev": {"pt": "gn", "en": "gn"},
"name": "Gênesis",
"author": "Moisés",
"group": "Pentateuco",
"version": "nvi"
},
"chapter": 1,
"number": 2,
"text": "Era a terra sem forma e vazia; trevas cobriam a face do abismo, e o Espírito de Deus se movia sobre a face das águas."
},
// mais versículos aqui...
]

O uso deste endpoint é semelhante ao do Get Verse, porém é necessário especificar apenas o número do capítulo e não do versículo. Por exemplo:

ruby
Copy code
GET https://www.abibliadigital.com.br/api/chapters/nvi/gn/1
Retorna todos os versículos do primeiro capítulo de Gênesis na versão NVI.
