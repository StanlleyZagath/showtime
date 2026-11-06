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

1. Abra o endereço do app (GitHub Pages) ou rode localmente (veja abaixo).
2. Em **Perfil**, cole as chaves do TMDB e do OMDb (ficam salvas só no seu aparelho).
3. Para instalar no celular: Android com Chrome → "Instalar app"; iPhone com Safari → Compartilhar → "Adicionar à Tela de Início".

## Baixar e rodar no seu computador

1. Instale o [Git](https://git-scm.com/downloads) e o [Node.js](https://nodejs.org/) (o Node só é usado para abrir um servidor local).
2. Clone o repositório e entre na pasta:
   ```bash
   git clone https://github.com/StanlleyZagath/showtime.git
   cd showtime
   ```
   (Se preferir interface gráfica, use o [GitHub Desktop](https://desktop.github.com/): **File → Clone repository → URL** e cole o endereço acima.)
3. Abra um servidor local:
   ```bash
   npx http-server . -p 8080
   ```
4. Acesse `http://localhost:8080` no Chrome ou no Edge.

> Abrir o `index.html` com duplo clique não é recomendado: o modo offline e a instalação como app só funcionam por `http://localhost` ou `https`.

## Publicar a sua própria cópia (GitHub Pages)

Para ter o app online, com endereço https, e poder instalá-lo no celular, você precisa de uma cópia do repositório na **sua** conta.

**Etapa 1: copiar o repositório para a sua conta**
1. Entre na sua conta do GitHub.
2. Abra https://github.com/StanlleyZagath/showtime e clique em **Fork** (canto superior direito) → **Create fork**.

**Etapa 2: abrir a página de configuração do Pages**
1. No seu fork, clique em **Settings** (aba no topo do repositório).
2. No menu da esquerda, clique em **Pages**. O endereço direto é `https://github.com/SEU-USUARIO/showtime/settings/pages`.
3. Se aparecer "404", você não está logado na conta dona do fork.

**Etapa 3: escolher de onde o site sai**
1. Em **Build and deployment → Source**, deixe **Deploy from a branch**.
2. Em **Branch**, abra o menu "None" e escolha **main**.
3. No menu ao lado, deixe **/ (root)** e clique em **Save**.

**Etapa 4: esperar e abrir o site**
1. Atualize a página com `F5`. Depois de 1 a 2 minutos aparece a faixa "Your site is live at…".
2. O endereço fica no formato `https://SEU-USUARIO.github.io/showtime/`. Abra no celular e instale como app.

Se você mudar algum arquivo e enviar ao GitHub (`git push` ou **Push origin** no GitHub Desktop), o site atualiza sozinho em cerca de 1 minuto. Depois de atualizar, force o recarregamento no navegador com `Ctrl+Shift+R`, porque o app guarda uma cópia em cache.

Para login e sincronização entre aparelhos, siga [CONFIGURAR-FIREBASE.md](CONFIGURAR-FIREBASE.md) e adicione `SEU-USUARIO.github.io` aos domínios autorizados do Firebase.

## Seus dados

Tudo fica salvo no navegador (`localStorage`). Use **Perfil → Exportar backup** de vez em quando. Para ter a mesma lista em vários aparelhos, configure a sincronização seguindo [CONFIGURAR-FIREBASE.md](CONFIGURAR-FIREBASE.md).

## Aviso

Projeto pessoal, sem vínculo com TV Time, Netflix, Rotten Tomatoes ou TMDB. Este produto usa a API do TMDB, mas não é endossado nem certificado por ela.
