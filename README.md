# Documentação da API BallDontLie
BallDontLie - API que fornece estatísticas de basquete sobre a NBA. Esta API é gratuita e aberta para uso público.

Base URL
O URL base para todas as solicitações é: https://www.balldontlie.io/api/v1/

Recursos
A API fornece os seguintes recursos:

Jogos (Games)
GET /games: Retorna uma lista de jogos. É possível filtrar por data (start_date e end_date), pela equipe da casa (home_team) e pela equipe visitante (visitor_team).

GET /games/:id: Retorna um jogo específico pelo seu ID.

Equipes (Teams)
GET /teams: Retorna uma lista de equipes.

GET /teams/:id: Retorna uma equipe específica pelo seu ID.

Jogadores (Players)
GET /players: Retorna uma lista de jogadores.

GET /players/:id: Retorna um jogador específico pelo seu ID.

Estatísticas (Stats)
GET /stats: Retorna uma lista de estatísticas de jogadores em jogos específicos. É possível filtrar por data (start_date e end_date), pelo ID do jogador (player_ids) e pelo ID do jogo (game_ids).

Parâmetros de consulta (Query parameters)
A API suporta os seguintes parâmetros de consulta:

per_page: Número de resultados por página. O padrão é 25 e o máximo é 100.
page: Número da página desejada.
sort: Ordenação dos resultados. Pode ser asc (crescente) ou desc (decrescente).
search: Busca por um termo específico.
fields: Campos específicos a serem retornados na resposta.

Exemplo de solicitação:
bash
GET /games?start_date=2022-01-01&end_date=2022-01-31&home_team=Los Angeles Lakers&per_page=50&page=2
Esta solicitação retornará uma lista de jogos dos Lakers em janeiro de 2022, com 50 resultados por página e exibindo a segunda página de resultados.

Limites de taxa (Rate limits)
A API tem um limite de taxa de 150 solicitações por minuto. Se você exceder esse limite, receberá uma resposta com o código de status 429 (Muitas solicitações). É importante que você respeite esse limite para evitar bloqueios de IP.

Erros
A API retornará erros com o código de status HTTP apropriado. O corpo da resposta incluirá uma mensagem de erro explicando o problema.

Autenticação
A API BallDontLie não requer autenticação para ser usada.
