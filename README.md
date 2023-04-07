# BibleDigital_Davi_E_Maurício
Repositório Elaboração 

URL documetação da API: https://github.com/marciovsena/abibliadigital/blob/master/DOCUMENTATION.md

<a href="https://imgbb.com/"><img src="https://i.ibb.co/bXLx4sF/jesus-cristo.jpg" alt="jesus-cristo" border="0" display="flex"></a>



Esta é uma documentação da API para uma plataforma de Bíblia digital. A API fornece vários endpoints para acessar livros, capítulos e versículos da Bíblia. Existem endpoints para recuperar uma lista de todos os livros da Bíblia, detalhes do livro, capítulos, versículos e pesquisa por palavra-chave. Além disso, a API suporta a criação, recuperação, atualização e exclusão de contas de usuário para a plataforma.

Os endpoints da API são acessíveis por meio de solicitações HTTP GET e POST. A URL do endpoint e os parâmetros necessários são listados para cada solicitação. Alguns endpoints exigem autenticação, que é realizada usando um token de acesso obtido ao criar uma conta de usuário. A API fornece acesso autenticado e não autenticado aos usuários.

Os endpoints da API incluem:

- *Get Books* - retorna uma lista de todos os livros da Bíblia disponíveis na plataforma, incluindo abreviações, autores e número de capítulos.
- *Get Book * - retorna detalhes de um livro específico da Bíblia, incluindo o nome do livro, autor, número de capítulos, etc.
- *Get Chapter* - retorna todos os versículos e detalhes de um capítulo específico, incluindo o livro, número do capítulo e texto do versículo.
- *Get Verse* - retorna um versículo específico de um capítulo, incluindo o livro, capítulo, número do versículo e texto do versículo.
- *Get Random Verse* - retorna um versículo aleatório de um capítulo específico.
- *Get Random Verse Book* - retorna um versículo aleatório de um livro específico.
- *Search by word* - retorna versículos contendo uma palavra-chave específica.
- *Get VersionS* - retorna todas as versões da Bíblia disponíveis na plataforma.
- *Create User* - cria uma nova conta de usuário para a plataforma.
- *Get User* - retorna detalhes de uma conta de usuário específica.
- *Get User Stats* - retorna estatísticas para uma conta de usuário específica, como a data do último login e o número de solicitações feitas por mês.
- *Update Token* - atualiza o token de acesso de uma conta de usuário específica.
- *Delete User* - exclui uma conta de usuário específica da plataforma.

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


- API Usuários para Abibliadigital:

Esta API permite que os usuários criem, recuperem, atualizem e excluam suas contas. O projeto é de código aberto e a autenticação é usada apenas para rastrear o uso e enviar emails de atualização.

Para criar um usuário, envie uma solicitação POST para https://www.abibliadigital.com.br/api/users com um corpo JSON incluindo um nome, email, senha (mínimo de 6 dígitos) e se o usuário deseja receber emails de atualização. A resposta incluirá o nome, email e um token que não expira.

Para recuperar informações do usuário, envie uma solicitação GET para https://www.abibliadigital.com.br/api/users/:email com um token de autenticação. A resposta incluirá o nome, email, token, se eles desejam receber emails de atualização e a data do último login.

Para recuperar estatísticas do usuário, envie uma solicitação GET para https://www.abibliadigital.com.br/api/users/stats com um token de autenticação. A resposta incluirá a data do último login do usuário e um array de solicitações por mês com um intervalo e total.

Para atualizar o token do usuário, envie uma solicitação PUT para https://www.abibliadigital.com.br/api/users/token com um corpo JSON incluindo o email e senha do usuário. A resposta incluirá o nome, email e um novo token.

Para excluir um usuário, envie uma solicitação DELETE para https://www.abibliadigital.com.br/api/users com um token de autenticação e um corpo JSON incluindo o email e senha do usuário. A resposta confirmará que o usuário foi excluído com sucesso.

Para reenviar a senha do usuário, envie uma solicitação POST para https://www.abibliadigital.com.br/api/users/password/:email com o email do usuário como um parâmetro. A resposta confirmará que uma nova senha foi enviada para o email do usuário.


- Requisições GET - Todas as requisições do período

Endpoint: GET https://www.abibliadigital.com.br/api/requests/:range (mês, semana, dia)
Autenticado: Sim
Resposta:

[
{
"url": "/api/verses/nvi/1co/9/8",
"date": "2020-01-17T21:03:50.996Z"
},
{
"url": "/api/books",
"date": "2020-01-17T20:13:19.078Z"
}
]

Obter o número de requisições - Número de requisições para o período

Endpoint: GET https://www.abibliadigital.com.br/api/requests/amount/:range (mês, semana, dia)
Autenticado: Sim
Resposta:

{
"total": 3,
"requests": [
{
"_id": "/api/books/",
"count": 2
},
{
"_id": "/api/verses/nvi/sl/23/",
"count": 1
}
]
