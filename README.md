# BibleDigPAM
Repositório Elaboração Api.

API Documentation - Abibliadigital
This API allows you to retrieve information about the books, chapters, verses and versions of the Bible. It also allows user authentication to create, retrieve, update and delete user accounts.

Base URL
https://www.abibliadigital.com.br/api/
Authentication
There is no need for authentication to use the API, but requests will be limited to 20 per hour. For unlimited requests, you can create an account.
Books
Returns a list of all the 66 books of the Bible.
GET /books
Retrieves a list of all books of the Bible.
Response
css
Copy code
[  {    "abbrev": {"pt":"gn","en":"gn"},    "author":"Moisés",    "chapters":50,    "group":"Pentateuco",    "name":"Gênesis",    "testament":"VT"  },  ...]
GET /books/:abbrev
Retrieves details of a specific book.
Response
json
Copy code
{
  "abbrev": {"pt":"mt","en":"mt"},
  "author":"Mateus",
  "chapters":28,
  "comment":"",
  "group":"Evangelhos",
  "name":"Mateus",
  "testament":"NT"
}
Verses
Returns information about verses and chapters of the Bible.
GET /verses/:version/:abbrev/:chapter
Retrieves all verses and details of a chapter.
Response
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
GET /verses/:version/:abbrev/:chapter/:number
Retrieves a specific verse from a chapter.
Response
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
GET /verses/random/:version/:abbrev/:chapter
Retrieves a random verse from a specific chapter.
GET /verses/random/:version/:abbrev
Retrieves a random verse from a specific book.
GET /verses/search/:version/:query
Searches for verses containing a specific word.
Versions
Returns information about Bible versions.
GET /versions
Retrieves all Bible versions and the number of verses.
Users
Allows user authentication and account management.
POST /users
Creates a new user account.
Request
css
Copy code
Header: 
{ 
  'Accept': 'application/json',
  'Content-Type': 'application/json'
}

Body:
{
  "name": "Name",
  "email
