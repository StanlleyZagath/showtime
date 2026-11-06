# Show Time

App pessoal para acompanhar séries e filmes, com visual inspirado em serviços de streaming. Funciona direto no navegador, instala no celular como app (PWA) e não precisa de servidor.

## O que ele faz

- **Séries:** acompanhe episódios por temporada, marque como visto (com "marcar toda a temporada"), veja o próximo episódio e o progresso de cada série.
- **Filmes:** listas "Quero ver" e "Assistidos".
- **Início:** banner em destaque, "Continuar assistindo", assistidos recentemente, favoritos e fileiras por gênero, com setas e arraste lateral.
- **Explorar:** filmes em cartaz no cinema, em alta na semana, lançamentos e estreias recentes, Top 10 da semana e Top 10 de bilheteria.
- **Filtros e ordenação:** por gênero, década, situação, favoritos, sua nota e nota geral, além de busca dentro da lista.
- **Notas e informações:** sua nota de 1 a 5 estrelas, nota de crítica (Rotten Tomatoes), nota do público (TMDB e IMDb), Metacritic, Oscars e outros prêmios, elenco, direção, onde assistir no Brasil e trailer.
- **Favoritos, histórico e calendário** de próximos episódios.
- **Importação do TV Time** (a partir do export de dados) e backup em arquivo.
- **Sincronização opcional** entre aparelhos, com login Google ou e-mail e senha (Firebase).

## Fontes de dados

| Fonte | Uso | Chave |
|---|---|---|
| [TVmaze](https://www.tvmaze.com/api) | séries e episódios | não precisa |
| [TMDB](https://www.themoviedb.org/) | filmes, Explorar, elenco, onde assistir | grátis, em Perfil |
| [OMDb](https://www.omdbapi.com/) | Rotten Tomatoes (crítica), IMDb, Metacritic, prêmios | grátis, em Perfil |

A nota do **público** do Rotten Tomatoes não está disponível em APIs gratuitas. O app mostra o público do TMDB e do IMDb e tem um atalho para a página do título no Rotten Tomatoes.

## Como usar

1. Abra o endereço do app (GitHub Pages) ou rode localmente: `npx http-server .` e acesse `http://localhost:8080`.
2. Em **Perfil**, cole as chaves do TMDB e do OMDb (ficam salvas só no seu aparelho).
3. Para instalar no celular: Android com Chrome → "Instalar app"; iPhone com Safari → Compartilhar → "Adicionar à Tela de Início".

## Seus dados

Tudo fica salvo no navegador (`localStorage`). Use **Perfil → Exportar backup** de vez em quando. Para ter a mesma lista em vários aparelhos, configure a sincronização seguindo [CONFIGURAR-FIREBASE.md](CONFIGURAR-FIREBASE.md).

## Aviso

Projeto pessoal, sem vínculo com TV Time, Netflix, Rotten Tomatoes ou TMDB. Este produto usa a API do TMDB, mas não é endossado nem certificado por ela.
