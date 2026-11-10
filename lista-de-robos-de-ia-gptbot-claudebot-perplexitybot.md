# Lista de robôs de IA: GPTBot, ClaudeBot, PerplexityBot e os user-agents de cada empresa

**Os robôs de IA são os programas que as empresas de IA e os buscadores usam para ler sites, cada um identificado por um nome (o user-agent). Cada empresa tem robôs diferentes para treinar modelos, para a busca da IA e para visitar páginas a pedido do usuário: a OpenAI usa `GPTBot`, `OAI-SearchBot` e `ChatGPT-User`; a Anthropic, `ClaudeBot`, `Claude-SearchBot` e `Claude-User`; o Perplexity, `PerplexityBot` e `Perplexity-User`. Esta lista traz os 27 robôs de 11 empresas, conferidos na documentação oficial em 09/11/2026.**

A base é da TRIWI, agência brasileira 100% especializada em SEO e Otimização para IAs. Para montar o robots.txt com estes robôs, use os [modelos prontos](robots-txt-para-ia-modelos-prontos.md) ou o [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos).

*Por equipe de SEO da TRIWI, com revisão de Ricardo Martins, fundador. Publicado em 09/11/2026. Atualizado em 09/11/2026.*

## Índice

- [Quais são os robôs do Google?](#quais-são-os-robôs-do-google)
- [Quais são os robôs da OpenAI?](#quais-são-os-robôs-da-openai)
- [Quais são os robôs da Anthropic?](#quais-são-os-robôs-da-anthropic)
- [Quais são os robôs da Microsoft?](#quais-são-os-robôs-da-microsoft)
- [Quais são os robôs do Perplexity?](#quais-são-os-robôs-do-perplexity)
- [Quais são os robôs da Meta?](#quais-são-os-robôs-da-meta)
- [Quais são os robôs da Apple?](#quais-são-os-robôs-da-apple)
- [Quais são os robôs da Amazon?](#quais-são-os-robôs-da-amazon)
- [Quais são os robôs da Mistral AI?](#quais-são-os-robôs-da-mistral-ai)
- [Quais são os robôs do DuckDuckGo?](#quais-são-os-robôs-do-duckduckgo)
- [Quais são os robôs da Common Crawl?](#quais-são-os-robôs-da-common-crawl)
- [Como os robôs se dividem por função?](#como-os-robôs-se-dividem-por-função)
- [Por que alguns robôs não estão nesta lista?](#por-que-alguns-robôs-não-estão-nesta-lista)
- [Como confirmar que a visita é de um robô verdadeiro?](#como-confirmar-que-a-visita-é-de-um-robô-verdadeiro)
- [Perguntas frequentes](#perguntas-frequentes)

## Quais são os robôs do Google?

A base traz 4 robôs do Google: `Googlebot`, `Google-Extended`, `Google-Agent` e `Google-GeminiNotebook`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`Googlebot`](#o-que-é-o-googlebot) | Busca | Sim, declarado |
| [`Google-Extended`](#o-que-é-o-google-extended) | Treino | Não se aplica |
| [`Google-Agent`](#o-que-é-o-google-agent) | Visita a pedido do usuário | Em geral não segue |
| [`Google-GeminiNotebook`](#o-que-é-o-google-gemininotebook) | Visita a pedido do usuário | Em geral não segue |

Documentação oficial: [página sobre `Googlebot` e `Google-Extended`](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) e [página sobre `Google-Agent` e `Google-GeminiNotebook`](https://developers.google.com/crawling/docs/crawlers-fetchers/google-user-triggered-fetchers), conferidas em 09/11/2026. Mudanças recentes: [Atualizações do Google](https://triwi.com.br/atualizacoes/google/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos) e [Atualizações do Gemini](https://triwi.com.br/atualizacoes/gemini/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

### O que é o Googlebot?

O `Googlebot` é o robô de busca do Google (Pesquisa Google, AI Overviews e Modo IA). Os rastreadores comuns do Google seguem o robots.txt no rastreamento automático. Para limitar o que aparece nos recursos de IA da busca, o Google indica nosnippet, data-nosnippet, max-snippet e noindex.

- **Se for bloqueado:** O site deixa de ser rastreado para a Pesquisa Google e, com isso, sai também dos AI Overviews e do Modo IA, que só usam páginas indexadas na Pesquisa.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “They always obey robots.txt rules when crawling automatically.”
- **Como aparece no log:** `Googlebot/2.1 (+http://www.google.com/bot.html)`
- **Como confirmar a origem:** [método oficial de verificação](https://developers.google.com/crawling/docs/crawlers-fetchers/verify-google-requests)

### O que é o Google-Extended?

O `Google-Extended` é o token de controle de treino do Google (Apps Gemini e Vertex AI). Não é um robô: é um token de controle lido pelos robôs do Google. Não afeta a inclusão na Pesquisa Google e não é sinal de ranking. O Google diz que pretende aceitar o sinal AIPREF de preferência de treino no início de 2027.

- **Se for bloqueado:** O conteúdo deixa de ser usado no treino dos próximos modelos Gemini e como base (grounding) das respostas dos apps Gemini e do Grounding with Google Search na Vertex AI.
- **Segue o robots.txt?** Não se aplica. Na documentação: “Google-Extended does not impact a site's inclusion in Google Search”
- **Como aparece no log:** n/d (token de controle, não aparece no log)
- **Como confirmar a origem:** n/d (token de controle)

### O que é o Google-Agent?

O `Google-Agent` é o robô do Google que visita páginas a pedido do usuário (Agentes do Google). Usado por agentes que rodam na infraestrutura do Google para navegar na web e agir a pedido do usuário.

- **Se for bloqueado:** Sem efeito garantido: o Google diz que as buscas pedidas pelo usuário em geral ignoram o robots.txt.
- **Segue o robots.txt?** Em geral não segue. Na documentação: “these fetchers generally ignore robots.txt rules”
- **Como aparece no log:** `Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko; compatible; Google-Agent; +https://developers.google.com/crawling/docs/crawlers-fetchers/google-agent) Chrome/W.X.Y.Z Safari/537.36`
- **Como confirmar a origem:** [lista oficial de IPs](https://developers.google.com/static/crawling/ipranges/user-triggered-fetchers.json)

### O que é o Google-GeminiNotebook?

O `Google-GeminiNotebook` é o robô do Google que visita páginas a pedido do usuário (Gemini Notebook). Busca as URLs que o usuário adiciona como fonte nos projetos do Gemini Notebook. Substitui o token Google-NotebookLM, aceito até agosto de 2026.

- **Se for bloqueado:** Sem efeito garantido: o Google diz que as buscas pedidas pelo usuário em geral ignoram o robots.txt.
- **Segue o robots.txt?** Em geral não segue. Na documentação: “these fetchers generally ignore robots.txt rules”
- **Como aparece no log:** `Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/137.0.0.0 Safari/537.36 (compatible; Google-GeminiNotebook; +https://developers.google.com/crawling/docs/crawlers-fetchers/google-gemininotebook)`
- **Como confirmar a origem:** [lista oficial de IPs](https://developers.google.com/static/crawling/ipranges/user-triggered-fetchers.json)

## Quais são os robôs da OpenAI?

A base traz 3 robôs da OpenAI: `GPTBot`, `OAI-SearchBot` e `ChatGPT-User`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`GPTBot`](#o-que-é-o-gptbot) | Treino | Bloqueio documentado |
| [`OAI-SearchBot`](#o-que-é-o-oai-searchbot) | Busca | Bloqueio documentado |
| [`ChatGPT-User`](#o-que-é-o-chatgpt-user) | Visita a pedido do usuário | Pode não seguir |

Documentação oficial: [página da OpenAI sobre os seus robôs](https://developers.openai.com/api/docs/bots), conferida em 09/11/2026. Mudanças recentes: [Atualizações do ChatGPT](https://triwi.com.br/atualizacoes/chatgpt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

### O que é o GPTBot?

O `GPTBot` é o robô de treino da OpenAI (ChatGPT). Regra independente da do OAI-SearchBot. Se os dois robôs estiverem liberados, a OpenAI pode usar uma só coleta para os dois usos.

- **Se for bloqueado:** O conteúdo deixa de ser coletado para treinar os modelos de fundação da OpenAI. O site continua elegível para a busca do ChatGPT.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “Disallowing GPTBot indicates a site’s content should not be used in training”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.4; +https://openai.com/gptbot`
- **Como confirmar a origem:** [lista oficial de IPs](https://openai.com/gptbot.json)

### O que é o OAI-SearchBot?

O `OAI-SearchBot` é o robô de busca da OpenAI (ChatGPT). A OpenAI recomenda liberar este robô para aparecer nos resultados de busca. Mudanças no robots.txt levam cerca de 24 horas para valer na busca.

- **Se for bloqueado:** O site deixa de aparecer nos resultados de busca do ChatGPT.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “we recommend allowing OAI-SearchBot in your site’s robots.txt file”
- **Como aparece no log:** `compatible; OAI-SearchBot/1.4; +https://openai.com/searchbot`
- **Como confirmar a origem:** [lista oficial de IPs](https://openai.com/searchbot.json)

### O que é o ChatGPT-User?

O `ChatGPT-User` é o robô da OpenAI que visita páginas a pedido do usuário (ChatGPT). Não rastreia a web de forma automática e não decide se o site aparece na busca do ChatGPT; para isso, vale o OAI-SearchBot.

- **Se for bloqueado:** Sem efeito garantido: por ser acionado pelo usuário, a empresa avisa que este robô pode não seguir o robots.txt.
- **Segue o robots.txt?** Pode não seguir. Na documentação: “Because these actions are initiated by a user, robots.txt rules may not apply.”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +https://openai.com/bot`
- **Como confirmar a origem:** [lista oficial de IPs](https://openai.com/chatgpt-user.json)

## Quais são os robôs da Anthropic?

A base traz 3 robôs da Anthropic: `ClaudeBot`, `Claude-SearchBot` e `Claude-User`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`ClaudeBot`](#o-que-é-o-claudebot) | Treino | Sim, declarado |
| [`Claude-SearchBot`](#o-que-é-o-claude-searchbot) | Busca | Sim, declarado |
| [`Claude-User`](#o-que-é-o-claude-user) | Visita a pedido do usuário | Sim, declarado |

Documentação oficial: [página da Anthropic sobre os seus robôs](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Claude](https://triwi.com.br/atualizacoes/claude/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

### O que é o ClaudeBot?

O `ClaudeBot` é o robô de treino da Anthropic (Claude). Quando o robots.txt cita o ClaudeBot pelo nome, a Anthropic segue essa regra mesmo que a regra geral diga outra coisa.

- **Se for bloqueado:** O conteúdo publicado dali em diante deixa de entrar nos dados de treino dos modelos da Anthropic.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “If your robots.txt file names ClaudeBot, we follow that rule”
- **Como aparece no log:** n/d (a documentação não publica a frase completa)
- **Como confirmar a origem:** [lista oficial de IPs](https://claude.com/crawling/bots.json)

### O que é o Claude-SearchBot?

O `Claude-SearchBot` é o robô de busca da Anthropic (Claude). Rastreia a web para melhorar a relevância e a precisão das respostas de busca do Claude.

- **Se for bloqueado:** O site deixa de ser indexado para a busca do Claude, o que pode reduzir a visibilidade nas respostas.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “Anthropic’s Bots respect “do not crawl” signals by honoring industry standard directives in robots.txt.”
- **Como aparece no log:** n/d (a documentação não publica a frase completa)
- **Como confirmar a origem:** [lista oficial de IPs](https://claude.com/crawling/bots.json)

### O que é o Claude-User?

O `Claude-User` é o robô da Anthropic que visita páginas a pedido do usuário (Claude). A Anthropic declara que os seus robôs respeitam as diretivas padrão do robots.txt, inclusive este.

- **Se for bloqueado:** O Claude deixa de buscar páginas do site quando a pergunta de um usuário pede, o que pode reduzir a visibilidade nessas respostas.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “Anthropic’s Bots respect “do not crawl” signals by honoring industry standard directives in robots.txt.”
- **Como aparece no log:** n/d (a documentação não publica a frase completa)
- **Como confirmar a origem:** [lista oficial de IPs](https://claude.com/crawling/bots.json)

## Quais são os robôs da Microsoft?

A base traz 1 robô da Microsoft: `Bingbot`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`Bingbot`](#o-que-é-o-bingbot) | Busca | Bloqueio documentado |

Documentação oficial: [página da Microsoft sobre os seus robôs](https://www.bing.com/webmasters/help/which-crawlers-does-bing-use-8c184ec0), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Copilot](https://triwi.com.br/atualizacoes/copilot/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

### O que é o Bingbot?

O `Bingbot` é o robô de busca da Microsoft (Bing). Rastreador padrão do Bing. A Microsoft indica o robots.txt e o controle de rastreamento do Bing Webmaster Tools para controlar os seus robôs. A página não trata de treino de IA.

- **Se for bloqueado:** O site deixa de ser rastreado para o índice do Bing.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “Robots.txt files can be configured to tell Bing crawlers how to interact (...)”
- **Como aparece no log:** `Mozilla/5.0 (compatible; bingbot/2.0; +http://www.bing.com/bingbot.htm)`
- **Como confirmar a origem:** [método oficial de verificação](https://www.bing.com/webmasters/help/how-to-verify-bingbot-3905dc26)

## Quais são os robôs do Perplexity?

A base traz 2 robôs do Perplexity: `PerplexityBot` e `Perplexity-User`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`PerplexityBot`](#o-que-é-o-perplexitybot) | Busca | Bloqueio documentado |
| [`Perplexity-User`](#o-que-é-o-perplexity-user) | Visita a pedido do usuário | Em geral não segue |

Documentação oficial: [página do Perplexity sobre os seus robôs](https://docs.perplexity.ai/guides/bots), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Perplexity](https://triwi.com.br/atualizacoes/perplexity/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

### O que é o PerplexityBot?

O `PerplexityBot` é o robô de busca do Perplexity (Perplexity). Segundo a empresa, não é usado para coletar conteúdo para modelos de fundação de IA.

- **Se for bloqueado:** O site deixa de aparecer e de ser linkado nos resultados do Perplexity.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “we recommend allowing PerplexityBot in your site's robots.txt file”
- **Como aparece no log:** `Mozilla/5.0 (compatible; PerplexityBot/1.0; +https://perplexity.ai/perplexitybot)`
- **Como confirmar a origem:** [lista oficial de IPs](https://www.perplexity.ai/perplexitybot.json)

### O que é o Perplexity-User?

O `Perplexity-User` é o robô do Perplexity que visita páginas a pedido do usuário (Perplexity). Visita a página para ajudar a responder a pergunta do usuário e pode linkar a página na resposta. Não rastreia a web nem coleta conteúdo para treino.

- **Se for bloqueado:** Sem efeito garantido: a empresa diz que este robô em geral ignora o robots.txt, porque a visita foi pedida pelo usuário.
- **Segue o robots.txt?** Em geral não segue. Na documentação: “this fetcher generally ignores robots.txt rules”
- **Como aparece no log:** `Mozilla/5.0 (compatible; Perplexity-User/1.0; +https://perplexity.ai/perplexity-user)`
- **Como confirmar a origem:** [lista oficial de IPs](https://www.perplexity.ai/perplexity-user.json)

## Quais são os robôs da Meta?

A base traz 3 robôs da Meta: `meta-externalagent`, `meta-webindexer` e `meta-externalfetcher`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`meta-externalagent`](#o-que-é-o-meta-externalagent) | Treino | Bloqueio documentado |
| [`meta-webindexer`](#o-que-é-o-meta-webindexer) | Busca | Bloqueio documentado |
| [`meta-externalfetcher`](#o-que-é-o-meta-externalfetcher) | Visita a pedido do usuário | Pode não seguir |

Documentação oficial: [página da Meta sobre os seus robôs](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Meta AI](https://triwi.com.br/atualizacoes/meta-ai/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

### O que é o meta-externalagent?

O `meta-externalagent` é o robô de treino da Meta (Meta AI e outros produtos da Meta). A Meta descreve dois usos: treino de modelos de fundação e melhoria de produtos com indexação direta do conteúdo. Mudanças no robots.txt podem levar até 24 horas para valer.

- **Se for bloqueado:** O conteúdo deixa de ser coletado para treinar os modelos de fundação da Meta e para a indexação direta em produtos da empresa.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “add a disallow for the relevant crawler to robots.txt”
- **Como aparece no log:** `meta-externalagent/1.1 (+https://developers.facebook.com/docs/sharing/webmasters/crawler)`
- **Como confirmar a origem:** Consulta whois das rotas do AS32934, método descrito na documentação

### O que é o meta-webindexer?

O `meta-webindexer` é o robô de busca da Meta (Meta AI). Navega na web para melhorar a qualidade dos resultados de busca da Meta AI. A Meta diz que liberar este robô ajuda a citar e linkar o conteúdo nas respostas.

- **Se for bloqueado:** Reduz a chance de a Meta AI citar e linkar o site nas respostas.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “Allowing Meta-WebIndexer in your robots.txt file helps us cite and link to your content”
- **Como aparece no log:** `meta-webindexer/1.1 (+https://developers.facebook.com/docs/sharing/webmasters/crawler)`
- **Como confirmar a origem:** Consulta whois das rotas do AS32934, método descrito na documentação

### O que é o meta-externalfetcher?

O `meta-externalfetcher` é o robô da Meta que visita páginas a pedido do usuário (Meta AI). Busca links individuais a pedido do usuário, inclusive para ajudar a IA a navegar em sites e concluir tarefas.

- **Se for bloqueado:** Sem efeito garantido: por ser acionado pelo usuário, a empresa avisa que este robô pode não seguir o robots.txt.
- **Segue o robots.txt?** Pode não seguir. Na documentação: “this crawler may bypass robots.txt rules”
- **Como aparece no log:** `meta-externalfetcher/1.1 (+https://developers.facebook.com/docs/sharing/webmasters/crawler)`
- **Como confirmar a origem:** Consulta whois das rotas do AS32934, método descrito na documentação

## Quais são os robôs da Apple?

A base traz 2 robôs da Apple: `Applebot` e `Applebot-Extended`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`Applebot`](#o-que-é-o-applebot) | Busca | Sim, declarado |
| [`Applebot-Extended`](#o-que-é-o-applebot-extended) | Treino | Não se aplica |

Documentação oficial: [página da Apple sobre os seus robôs](https://support.apple.com/en-us/119829), conferida em 09/11/2026.

### O que é o Applebot?

O `Applebot` é o robô de busca da Apple (Pesquisa da Apple, Siri e Spotlight). Se o robots.txt não tem regra para o Applebot mas tem para o Googlebot, o Applebot segue as regras do Googlebot. Não segue crawl-delay.

- **Se for bloqueado:** O conteúdo deixa de aparecer nos resultados de busca da Apple.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “Applebot respects standard robots.txt directives in general search crawls”
- **Como aparece no log:** `Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.4 Safari/605.1.15 (Applebot/0.1; +http://www.apple.com/go/applebot)`
- **Como confirmar a origem:** [lista oficial de IPs](http://search.developer.apple.com/applebot.json)

### O que é o Applebot-Extended?

O `Applebot-Extended` é o token de controle de treino da Apple (Modelos de fundação da Apple). Não rastreia páginas: é um controle adicional sobre como a Apple pode usar o conteúdo. A regra para o Applebot-Extended não pesa no ranking da busca da Apple.

- **Se for bloqueado:** O conteúdo deixa de ser usado no treino dos modelos de fundação da Apple. O site continua nos resultados de busca da Apple.
- **Segue o robots.txt?** Não se aplica. Na documentação: “Applebot-Extended does not crawl webpages.”
- **Como aparece no log:** n/d (token de controle, não aparece no log)
- **Como confirmar a origem:** n/d (token de controle)

## Quais são os robôs da Amazon?

A base traz 3 robôs da Amazon: `Amazonbot`, `Amzn-SearchBot` e `Amzn-User`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`Amazonbot`](#o-que-é-o-amazonbot) | Treino | Sim, declarado |
| [`Amzn-SearchBot`](#o-que-é-o-amzn-searchbot) | Busca | Sim, declarado |
| [`Amzn-User`](#o-que-é-o-amzn-user) | Visita a pedido do usuário | Pode não seguir |

Documentação oficial: [página da Amazon sobre os seus robôs](https://developer.amazon.com/amazonbot), conferida em 09/11/2026.

### O que é o Amazonbot?

O `Amazonbot` é o robô de treino da Amazon (Produtos e serviços da Amazon). A Amazon declara que o rastreamento automático dos seus robôs segue o Robots Exclusion Protocol, usa uma cópia do robots.txt de até 30 dias e não aceita crawl-delay.

- **Se for bloqueado:** O conteúdo deixa de ser coletado para melhorar produtos e serviços da Amazon e para treinar modelos de IA da Amazon.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “Automated crawling from these listed user agents respects the Robots Exclusion Protocol.”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Amazonbot/0.1) Chrome/W.X.Y.Z Safari/537.36`
- **Como confirmar a origem:** [lista oficial de IPs](https://developer.amazon.com/amazonbot/ip-addresses/)

### O que é o Amzn-SearchBot?

O `Amzn-SearchBot` é o robô de busca da Amazon (Alexa e outras buscas da Amazon). Não rastreia para treino de IA generativa. Se o robots.txt dá regras a outros robôs de busca e não cita o Amzn-SearchBot, ele segue as regras dadas aos outros robôs de busca.

- **Se for bloqueado:** O site deixa de ser usado nas experiências de busca dos produtos da Amazon, como a Alexa.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “Automated crawling from these listed user agents respects the Robots Exclusion Protocol.”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Amzn-SearchBot/0.1) Chrome/W.X.Y.Z Safari/537.36`
- **Como confirmar a origem:** [lista oficial de IPs](https://developer.amazon.com/amazonbot/searchbot-ip-addresses/)

### O que é o Amzn-User?

O `Amzn-User` é o robô da Amazon que visita páginas a pedido do usuário (Alexa). Busca informação atual na web para responder perguntas na Alexa. Não é usado para treino de IA generativa.

- **Se for bloqueado:** Sem efeito garantido: por ser acionado pelo usuário, a empresa avisa que este robô pode não seguir o robots.txt.
- **Segue o robots.txt?** Pode não seguir. Na documentação: “may not follow all robots.txt directives”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Amzn-User/0.1) Chrome/W.X.Y.Z Safari/537.36`
- **Como confirmar a origem:** [lista oficial de IPs](https://developer.amazon.com/amazonbot/live-ip-addresses/)

## Quais são os robôs da Mistral AI?

A base traz 3 robôs da Mistral AI: `MistralAI-Training`, `MistralAI-Index` e `MistralAI-User`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`MistralAI-Training`](#o-que-é-o-mistralai-training) | Treino | Bloqueio documentado |
| [`MistralAI-Index`](#o-que-é-o-mistralai-index) | Busca | Bloqueio documentado |
| [`MistralAI-User`](#o-que-é-o-mistralai-user) | Visita a pedido do usuário | Sim, declarado |

Documentação oficial: [página da Mistral AI sobre os seus robôs](https://docs.mistral.ai/robots), conferida em 09/11/2026.

### O que é o MistralAI-Training?

O `MistralAI-Training` é o robô de treino da Mistral AI (Vibe). Não é usado para indexação de busca nem para responder perguntas ao vivo no Vibe.

- **Se for bloqueado:** O conteúdo deixa de entrar nos conjuntos de dados de treino dos modelos de IA generativa da Mistral.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “Webmasters can disallow this user agent in their robots.txt file.”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; MistralAI-Training/1.0; +https://docs.mistral.ai/robots)`
- **Como confirmar a origem:** n/d (a documentação não publica faixas de IP deste robô)

### O que é o MistralAI-Index?

O `MistralAI-Index` é o robô de busca da Mistral AI (Vibe). Segundo a empresa, o conteúdo coletado por este robô não é usado em treino de IA generativa de nenhum tipo.

- **Se for bloqueado:** O site deixa de ser indexado para a busca da Mistral, que ajuda a responder perguntas no Vibe.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “Mistral uses specific robots.txt tags”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; MistralAI-Index/1.0; +https://docs.mistral.ai/robots)`
- **Como confirmar a origem:** [lista oficial de IPs](https://mistral.ai/mistralai-index-ips.json)

### O que é o MistralAI-User?

O `MistralAI-User` é o robô da Mistral AI que visita páginas a pedido do usuário (Vibe). A Mistral diz que este token define em quais sites as visitas pedidas por usuários podem ser feitas. Não rastreia a web de forma automática nem coleta conteúdo para treino.

- **Se for bloqueado:** O Vibe deixa de visitar o site para responder perguntas de usuários.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “MistralAI-User governs which sites these user requests can be made to.”
- **Como aparece no log:** `Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; MistralAI-User/1.0; +https://docs.mistral.ai/robots)`
- **Como confirmar a origem:** [lista oficial de IPs](https://mistral.ai/mistralai-user-ips.json)

## Quais são os robôs do DuckDuckGo?

A base traz 2 robôs do DuckDuckGo: `DuckDuckBot` e `DuckAssistBot`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`DuckDuckBot`](#o-que-é-o-duckduckbot) | Busca | Sim, declarado |
| [`DuckAssistBot`](#o-que-é-o-duckassistbot) | Busca | Bloqueio documentado |

Documentação oficial: [página sobre `DuckDuckBot`](https://duckduckgo.com/duckduckgo-help-pages/results/duckduckbot) e [página sobre `DuckAssistBot`](https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot), conferidas em 09/11/2026.

### O que é o DuckDuckBot?

O `DuckDuckBot` é o robô de busca do DuckDuckGo (Busca do DuckDuckGo). A página oficial não diz se o conteúdo é usado em treino de IA.

- **Se for bloqueado:** O site deixa de ser rastreado para os resultados de busca do DuckDuckGo.
- **Segue o robots.txt?** Sim, declarado. Na documentação: “DuckDuckBot respects https://robotstxt.org/”
- **Como aparece no log:** `DuckDuckBot/1.1; (+http://duckduckgo.com/duckduckbot.html)`
- **Como confirmar a origem:** [lista oficial de IPs](https://duckduckgo.com/duckduckbot.json)

### O que é o DuckAssistBot?

O `DuckAssistBot` é o robô de busca do DuckDuckGo (Respostas com IA do DuckDuckGo). Busca páginas em tempo real para as respostas com IA. Segundo a empresa, os dados não são usados para treinar modelos de IA.

- **Se for bloqueado:** O site deixa de ser usado nas respostas com IA do DuckDuckGo, que citam as fontes. A mudança vale depois de 72 horas e não afeta a posição na busca orgânica.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “the change will take effect after 72 hours”
- **Como aparece no log:** `DuckAssistBot/1.2; (+http://duckduckgo.com/duckassistbot.html)`
- **Como confirmar a origem:** [lista oficial de IPs](https://duckduckgo.com/duckassistbot.json)

## Quais são os robôs da Common Crawl?

A base traz 1 robô da Common Crawl: `CCBot`.

| Robô (user-agent) | Função | Segue o robots.txt? |
|:---|:---|:---|
| [`CCBot`](#o-que-é-o-ccbot) | Arquivo aberto da web | Bloqueio documentado |

Documentação oficial: [página da Common Crawl sobre os seus robôs](https://commoncrawl.org/ccbot), conferida em 09/11/2026.

### O que é o CCBot?

O `CCBot` é o robô do arquivo aberto da Common Crawl (Arquivo aberto da Common Crawl). A página oficial ensina o bloqueio pelo robots.txt e não trata de treino de IA. O arquivo da Common Crawl é aberto a qualquer pessoa.

- **Se for bloqueado:** O site deixa de entrar nas próximas coletas do arquivo aberto da Common Crawl.
- **Segue o robots.txt?** Bloqueio documentado. Na documentação: “To prevent Common Crawl from crawling your website, include the following in your robots.txt”
- **Como aparece no log:** `CCBot/2.0 (https://commoncrawl.org/faq/)`
- **Como confirmar a origem:** [lista oficial de IPs](https://index.commoncrawl.org/ccbot.json)

## Como os robôs se dividem por função?

| Função | O que faz | Robôs na base | Exemplos |
|:---|:---|:---|:---|
| Treino | Coleta conteúdo que pode ser usado para treinar modelos de IA, ou é o token que controla esse uso | 7 | `Google-Extended`, `GPTBot`, `ClaudeBot` e `meta-externalagent` |
| Busca | Rastreia e indexa páginas para a busca do buscador ou da IA, de onde saem as citações e os links das respostas | 11 | `Googlebot`, `OAI-SearchBot`, `Claude-SearchBot` e `Bingbot` |
| Visita a pedido do usuário | Abre uma página na hora em que um usuário pede, para responder ou executar uma tarefa | 8 | `Google-Agent`, `Google-GeminiNotebook`, `ChatGPT-User` e `Claude-User` |
| Arquivo aberto da web | Coleta páginas para um arquivo público da web, aberto a qualquer pessoa | 1 | `CCBot` |
| **Total** | | **27** | |

A divisão importa porque o efeito do bloqueio muda com a função. Bloquear um robô de treino não tira o site das respostas da IA, segundo as documentações. Bloquear um robô de busca pode tirar. E bloquear um robô de visita a pedido do usuário pode nem ter efeito, porque vários deles não seguem o robots.txt.

## Por que alguns robôs não estão nesta lista?

A lista só aceita robô com documentação oficial publicada pela própria empresa, com o nome do robô e para que ele serve. Robôs que aparecem em listas de terceiros sem página oficial ficam fora até que a empresa documente; quando isso acontecer, entram na base com a data da verificação. Robôs de anúncio, de prévia de link e de verificação de propriedade também ficam fora, porque não decidem a presença da marca nas buscas e nas IAs.

Para robôs fora da lista, o grupo `User-agent: *` do robots.txt define a regra geral, e o bloqueio no servidor ou na CDN cobre os que não seguem o arquivo.

## Como confirmar que a visita é de um robô verdadeiro?

O user-agent é só um texto enviado na visita, e qualquer um pode imitá-lo. As próprias empresas avisam isso e oferecem formas de conferir, e o bloco de cada robô acima traz o link: 21 dos 27 robôs têm lista oficial de IPs ou método de verificação publicado. Google, Bing e Common Crawl também aceitam a conferência por DNS reverso, e a Meta indica a consulta das rotas da rede dela. Para ver quais robôs visitam o site e quais páginas eles leem, use o [Analisador de logs para SEO da TRIWI](https://triwi.com.br/ferramentas/analisador-de-logs-para-seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos).

## Perguntas frequentes

<details>
<summary><strong>O que significa bloqueio documentado?</strong></summary>

Que a empresa ensina a bloquear o robô pelo robots.txt, mas não diz com todas as letras que ele segue o arquivo. É diferente de Sim, declarado, quando a documentação afirma que o robô obedece às regras. Na base, são 9 robôs com declaração e 10 com bloqueio documentado; o trecho de cada documentação está no bloco do robô.
</details>

<details>
<summary><strong>Qual a diferença entre ClaudeBot, Claude-SearchBot e Claude-User?</strong></summary>

O `ClaudeBot` coleta conteúdo que pode ser usado no treino dos modelos da Anthropic; o `Claude-SearchBot` rastreia a web para a busca do Claude; o `Claude-User` abre páginas quando a pergunta de um usuário pede. A Anthropic declara que os três respeitam o robots.txt, e bloquear os dois últimos pode reduzir a visibilidade nas respostas do Claude.
</details>

<details>
<summary><strong>Por que alguns robôs não têm a frase completa do log?</strong></summary>

Porque a empresa não publica. A Anthropic, por exemplo, documenta o nome dos três robôs e a lista de IPs, mas não a frase completa do user-agent. Os tokens de controle, como o `Google-Extended` e o `Applebot-Extended`, não aparecem no log porque não fazem visitas.
</details>

<details>
<summary><strong>Os robôs que visitam a pedido do usuário podem ser bloqueados?</strong></summary>

No robots.txt, só em parte. `Google-Agent`, `Google-GeminiNotebook`, `ChatGPT-User`, `Perplexity-User`, `meta-externalfetcher` e `Amzn-User` podem não seguir o arquivo, segundo as próprias empresas, porque a visita foi pedida por uma pessoa. Para barrá-los de fato, o bloqueio tem que ser feito no servidor ou na CDN, como explica o [Guia de GEO da TRIWI](https://triwi.com.br/guias/geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos).
</details>

**Ver também na Base de Conhecimento da TRIWI:** [Crawling e Indexação: Como Garantir que o Google Encontre Seu Site](https://github.com/TRIWI-SEO/SEO-IA/blob/main/seo-tecnico/crawling-e-indexacao-como-garantir-que-o-google-encontre-seu-site.md), [Otimização para Perplexity, Claude e Outras IAs de Busca](https://github.com/TRIWI-SEO/SEO-IA/blob/main/geo-seo-para-ia/otimizacao-para-perplexity-claude-e-outras-ias-de-busca.md), [SEO para IA: Como Aparecer nas Respostas do ChatGPT, Gemini e Claude](https://github.com/TRIWI-SEO/SEO-IA/blob/main/geo-seo-para-ia/seo-para-ia-como-aparecer-nas-respostas-do-chatgpt-gemini-e-claude.md).

**Ver também no Glossário da TRIWI:** [Rastreadores de IA](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos#seo-rastreadores-de-ia), [Robots.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos#seo-robots-txt), [llms.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos#seo-llms-txt), [GEO](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos#seo-geo), [AI Overviews](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos#seo-ai-overviews), [Grounding](https://triwi.com.br/glossario/inteligencia-artificial/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos#ia-grounding).

[Voltar para o início](README.md)

---

<p align="center">
  <strong>Quando alguém pergunta à IA sobre o seu mercado, ela cita a sua empresa?</strong><br>
  <a href="https://triwi.com.br/contato/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos">Que tal um café com a TRIWI?</a>
</p>

<p align="center">
  <sub>Base publicada e mantida pela equipe da TRIWI, agência 100% especializada em SEO e Otimização para IAs.</sub>
</p>
