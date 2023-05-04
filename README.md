# Documentação da API BallDontLie
BallDontLie - API que fornece estatísticas de basquete sobre a NBA. Esta API é gratuita e aberta para uso público.

A API BallDontLie é uma API pública gratuita e aberta para uso público que fornece estatísticas de basquete da NBA. Com esta API, é possível obter informações sobre jogos, equipes, jogadores e estatísticas de jogadores em jogos específicos.

URL Base
O URL base para todas as solicitações é: https://www.balldontlie.io/api/v1/

Recursos
A API fornece quatro recursos principais: jogos (Games), equipes (Teams), jogadores (Players) e estatísticas (Stats). Cada recurso possui endpoints específicos para solicitações.

Jogos (Games)
O recurso Games fornece informações sobre os jogos da NBA. É possível filtrar por data (start_date e end_date), pela equipe da casa (home_team) e pela equipe visitante (visitor_team). Os endpoints para solicitações deste recurso são:

GET /games: Retorna uma lista de jogos.
GET /games/:id: Retorna um jogo específico pelo seu ID.
Equipes (Teams)
O recurso Teams fornece informações sobre as equipes da NBA. Os endpoints para solicitações deste recurso são:

GET /teams: Retorna uma lista de equipes.
GET /teams/:id: Retorna uma equipe específica pelo seu ID.
Jogadores (Players)
O recurso Players fornece informações sobre os jogadores da NBA. Os endpoints para solicitações deste recurso são:

GET /players: Retorna uma lista de jogadores.
GET /players/:id: Retorna um jogador específico pelo seu ID.
Estatísticas (Stats)
O recurso Stats fornece estatísticas de jogadores em jogos específicos. É possível filtrar por data (start_date e end_date), pelo ID do jogador (player_ids) e pelo ID do jogo (game_ids). Os endpoints para solicitações deste recurso são:

GET /stats: Retorna uma lista de estatísticas de jogadores em jogos específicos.
Parâmetros de consulta (Query parameters)
A API suporta vários parâmetros de consulta que podem ser usados ​​para filtrar, classificar e limitar os resultados das solicitações. Os principais parâmetros de consulta incluem:

per_page: Número de resultados por página.
page: Número da página desejada.
sort: Ordenação dos resultados.
search: Busca por um termo específico.
fields: Campos específicos a serem retornados na resposta.
Limites de taxa (Rate limits)
A API BallDontLie possui um limite de taxa de 150 solicitações por minuto. Se você exceder esse limite, receberá uma resposta com o código de status 429 (Muitas solicitações). É importante que você respeite esse limite para evitar bloqueios de IP.

Erros
A API retornará erros com o código de status HTTP apropriado. O corpo da resposta incluirá uma mensagem de erro explicando o problema.

Autenticação
A API BallDontLie não requer autenticação para ser usada.



# Endpoints que serão utilizados ou considerados na aplicação e seus recursos


Endpoints de jogadores
1. /players
Este endpoint retorna uma lista de jogadores. Os resultados podem ser filtrados por nome, posição e equipe.

Exemplo:
GET https://www.balldontlie.io/api/v1/players?search=LeBron James&per_page=5
Este exemplo retorna uma lista de até 5 jogadores que contêm "LeBron James" em seu nome.

2. /players/{id}
Este endpoint retorna informações detalhadas sobre um jogador específico com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/players/237

Endpoints de times
3. /teams
Este endpoint retorna uma lista de times. Os resultados podem ser filtrados por nome e cidade.

Exemplo: 
GET https://www.balldontlie.io/api/v1/teams?per_page=10
Este exemplo retorna uma lista de até 10 times.

4. /teams/{id}
Este endpoint retorna informações detalhadas sobre um time específico com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/teams/1

# Planificação - Telas e funcionalidades da aplicação

O aplicativo é uma plataforma de pesquisa e consulta de dados da NBA, focando em jogadores, times e jogos. Possui as seguintes telas:

1. Tela de carregamento (Splash)
2. Menu, com botões direcionando para as telas de busca e consulta
3. Tela de pesquisa, busca e consulta sobre jogadores
4. Tela de pesquisa, busca e consulta sobre times
5. Tela de histórico, com dados sobre as pesquisas recentes em ambas as telas.

# Navegação

<img src="https://user-images.githubusercontent.com/101807467/236198117-15264d4b-a554-43ef-9e4b-f99a231c05a5.png">

# Diagrama de Classes Diagrama de Banco

<img src="https://user-images.githubusercontent.com/101807467/236352837-7b3fb77e-e549-45c0-8e68-7697264bd66e.png">



