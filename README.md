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

3. /players/{id}/stats
Este endpoint retorna uma lista de estatísticas de um jogador específico com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/players/237/stats

4. /players/{id}/season_averages
Este endpoint retorna as médias de estatísticas de um jogador específico com o ID especificado para todas as temporadas.

Exemplo:
GET https://www.balldontlie.io/api/v1/players/237/season_averages

5. /players/{id}/games
Este endpoint retorna uma lista de jogos que um jogador específico com o ID especificado jogou.

Exemplo:
GET https://www.balldontlie.io/api/v1/players/237/games

Endpoints de times
6. /teams
Este endpoint retorna uma lista de times. Os resultados podem ser filtrados por nome e cidade.

Exemplo: 
GET https://www.balldontlie.io/api/v1/teams?per_page=10
Este exemplo retorna uma lista de até 10 times.

7. /teams/{id}
Este endpoint retorna informações detalhadas sobre um time específico com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/teams/1

8. /teams/{id}/stats
Este endpoint retorna uma lista de estatísticas de uma equipe específica com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/teams/1/stats

9. /teams/{id}/games
Este endpoint retorna uma lista de jogos que uma equipe específica com o ID especificado jogou.

Exemplo:
GET https://www.balldontlie.io/api/v1/teams/1/games

Endpoints de jogos
10. /games
Este endpoint retorna uma lista de jogos. Os resultados podem ser filtrados por data, equipe da casa, equipe visitante e status do jogo.

Exemplo:
GET https://www.balldontlie.io/api/v1/games?seasons[]=2020&team_ids[]=1&status[]=Final&per_page=5
Este exemplo retorna uma lista de até 5 jogos jogados na temporada 2020, onde o time com ID 1 participou e o status do jogo é "Final".

11. /games/{id}
Este endpoint retorna informações detalhadas sobre um jogo específico com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/games/40107

12. /schedule
Este endpoint retorna uma lista de jogos agendados. Os resultados podem ser filtrados por data, equipe da casa e equipe visitante.

Exemplo:
GET https://www.balldontlie.io/api/v1/schedule?start_date=2022-05-01&end_date=2022-05-15&team_ids[]=1&team_ids[]=2
Este exemplo retorna uma lista de jogos agendados entre 1 e 15 de maio de 2022, onde os times com ID 1 e 2 participam.

13. /games/{id}/play_by_play
Este endpoint retorna uma lista de jogadas de um jogo específico com o ID especificado.

Exemplo:
GET https://www.balldontlie.io/api/v1/games/40107/play_by_play





# Planificação - Telas e funcionalidades da aplicação

O aplicativo é uma plataforma de pesquisa e consulta de dados da NBA, focando em jogadores, times e jogos. Possui as seguintes telas:

Tela de carregamento (Splash)
Menu, com botões direcionando para as telas de busca e consulta
Tela de pesquisa, busca e consulta sobre jogadores
Tela de pesquisa, busca e consulta sobre times
Tela de pesquisa, busca e consulta sobre jogos e informações
Tela de histórico, com dados sobre as pesquisas recentes em ambas as telas.
Caso necessário - haverá somente a adição de telas referente ao resultados das respectivas anteriores para a exibição de seus dados.
