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
