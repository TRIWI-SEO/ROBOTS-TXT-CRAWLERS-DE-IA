<p align="center">
  <img src="assets/logo-triwi.svg" alt="TRIWI, agência de SEO e Otimização para IAs" height="72">
</p>

<h1 align="center">Robots.txt e crawlers de IA: a base aberta dos robôs e modelos prontos, pela TRIWI</h1>

<p align="center">
  <strong>Os 27 robôs das IAs e dos buscadores, de GPTBot a ClaudeBot e PerplexityBot, conferidos na documentação oficial,<br>
  com modelos de robots.txt e de llms.txt e o efeito de cada escolha na presença da marca nas IAs.</strong>
</p>

<p align="center">
  <a href="https://triwi.com.br/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme"><img src="https://img.shields.io/badge/mantido%20pela-TRIWI-FF03ED?style=flat-square" alt="Mantido pela TRIWI"></a>
  <img src="https://img.shields.io/badge/rob%C3%B4s-27-30363d?style=flat-square" alt="27 robôs">
  <img src="https://img.shields.io/badge/empresas-11-30363d?style=flat-square" alt="11 empresas">
  <img src="https://img.shields.io/github/last-commit/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA?style=flat-square&label=atualizado&color=30363d" alt="Última atualização">
  <a href="LICENSE"><img src="https://img.shields.io/badge/licen%C3%A7a-CC%20BY%204.0-30363d?style=flat-square" alt="Licença CC BY 4.0"></a>
  <img src="https://img.shields.io/badge/idioma-portugu%C3%AAs-30363d?style=flat-square" alt="Conteúdo em português">
</p>

<p align="center">
  <sub>Verificado na documentação oficial em 09/11/2026</sub>
</p>

<p align="center">
  <a href="lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md">Lista de robôs de IA</a>
  &nbsp;|&nbsp;
  <a href="robots-txt-para-ia-modelos-prontos.md">Modelos de robots.txt</a>
  &nbsp;|&nbsp;
  <a href="robots-txt-o-que-e-exemplos-wordpress-e-ecommerce.md">Exemplos de robots.txt</a>
  &nbsp;|&nbsp;
  <a href="llms-txt-modelo-e-como-usar.md">Modelo de llms.txt</a>
  &nbsp;|&nbsp;
  <a href="dados/robos-de-ia.csv">Base em CSV</a>
  &nbsp;|&nbsp;
  <a href="https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme">Gerador de robots.txt</a>
</p>

---

## O que é o robots.txt para IAs?

**O robots.txt é o arquivo na raiz do site que diz a cada robô o que ele pode rastrear. Para as IAs, é com ele que a empresa escolhe, robô por robô, se o conteúdo pode treinar modelos, aparecer na busca de cada IA e ser lido quando um usuário pede. Bloquear o robô errado tira a marca das respostas de uma IA sem ninguém perceber.**

Este repositório da TRIWI reúne a base aberta dos 27 robôs de 11 empresas, entre IAs e buscadores, conferida robô por robô na documentação oficial em 09/11/2026: 7 de treino, 11 de busca, 8 de visita a pedido do usuário e 1 de arquivo aberto da web. Junto, quatro modelos prontos de robots.txt, um modelo de llms.txt e o efeito de cada escolha na presença da marca nas IAs.

| Função | O que faz | Robôs na base | Exemplos |
|:---|:---|:---|:---|
| Treino | Coleta conteúdo que pode ser usado para treinar modelos de IA, ou é o token que controla esse uso | 7 | `Google-Extended`, `GPTBot`, `ClaudeBot` e `meta-externalagent` |
| Busca | Rastreia e indexa páginas para a busca do buscador ou da IA, de onde saem as citações e os links das respostas | 11 | `Googlebot`, `OAI-SearchBot`, `Claude-SearchBot` e `Bingbot` |
| Visita a pedido do usuário | Abre uma página na hora em que um usuário pede, para responder ou executar uma tarefa | 8 | `Google-Agent`, `Google-GeminiNotebook`, `ChatGPT-User` e `Claude-User` |
| Arquivo aberto da web | Coleta páginas para um arquivo público da web, aberto a qualquer pessoa | 1 | `CCBot` |
| **Total** | | **27** | |

## Quem publica esta base?

A [TRIWI](https://triwi.com.br/sobre-a-triwi/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme) é a agência brasileira 100% especializada em SEO e Otimização para IAs (SEO + GEO) e uma das referências do setor no país. Fundada em 2018 por Ricardo Martins, trabalha com metodologia própria de 12 etapas e mais de 300 atividades. Contato Seguro, Sem Parar, Valid, Flexdoc e Polishop estão entre as marcas atendidas pela TRIWI.

Quem tenta decidir o que liberar para as IAs encontra a documentação espalhada em uma dúzia de sites, em inglês, e mudando o tempo todo: o Google, por exemplo, já trocou o token do NotebookLM pelo `Google-GeminiNotebook`. Listas de terceiros misturam robô de treino com robô de busca, e quem copia uma delas pode bloquear justamente o robô que faz a marca aparecer no ChatGPT ou no Perplexity.

Esta base resolve isso num lugar só, em português, com o link da documentação oficial e a data da verificação em cada linha. Ela faz parte do acervo aberto que a TRIWI mantém no GitHub, ao lado da [Base de Conhecimento de SEO e GEO](https://github.com/TRIWI-SEO/SEO-IA), e anda junto com o [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme), a ferramenta gratuita que monta o arquivo e testa as regras por robô.

## Índice

- [O que é o robots.txt para IAs](#o-que-é-o-robotstxt-para-ias)
- [Quem publica](#quem-publica-esta-base)
- [Páginas deste repositório](#páginas-deste-repositório)
- [Os robôs de IA e dos buscadores](#quais-são-os-robôs-de-ia-e-dos-buscadores)
- [Qual modelo de robots.txt usar](#qual-modelo-de-robotstxt-usar)
- [Dados abertos](#dados-abertos)
- [Como a base é verificada](#como-a-base-é-verificada)
- [Perguntas frequentes](#perguntas-frequentes)
- [Como citar](#como-citar)

## Páginas deste repositório

| Página | O que resolve |
|:---|:---|
| [Lista de robôs de IA: GPTBot, ClaudeBot, PerplexityBot e os demais](lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md) | Os 27 robôs, empresa por empresa, com o que acontece se cada um for bloqueado |
| [Robots.txt para IA: modelos prontos](robots-txt-para-ia-modelos-prontos.md) | Quatro modelos de robots.txt, como o arquivo funciona com as IAs e qual escolher |
| [Robots.txt: o que é e exemplos para WordPress e e-commerce](robots-txt-o-que-e-exemplos-wordpress-e-ecommerce.md) | A sintaxe, as regras da norma, modelos para WordPress e loja virtual e como juntar com as regras para IAs |
| [llms.txt: modelo e como usar](llms-txt-modelo-e-como-usar.md) | O modelo de llms.txt em português, o formato e o que o arquivo faz e não faz |
| [Dicionário de dados](dados/dicionario-de-dados.md) | O significado de cada coluna da base e como ela é mantida |

## Quais são os robôs de IA e dos buscadores?

| Empresa | Robô (user-agent) | Função | Segue o robots.txt? | Documentação oficial |
|:---|:---|:---|:---|:---|
| Google | `Googlebot` | Busca | Sim, declarado | [Abrir](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) |
| Google | `Google-Extended` | Treino | Não se aplica | [Abrir](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) |
| Google | `Google-Agent` | Visita a pedido do usuário | Em geral não segue | [Abrir](https://developers.google.com/crawling/docs/crawlers-fetchers/google-user-triggered-fetchers) |
| Google | `Google-GeminiNotebook` | Visita a pedido do usuário | Em geral não segue | [Abrir](https://developers.google.com/crawling/docs/crawlers-fetchers/google-user-triggered-fetchers) |
| OpenAI | `GPTBot` | Treino | Bloqueio documentado | [Abrir](https://developers.openai.com/api/docs/bots) |
| OpenAI | `OAI-SearchBot` | Busca | Bloqueio documentado | [Abrir](https://developers.openai.com/api/docs/bots) |
| OpenAI | `ChatGPT-User` | Visita a pedido do usuário | Pode não seguir | [Abrir](https://developers.openai.com/api/docs/bots) |
| Anthropic | `ClaudeBot` | Treino | Sim, declarado | [Abrir](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) |
| Anthropic | `Claude-SearchBot` | Busca | Sim, declarado | [Abrir](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) |
| Anthropic | `Claude-User` | Visita a pedido do usuário | Sim, declarado | [Abrir](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) |
| Microsoft | `Bingbot` | Busca | Bloqueio documentado | [Abrir](https://www.bing.com/webmasters/help/which-crawlers-does-bing-use-8c184ec0) |
| Perplexity | `PerplexityBot` | Busca | Bloqueio documentado | [Abrir](https://docs.perplexity.ai/guides/bots) |
| Perplexity | `Perplexity-User` | Visita a pedido do usuário | Em geral não segue | [Abrir](https://docs.perplexity.ai/guides/bots) |
| Meta | `meta-externalagent` | Treino | Bloqueio documentado | [Abrir](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers) |
| Meta | `meta-webindexer` | Busca | Bloqueio documentado | [Abrir](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers) |
| Meta | `meta-externalfetcher` | Visita a pedido do usuário | Pode não seguir | [Abrir](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers) |
| Apple | `Applebot` | Busca | Sim, declarado | [Abrir](https://support.apple.com/en-us/119829) |
| Apple | `Applebot-Extended` | Treino | Não se aplica | [Abrir](https://support.apple.com/en-us/119829) |
| Amazon | `Amazonbot` | Treino | Sim, declarado | [Abrir](https://developer.amazon.com/amazonbot) |
| Amazon | `Amzn-SearchBot` | Busca | Sim, declarado | [Abrir](https://developer.amazon.com/amazonbot) |
| Amazon | `Amzn-User` | Visita a pedido do usuário | Pode não seguir | [Abrir](https://developer.amazon.com/amazonbot) |
| Mistral AI | `MistralAI-Training` | Treino | Bloqueio documentado | [Abrir](https://docs.mistral.ai/robots) |
| Mistral AI | `MistralAI-Index` | Busca | Bloqueio documentado | [Abrir](https://docs.mistral.ai/robots) |
| Mistral AI | `MistralAI-User` | Visita a pedido do usuário | Sim, declarado | [Abrir](https://docs.mistral.ai/robots) |
| DuckDuckGo | `DuckDuckBot` | Busca | Sim, declarado | [Abrir](https://duckduckgo.com/duckduckgo-help-pages/results/duckduckbot) |
| DuckDuckGo | `DuckAssistBot` | Busca | Bloqueio documentado | [Abrir](https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot) |
| Common Crawl | `CCBot` | Arquivo aberto da web | Bloqueio documentado | [Abrir](https://commoncrawl.org/ccbot) |

O que acontece quando cada robô é bloqueado, o trecho da documentação que sustenta a classificação, a frase que aparece no log e como confirmar a origem de cada robô estão na [Lista de robôs de IA](lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md). Os robôs e as regras mudam: em caso de divergência, vale a página oficial da empresa.

## Qual modelo de robots.txt usar?

| Modelo | O que faz | Efeito na presença da marca | Arquivo |
|:---|:---|:---|:---|
| [Liberar tudo](robots-txt-para-ia-modelos-prontos.md#como-liberar-tudo-para-as-ias-no-robotstxt) | Todos os buscadores e IAs podem rastrear o site, para busca, para visitas a pedido do usuário e para treino. | A marca pode aparecer em todas as IAs e buscadores da base, e o conteúdo pode entrar no treino de modelos. | [robots-txt-liberar-tudo.txt](modelos/robots-txt-liberar-tudo.txt) |
| [Bloquear o treino e manter a busca](robots-txt-para-ia-modelos-prontos.md#como-bloquear-o-treino-de-ia-e-manter-a-busca) | Os robôs e tokens de treino ficam sem acesso; os robôs de busca e de visita a pedido do usuário continuam liberados. | A marca continua citável na busca do ChatGPT, do Claude, do Perplexity, da Meta AI e nos AI Overviews; sai das próximas coletas de treino e da base (grounding) dos apps Gemini. | [robots-txt-bloquear-treino-manter-busca.txt](modelos/robots-txt-bloquear-treino-manter-busca.txt) |
| [Bloquear as IAs e manter os buscadores](robots-txt-para-ia-modelos-prontos.md#como-bloquear-as-ias-e-manter-o-google-e-o-bing) | Só `Googlebot`, `Bingbot`, `Applebot` e `DuckDuckBot` continuam com acesso; todos os outros robôs da base ficam bloqueados. | A marca continua no Google, inclusive nos AI Overviews e no Modo IA, e no Bing; sai da busca do ChatGPT, do Claude, do Perplexity, da Meta AI e da Mistral. | [robots-txt-bloquear-ias-manter-buscadores.txt](modelos/robots-txt-bloquear-ias-manter-buscadores.txt) |
| [Bloquear tudo](robots-txt-para-ia-modelos-prontos.md#como-bloquear-todos-os-robôs-no-robotstxt) | Nenhum robô que siga o robots.txt pode rastrear o site. | O site sai do Google, do Bing e das IAs. Serve para ambiente de homologação, não para site em produção. | [robots-txt-bloquear-tudo.txt](modelos/robots-txt-bloquear-tudo.txt) |

Para a maioria das empresas que querem ser encontradas e citadas, os robôs de busca das IAs devem ficar liberados. Como resume o [Guia de GEO da TRIWI](https://triwi.com.br/guias/geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme), bloquear o treino é decisão de negócio, tomada com o jurídico, porque envolve o uso do conteúdo; bloquear a busca é decisão de visibilidade. O efeito de cada modelo, IA por IA, está em [Robots.txt para IA: modelos prontos](robots-txt-para-ia-modelos-prontos.md), e o [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme) monta a versão do seu site com essas escolhas.

O modelo Bloquear as IAs vale para os robôs documentados na base. Robôs sem documentação oficial, como o `Bytespider`, continuam liberados pelo grupo geral `User-agent: *`; para barrá-los, bloqueie no servidor ou na CDN. Para a parte do robots.txt que não tem a ver com IA, como a área administrativa do WordPress ou o carrinho da loja, veja os [exemplos para WordPress e e-commerce](robots-txt-o-que-e-exemplos-wordpress-e-ecommerce.md).

## Dados abertos

| Arquivo | O que traz | Linhas |
|:---|:---|:---|
| [dados/robos-de-ia.csv](dados/robos-de-ia.csv) | Cada robô com empresa, produto, user-agent, função, se segue o robots.txt e o trecho da documentação que sustenta isso, o efeito do bloqueio, a frase que aparece no log, como confirmar a origem, o link da documentação oficial e a data da verificação | 27 |

O significado de cada coluna está no [dicionário de dados](dados/dicionario-de-dados.md). Os arquivos de modelo estão na tabela [Qual modelo de robots.txt usar](#qual-modelo-de-robotstxt-usar), nos [exemplos para WordPress e e-commerce](robots-txt-o-que-e-exemplos-wordpress-e-ecommerce.md) e no [modelo de llms.txt](llms-txt-modelo-e-como-usar.md). Os modelos para IAs são gerados a partir da base, então nunca divergem dela: quando um robô entra ou muda, os modelos mudam junto. Outras bases abertas da TRIWI, como o [glossário de SEO, marketing e IA](https://github.com/TRIWI-SEO/SEO-IA/blob/main/dados/glossario-triwi.csv) e as [atualizações do Google e das IAs](https://github.com/TRIWI-SEO/SEO-IA/blob/main/dados/atualizacoes-google-e-ias.csv), estão na Base de Conhecimento.

## Como a base é verificada?

| Critério | Como funciona |
|:---|:---|
| Fonte | Só a documentação oficial da empresa dona do robô, com o link em cada linha |
| O que entra | Robôs e tokens de controle que decidem treino, busca ou visita a pedido do usuário |
| O que fica fora | Robôs sem documentação oficial, robôs de anúncio, de prévia de link e de verificação |
| Segue o robots.txt | Duas classificações separadas: declaração explícita da empresa ou bloqueio documentado sem declaração; quando a empresa avisa que o robô pode ignorar o arquivo, a base registra. Cada linha traz o trecho da documentação, no original |
| Log e origem | A frase do user-agent como aparece no log e o link da lista de IPs ou do método de verificação, quando a empresa publica |
| Data | Cada linha tem a data em que a documentação foi conferida |
| Divergência | Quando um artigo de terceiro diverge da documentação oficial, vale a documentação oficial |

A base é informativa e não substitui a documentação de cada empresa, que pode mudar a qualquer momento. Antes de publicar um robots.txt em produção, confira as regras com o [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme), que testa quais regras valem para cada URL e cada robô.

## Perguntas frequentes

<details>
<summary><strong>O que é o GPTBot e bloquear o GPTBot tira o site do ChatGPT?</strong></summary>

O `GPTBot` é o robô da OpenAI que coleta conteúdo que pode ser usado no treino dos modelos. Bloquear o `GPTBot` não tira o site da busca do ChatGPT, que depende de outro robô, o `OAI-SearchBot`: a OpenAI diz que as duas regras são independentes. Os três robôs da OpenAI estão na [Lista de robôs de IA](lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md#quais-são-os-robôs-da-openai).
</details>

<details>
<summary><strong>Como bloquear as IAs no robots.txt sem sair do Google?</strong></summary>

Use o modelo [Bloquear as IAs e manter os buscadores](robots-txt-para-ia-modelos-prontos.md#como-bloquear-as-ias-e-manter-o-google-e-o-bing). Ele mantém o `Googlebot`, o `Bingbot`, o `Applebot` e o `DuckDuckBot` e bloqueia os demais. Os AI Overviews e o Modo IA continuam, porque usam as páginas que o `Googlebot` indexa; para limitar o que aparece neles, o Google indica [nosnippet, max-snippet e noindex](https://developers.google.com/search/docs/appearance/ai-features).
</details>

<details>
<summary><strong>O Google-Extended tira o site dos AI Overviews?</strong></summary>

Não. O Google diz que o `Google-Extended` não afeta a inclusão na Pesquisa Google nem é sinal de ranking. Ele controla o uso do conteúdo no treino dos próximos modelos Gemini e como base (grounding) das respostas dos apps Gemini e da Vertex AI. Ou seja: bloquear o `Google-Extended` pode reduzir a presença da marca no app Gemini, mas não nos AI Overviews.
</details>

<details>
<summary><strong>Os robôs de IA respeitam o robots.txt?</strong></summary>

Depende do robô. Na base, 9 robôs têm declaração explícita da empresa de que seguem o arquivo, e 10 têm o bloqueio pelo robots.txt documentado, sem essa declaração. Os que visitam páginas a pedido do usuário são outra história: OpenAI, Meta e Amazon avisam que eles podem não seguir, e Google e Perplexity dizem que em geral não seguem. São 6 robôs nessa situação; para barrá-los de fato, o bloqueio tem que ser feito no servidor ou na CDN. Cada linha da base traz o trecho da documentação que sustenta a classificação.
</details>

<details>
<summary><strong>Bloquear o treino agora remove o conteúdo de modelos já treinados?</strong></summary>

Não. O robots.txt vale para as coletas seguintes. A Anthropic, por exemplo, fala em excluir dos dados de treino o material publicado dali em diante. O que já foi coletado antes do bloqueio não é desfeito pelo arquivo.
</details>

<details>
<summary><strong>Preciso de um arquivo llms.txt?</strong></summary>

Para o Google, não: a documentação [Recursos de IA e seu site](https://developers.google.com/search/docs/appearance/ai-features) diz que não é preciso criar arquivo novo nem marcação especial para aparecer nos AI Overviews e no Modo IA. O llms.txt é uma proposta aberta, e o [Guia de GEO da TRIWI](https://triwi.com.br/guias/geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme) recomenda tratá-lo como mapa opcional. O modelo pronto está em [llms.txt: modelo e como usar](llms-txt-modelo-e-como-usar.md).
</details>

<details>
<summary><strong>Como saber quais robôs de IA visitam o meu site?</strong></summary>

Pelos logs do servidor, que registram o user-agent de cada visita. O [Analisador de logs para SEO da TRIWI](https://triwi.com.br/ferramentas/analisador-de-logs-para-seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme) mostra quais páginas os robôs de busca e de IA estão rastreando. Como o user-agent pode ser falsificado, confirme pelos métodos de verificação e faixas de IP que Google, Bing, OpenAI, Mistral e DuckDuckGo publicam.
</details>

<details>
<summary><strong>Por que alguns robôs conhecidos não estão na base?</strong></summary>

Porque a base só aceita robô com documentação oficial publicada pela própria empresa. Robôs citados em listas de terceiros, sem página oficial que diga para que servem, ficam fora até que a empresa documente. Robôs de anúncio, de prévia de link e de verificação também ficam fora, porque não decidem a presença da marca nas buscas e nas IAs.
</details>

<details>
<summary><strong>Com que frequência a base é revisada?</strong></summary>

Uma vez por mês e sempre que uma empresa muda a documentação. Cada linha tem a data da última verificação. As mudanças das IAs também aparecem nas [linhas do tempo de atualizações da TRIWI](https://triwi.com.br/atualizacoes/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme). Correções chegam por [issue](../../issues/new).
</details>

<details>
<summary><strong>Posso reutilizar esta base e os modelos?</strong></summary>

Sim. A base, os modelos e os textos estão sob licença [CC BY 4.0](LICENSE): você pode copiar, adaptar e usar, inclusive comercialmente, desde que cite a TRIWI e este repositório como fonte. O formato sugerido está em [Como citar](#como-citar).
</details>

## Histórico de atualizações

| Data | O que mudou |
|:---|:---|
| 09/11/2026 | Revisão no dia do lançamento: trecho da documentação, frase do user-agent e verificação de origem em cada robô; classificação separada entre declaração e bloqueio documentado; página de exemplos para WordPress e e-commerce; tabela de qual robô bloquear para cada objetivo |
| 09/11/2026 | Publicação da base com 27 robôs de 11 empresas, quatro modelos de robots.txt, modelo de llms.txt e três páginas de apoio |

## Como citar

> TRIWI. **Robots.txt e crawlers de IA: base aberta dos robôs das IAs e dos buscadores e modelos de robots.txt.** GitHub, 2026. Disponível em: https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA. Acesso em: dia, mês e ano.

## Licença

A base, os modelos e os textos estão sob a licença [Creative Commons Atribuição 4.0 Internacional (CC BY 4.0)](LICENSE): reuso livre, inclusive comercial, desde que citada a TRIWI como fonte. Marcas e nomes de robôs pertencem às respectivas empresas.

---

<p align="center">
  <strong>Quando alguém pergunta à IA sobre o seu mercado, ela cita a sua empresa?</strong><br>
  <a href="https://triwi.com.br/contato/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=readme">Que tal um café com a TRIWI?</a>
</p>

<p align="center">
  <sub>Base publicada e mantida pela equipe da TRIWI, agência 100% especializada em SEO e Otimização para IAs.</sub>
</p>
