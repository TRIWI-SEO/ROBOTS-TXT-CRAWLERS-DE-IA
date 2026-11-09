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

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `Googlebot` | Busca | Sim | O site deixa de ser rastreado para a Pesquisa Google e, com isso, sai também dos AI Overviews e do Modo IA, que só usam páginas indexadas na Pesquisa. | Os rastreadores comuns do Google seguem o robots.txt no rastreamento automático. Para limitar o que aparece nos recursos de IA da busca, o Google indica nosnippet, data-nosnippet, max-snippet e noindex. |
| `Google-Extended` | Treino | Não se aplica | O conteúdo deixa de ser usado no treino dos próximos modelos Gemini e como base (grounding) das respostas dos apps Gemini e do Grounding with Google Search na Vertex AI. | Não é um robô: é um token de controle lido pelos robôs do Google. Não afeta a inclusão na Pesquisa Google e não é sinal de ranking. O Google diz que pretende aceitar o sinal AIPREF de preferência de treino no início de 2027. |
| `Google-Agent` | Visita a pedido do usuário | Em geral não segue | Sem efeito garantido: o Google diz que as buscas pedidas pelo usuário em geral ignoram o robots.txt. | Usado por agentes que rodam na infraestrutura do Google para navegar na web e agir a pedido do usuário. |
| `Google-GeminiNotebook` | Visita a pedido do usuário | Em geral não segue | Sem efeito garantido: o Google diz que as buscas pedidas pelo usuário em geral ignoram o robots.txt. | Busca as URLs que o usuário adiciona como fonte nos projetos do Gemini Notebook. Substitui o token Google-NotebookLM, aceito até agosto de 2026. |

Documentação oficial: [página sobre `Googlebot` e `Google-Extended`](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) e [página sobre `Google-Agent` e `Google-GeminiNotebook`](https://developers.google.com/crawling/docs/crawlers-fetchers/google-user-triggered-fetchers), conferidas em 09/11/2026. Mudanças recentes: [Atualizações do Google](https://triwi.com.br/atualizacoes/google/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos) e [Atualizações do Gemini](https://triwi.com.br/atualizacoes/gemini/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

## Quais são os robôs da OpenAI?

A base traz 3 robôs da OpenAI: `GPTBot`, `OAI-SearchBot` e `ChatGPT-User`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `GPTBot` | Treino | Sim | O conteúdo deixa de ser coletado para treinar os modelos de fundação da OpenAI. O site continua elegível para a busca do ChatGPT. | Regra independente da do OAI-SearchBot. Se os dois robôs estiverem liberados, a OpenAI pode usar uma só coleta para os dois usos. |
| `OAI-SearchBot` | Busca | Sim | O site deixa de aparecer nos resultados de busca do ChatGPT. | A OpenAI recomenda liberar este robô para aparecer nos resultados de busca. Mudanças no robots.txt levam cerca de 24 horas para valer na busca. |
| `ChatGPT-User` | Visita a pedido do usuário | Pode não seguir | Sem efeito garantido: por ser acionado pelo usuário, a empresa avisa que este robô pode não seguir o robots.txt. | Não rastreia a web de forma automática e não decide se o site aparece na busca do ChatGPT; para isso, vale o OAI-SearchBot. |

Documentação oficial: [página da OpenAI sobre os seus robôs](https://developers.openai.com/api/docs/bots), conferida em 09/11/2026. Mudanças recentes: [Atualizações do ChatGPT](https://triwi.com.br/atualizacoes/chatgpt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

## Quais são os robôs da Anthropic?

A base traz 3 robôs da Anthropic: `ClaudeBot`, `Claude-SearchBot` e `Claude-User`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `ClaudeBot` | Treino | Sim | O conteúdo publicado dali em diante deixa de entrar nos dados de treino dos modelos da Anthropic. | Quando o robots.txt cita o ClaudeBot pelo nome, a Anthropic segue essa regra mesmo que a regra geral diga outra coisa. |
| `Claude-SearchBot` | Busca | Sim | O site deixa de ser indexado para a busca do Claude, o que pode reduzir a visibilidade nas respostas. | Rastreia a web para melhorar a relevância e a precisão das respostas de busca do Claude. |
| `Claude-User` | Visita a pedido do usuário | Sim | O Claude deixa de buscar páginas do site quando a pergunta de um usuário pede, o que pode reduzir a visibilidade nessas respostas. | A Anthropic declara que os seus robôs respeitam as diretivas padrão do robots.txt, inclusive este. |

Documentação oficial: [página da Anthropic sobre os seus robôs](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Claude](https://triwi.com.br/atualizacoes/claude/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

## Quais são os robôs da Microsoft?

A base traz 1 robô da Microsoft: `Bingbot`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `Bingbot` | Busca | Sim | O site deixa de ser rastreado para o índice do Bing. | Rastreador padrão do Bing. A Microsoft indica o robots.txt e o controle de rastreamento do Bing Webmaster Tools para controlar os seus robôs. A página não trata de treino de IA. |

Documentação oficial: [página da Microsoft sobre os seus robôs](https://www.bing.com/webmasters/help/which-crawlers-does-bing-use-8c184ec0), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Copilot](https://triwi.com.br/atualizacoes/copilot/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

## Quais são os robôs do Perplexity?

A base traz 2 robôs do Perplexity: `PerplexityBot` e `Perplexity-User`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `PerplexityBot` | Busca | Sim | O site deixa de aparecer e de ser linkado nos resultados do Perplexity. | Segundo a empresa, não é usado para coletar conteúdo para modelos de fundação de IA. |
| `Perplexity-User` | Visita a pedido do usuário | Em geral não segue | Sem efeito garantido: a empresa diz que este robô em geral ignora o robots.txt, porque a visita foi pedida pelo usuário. | Visita a página para ajudar a responder a pergunta do usuário e pode linkar a página na resposta. Não rastreia a web nem coleta conteúdo para treino. |

Documentação oficial: [página do Perplexity sobre os seus robôs](https://docs.perplexity.ai/guides/bots), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Perplexity](https://triwi.com.br/atualizacoes/perplexity/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

## Quais são os robôs da Meta?

A base traz 3 robôs da Meta: `meta-externalagent`, `meta-webindexer` e `meta-externalfetcher`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `meta-externalagent` | Treino | Sim | O conteúdo deixa de ser coletado para treinar os modelos de fundação da Meta e para a indexação direta em produtos da empresa. | A Meta descreve dois usos: treino de modelos de fundação e melhoria de produtos com indexação direta do conteúdo. Mudanças no robots.txt podem levar até 24 horas para valer. |
| `meta-webindexer` | Busca | Sim | Reduz a chance de a Meta AI citar e linkar o site nas respostas. | Navega na web para melhorar a qualidade dos resultados de busca da Meta AI. A Meta diz que liberar este robô ajuda a citar e linkar o conteúdo nas respostas. |
| `meta-externalfetcher` | Visita a pedido do usuário | Pode não seguir | Sem efeito garantido: por ser acionado pelo usuário, a empresa avisa que este robô pode não seguir o robots.txt. | Busca links individuais a pedido do usuário, inclusive para ajudar a IA a navegar em sites e concluir tarefas. |

Documentação oficial: [página da Meta sobre os seus robôs](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers), conferida em 09/11/2026. Mudanças recentes: [Atualizações do Meta AI](https://triwi.com.br/atualizacoes/meta-ai/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos), linhas do tempo da TRIWI.

## Quais são os robôs da Apple?

A base traz 2 robôs da Apple: `Applebot` e `Applebot-Extended`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `Applebot` | Busca | Sim | O conteúdo deixa de aparecer nos resultados de busca da Apple. | Se o robots.txt não tem regra para o Applebot mas tem para o Googlebot, o Applebot segue as regras do Googlebot. Não segue crawl-delay. |
| `Applebot-Extended` | Treino | Não se aplica | O conteúdo deixa de ser usado no treino dos modelos de fundação da Apple. O site continua nos resultados de busca da Apple. | Não rastreia páginas: é um controle adicional sobre como a Apple pode usar o conteúdo. A regra para o Applebot-Extended não pesa no ranking da busca da Apple. |

Documentação oficial: [página da Apple sobre os seus robôs](https://support.apple.com/en-us/119829), conferida em 09/11/2026.

## Quais são os robôs da Amazon?

A base traz 3 robôs da Amazon: `Amazonbot`, `Amzn-SearchBot` e `Amzn-User`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `Amazonbot` | Treino | Sim | O conteúdo deixa de ser coletado para melhorar produtos e serviços da Amazon e para treinar modelos de IA da Amazon. | A Amazon declara que o rastreamento automático dos seus robôs segue o Robots Exclusion Protocol, usa uma cópia do robots.txt de até 30 dias e não aceita crawl-delay. |
| `Amzn-SearchBot` | Busca | Sim | O site deixa de ser usado nas experiências de busca dos produtos da Amazon, como a Alexa. | Não rastreia para treino de IA generativa. Se o robots.txt dá regras a outros robôs de busca e não cita o Amzn-SearchBot, ele segue as regras dadas aos outros robôs de busca. |
| `Amzn-User` | Visita a pedido do usuário | Pode não seguir | Sem efeito garantido: por ser acionado pelo usuário, a empresa avisa que este robô pode não seguir o robots.txt. | Busca informação atual na web para responder perguntas na Alexa. Não é usado para treino de IA generativa. |

Documentação oficial: [página da Amazon sobre os seus robôs](https://developer.amazon.com/amazonbot), conferida em 09/11/2026.

## Quais são os robôs da Mistral AI?

A base traz 3 robôs da Mistral AI: `MistralAI-Training`, `MistralAI-Index` e `MistralAI-User`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `MistralAI-Training` | Treino | Sim | O conteúdo deixa de entrar nos conjuntos de dados de treino dos modelos de IA generativa da Mistral. | Não é usado para indexação de busca nem para responder perguntas ao vivo no Vibe. |
| `MistralAI-Index` | Busca | Sim | O site deixa de ser indexado para a busca da Mistral, que ajuda a responder perguntas no Vibe. | Segundo a empresa, o conteúdo coletado por este robô não é usado em treino de IA generativa de nenhum tipo. |
| `MistralAI-User` | Visita a pedido do usuário | Sim | O Vibe deixa de visitar o site para responder perguntas de usuários. | A Mistral diz que este token define em quais sites as visitas pedidas por usuários podem ser feitas. Não rastreia a web de forma automática nem coleta conteúdo para treino. |

Documentação oficial: [página da Mistral AI sobre os seus robôs](https://docs.mistral.ai/robots), conferida em 09/11/2026.

## Quais são os robôs do DuckDuckGo?

A base traz 2 robôs do DuckDuckGo: `DuckDuckBot` e `DuckAssistBot`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `DuckDuckBot` | Busca | Sim | O site deixa de ser rastreado para os resultados de busca do DuckDuckGo. | A página oficial não diz se o conteúdo é usado em treino de IA. |
| `DuckAssistBot` | Busca | Sim | O site deixa de ser usado nas respostas com IA do DuckDuckGo, que citam as fontes. A mudança vale depois de 72 horas e não afeta a posição na busca orgânica. | Busca páginas em tempo real para as respostas com IA. Segundo a empresa, os dados não são usados para treinar modelos de IA. |

Documentação oficial: [página sobre `DuckDuckBot`](https://duckduckgo.com/duckduckgo-help-pages/results/duckduckbot) e [página sobre `DuckAssistBot`](https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot), conferidas em 09/11/2026.

## Quais são os robôs da Common Crawl?

A base traz 1 robô da Common Crawl: `CCBot`.

| Robô (user-agent) | Função | Segue o robots.txt? | O que acontece se bloquear | Observação |
|:---|:---|:---|:---|:---|
| `CCBot` | Arquivo aberto da web | Sim | O site deixa de entrar nas próximas coletas do arquivo aberto da Common Crawl. | A página oficial ensina o bloqueio pelo robots.txt e não trata de treino de IA. O arquivo da Common Crawl é aberto a qualquer pessoa. |

Documentação oficial: [página da Common Crawl sobre os seus robôs](https://commoncrawl.org/ccbot), conferida em 09/11/2026.

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

O user-agent é só um texto enviado na visita, e qualquer um pode imitá-lo. As próprias empresas avisam isso e oferecem formas de conferir: Google e Bing têm métodos de verificação dos seus robôs, e OpenAI, Mistral e DuckDuckGo publicam as faixas de IP dos seus robôs. Para ver quais robôs visitam o site e quais páginas eles leem, use o [Analisador de logs para SEO da TRIWI](https://triwi.com.br/ferramentas/analisador-de-logs-para-seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=lista-de-robos).

## Perguntas frequentes

<details>
<summary><strong>O que é o OAI-SearchBot?</strong></summary>

É o robô da OpenAI que encontra e mostra sites nos recursos de busca do ChatGPT. É ele que decide se o site pode aparecer, com link, nas respostas com busca. A OpenAI recomenda deixá-lo liberado para aparecer nos resultados e diz que mudanças no robots.txt levam cerca de 24 horas para valer.
</details>

<details>
<summary><strong>Qual a diferença entre ClaudeBot, Claude-SearchBot e Claude-User?</strong></summary>

O `ClaudeBot` coleta conteúdo que pode ser usado no treino dos modelos da Anthropic; o `Claude-SearchBot` rastreia a web para a busca do Claude; o `Claude-User` abre páginas quando a pergunta de um usuário pede. A Anthropic declara que os três respeitam o robots.txt, e bloquear os dois últimos pode reduzir a visibilidade nas respostas do Claude.
</details>

<details>
<summary><strong>O que é o meta-externalagent?</strong></summary>

É o robô da Meta que coleta conteúdo para treinar modelos de fundação ou para melhorar produtos com indexação direta do conteúdo. A busca da Meta AI depende de outro robô, o `meta-webindexer`, que a Meta diz ajudar a citar e linkar o site nas respostas.
</details>

<details>
<summary><strong>O Applebot-Extended rastreia o site?</strong></summary>

Não. A Apple diz que o `Applebot-Extended` não rastreia páginas: é um controle sobre o uso do conteúdo no treino dos modelos de fundação da Apple. Bloqueá-lo não tira o site da busca da Apple, que depende do `Applebot`.
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
