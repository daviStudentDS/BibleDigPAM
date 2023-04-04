# BibleDigPAM
Repositório Elaboração Api.

API Documentation - Abibliadigital
This is an API documentation for a digital Bible platform. The API provides various endpoints to access books, chapters, and verses of the Bible. There are endpoints to retrieve a list of all Bible books, book details, chapters, verses, and search by keyword. Additionally, the API supports creating, retrieving, updating, and deleting user accounts for the platform.

The API endpoints are accessible through HTTP GET and POST requests. The endpoint URL and required parameters are listed for each request. Some endpoints require authentication, which is achieved using an access token obtained by creating a user account. The API provides both authenticated and non-authenticated access to users.

The API endpoints include:

Get Books - returns a list of all the Bible books available in the platform, including abbreviations, authors, and number of chapters.
Get Book - returns details of a specific Bible book, including the book name, author, number of chapters, etc.
Get Chapter - returns all verses and details of a specific chapter, including the book, chapter number, and verse text.
Get Verse - returns a specific verse of a chapter, including the book, chapter, verse number, and verse text.
Get Random Verse - returns a random verse from a specific chapter.
Get Random Verse Book - returns a random verse from a specific book.
Search by word - returns verses containing a specific keyword.
Get Versions - returns all Bible versions available in the platform.
Create User - creates a new user account for the platform.
Get User - returns details of a specific user account.
Get User Stats - returns statistics for a specific user account, such as the last login date and the number of requests made per month.
Update Token - updates the access token of a specific user account.
Delete User - deletes a specific user account from the platform.



reidadunk15@gmail.com
continue o texto acima seguindo as mesmas instruções
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




reidadunk15@gmail.com
Continue o texto a seguir: Além do endpoint anterior, a API também oferece o endpoint Get Chapter, que retorna todos os versículos de um capítulo específico de um livro da Bíblia em uma determinada versão.

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
