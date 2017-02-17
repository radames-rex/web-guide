# Diretrizes Web
> Checklist para ajudar no desenvolvimento progressivo de aplicações para web

Detalhes técnicos que os desenvolvedores web devem considerar antes de colocar um projeto no ar.

Talvez muitos dos itens você já deve conhecer. No entanto, algum item foi esquecido, deixado de lado ou não entendeu exatamente como funciona ou nunca ouviu falar, esse checklist vai te ajudar entender melhor.

## SEO (Search Engine Optimization)

* Instale [Google Analytics] (http://www.google.com/analytics/) no início (ou uma ferramenta de análise como [SharpSpring] (https://br.sharpspring.com/)). As ferramentas ajudam a integrar vários os itens dessa lista.

* Nos links ``<a title="">`` e imagens ``<img alt="" />`` não esquecer dos atributos ``title`` e ``alt`` respectivamente.

* Ter um [Sitemap XML] (http://www.sitemaps.org/), de preferência na raiz do projeto `/sitemap.xml`.

* Utilize URLs Amigáveis para "Mecanismos de busca", ou seja, use `example.com/pages/10-post-title` ao invés de `example.com/index.php?page=10`

* Não use links dizendo ["Clique aqui"] (http://ux.stackexchange.com/questions/12100/why-shouldnt-we-use-the-word-here-in-a-textlink). Você está desperdiçando uma oportunidade de SEO e torna as coisas mais difíceis para as pessoas com leitores de tela.

* Utilizar ``rel="no-follow"``. Serve para dizer aos mecanismos de busca, "Não siga links desta página" ou "Não siga este link específico". [Mais informaçes](https://support.google.com/webmasters/answer/96569?hl=pt-BR)

* Use [Ferramentas do Google para webmasters](http://www.google.com/webmasters/) and [Ferramentas do Bing para webmasters](http://www.bing.com/toolbox/webmaster).

* Entender como [robots.txt] (http://en.wikipedia.org/wiki/Robots_exclusion_standard) e o ``robô`` do Google trabalham indexando os links do site.

* Redirecionar solicitações (usando `301 Moved Permanently`) pedindo` www.example.com` para `example.com` (ou vice-versa) para evitar a divisão do ranking do google entre os dois sites.

* Use [Microdata](http://kaidez.com/html5-seo-microdata/), um padrão de representação de informações que estende as potencialidades semânticas do HTML5. [Ferramenta](https://search.google.com/structured-data/testing-tool) pra testar Microdata

* Use [`<link rel="canonical"...`](http://googlewebmastercentral.blogspot.com/2009/02/specify-your-canonical.html) quando você tem vários URLs que apontam para o mesmo conteúdo, este problema também pode ser abordado em [Ferramentas do Google para webmasters] (http://www.google.com/webmasters/).

* (Caso esteja usando uma aplicação em javascript ou SPA). Ao usar hash `#` para conteúdo dinâmico, altere a hash `#` para `#!` em seguida, no servidor `$_REQUEST["_escaped_fragment_"]` é o que googlebot usa em vez de `#!`. Em outras palavras, `./#!page=1` torna-se `./?_escaped_fragments_=page=1`. Além disso, para usuários que podem estar usando Firefox ou Chromium, `history.pushState({"foo": "bar"}, "Sobre", "./?page=1");` Portanto, mesmo que a barra de endereços tenha sido alterada, a página não será recarregada. Isso permite que você use `?` Em vez de `#!` Para manter o conteúdo dinâmico e também informar o servidor quando você envia um e-mail para o link que estamos atrás desta página e o AJAX não precisa fazer outra solicitação extra.

## Links para referência

[Guia - Otimização para buscadores](https://static.googleusercontent.com/media/www.google.com/pt-BR//intl/pt-PT/webmasters/docs/guia-optimizacao-para-motores-de-busca-PTpt.pdf)

[Tutorial de SEO em pt-BR](http://www.seomarketing.com.br/tutorial-SEO.php)

## Créditos
[StackExchange](http://softwareengineering.stackexchange.com/questions/46716/what-technical-details-should-a-programmer-of-a-web-application-consider-before#167608)
