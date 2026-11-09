# Robots.txt para IA: modelos prontos para liberar, bloquear o treino ou bloquear tudo

**Há quatro escolhas comuns de robots.txt para as IAs: liberar tudo, bloquear só o treino e manter a busca, bloquear as IAs e manter os buscadores, ou bloquear tudo. Para a empresa que quer ser citada pelo ChatGPT, pelo Claude, pelo Perplexity e pelos AI Overviews, o essencial é manter liberados os robôs de busca. Os quatro modelos abaixo são gerados a partir da base aberta de 27 robôs da TRIWI.**

Cada modelo vem com o arquivo pronto e o que muda, empresa por empresa, na presença da marca. Para adaptar ao seu site e testar as regras antes de publicar, use o [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt).

*Por equipe de SEO da TRIWI, com revisão de Ricardo Martins, fundador. Publicado em 09/11/2026. Atualizado em 09/11/2026.*

## Índice

- [Como o robots.txt funciona com os robôs de IA?](#como-o-robotstxt-funciona-com-os-robôs-de-ia)
- [Quais são os modelos de robots.txt para IA?](#quais-são-os-modelos-de-robotstxt-para-ia)
  - [Liberar tudo](#como-liberar-tudo-para-as-ias-no-robotstxt)
  - [Bloquear o treino e manter a busca](#como-bloquear-o-treino-de-ia-e-manter-a-busca)
  - [Bloquear as IAs e manter os buscadores](#como-bloquear-as-ias-e-manter-o-google-e-o-bing)
  - [Bloquear tudo](#como-bloquear-todos-os-robôs-no-robotstxt)
- [Qual modelo escolher?](#qual-modelo-escolher)
- [Como testar antes de publicar?](#como-testar-antes-de-publicar)
- [Perguntas frequentes](#perguntas-frequentes)

## Como o robots.txt funciona com os robôs de IA?

O robots.txt é um arquivo de texto na raiz do site, padronizado pela [RFC 9309](https://www.rfc-editor.org/rfc/rfc9309.html) da IETF. Ele é dividido em grupos: cada grupo começa com uma ou mais linhas `User-agent` e traz as regras `Allow` e `Disallow` daquele robô. Seis pontos decidem o resultado com as IAs:

| Ponto | Como funciona |
|:---|:---|
| Grupo próprio vence o geral | O robô segue o grupo que tem o nome dele e ignora o grupo `User-agent: *`. Quem cria um grupo para um robô precisa repetir ali as regras gerais que também valem para ele |
| Nome sem diferença de maiúscula | `GPTBot` e `gptbot` são o mesmo robô para a norma |
| Função de cada robô | Treino, busca e visita a pedido do usuário são robôs diferentes, com efeitos diferentes. A função de cada um está na [Lista de robôs de IA](lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md) |
| Tokens de controle | `Google-Extended` e `Applebot-Extended` não rastreiam nada: são nomes lidos pelos robôs do Google e da Apple para decidir o uso do conteúdo em IA |
| Visitas a pedido do usuário | 6 robôs da base podem não seguir o arquivo, segundo as próprias empresas |
| Rastrear não é indexar | O robots.txt impede a leitura da página, não a remove do índice; para isso existe o noindex |

## Quais são os modelos de robots.txt para IA?

Os quatro modelos estão abaixo, do mais aberto ao mais fechado. Todos usam `https://www.seusite.com.br/sitemap.xml` como exemplo de sitemap, para trocar pelo endereço do seu; se o site ainda não tem sitemap, o [Gerador de sitemap XML da TRIWI](https://triwi.com.br/ferramentas/gerador-de-sitemap-xml/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt) monta o arquivo.

### Como liberar tudo para as IAs no robots.txt?

**Todos os buscadores e IAs podem rastrear o site, para busca, para visitas a pedido do usuário e para treino.** A marca pode aparecer em todas as IAs e buscadores da base, e o conteúdo pode entrar no treino de modelos.

```text
# robots.txt modelo: Liberar tudo
# Todos os buscadores e IAs podem rastrear o site, para busca, para visitas a pedido do usuário e para treino.
# Gerado a partir da base aberta de robôs de IA da TRIWI, verificada em 09/11/2026:
# https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA
# Antes de publicar: troque o endereço do sitemap e acrescente as regras que o seu site já usa hoje.

User-agent: *
Allow: /

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Arquivo para baixar: [modelos/robots-txt-liberar-tudo.txt](modelos/robots-txt-liberar-tudo.txt).

#### O que muda na presença da marca com o modelo liberar tudo?

| Empresa | Busca e respostas da IA | Visitas a pedido do usuário | Treino de modelos |
|:---|:---|:---|:---|
| Google | Liberada | Liberadas | Liberado |
| OpenAI | Liberada | Liberadas | Liberado |
| Anthropic | Liberada | Liberadas | Liberado |
| Microsoft | Liberada | Sem robô na base | Sem robô de treino na base |
| Perplexity | Liberada | Liberadas | Sem robô de treino na base |
| Meta | Liberada | Liberadas | Liberado |
| Apple | Liberada | Sem robô na base | Liberado |
| Amazon | Liberada | Liberadas | Liberado |
| Mistral AI | Liberada | Liberadas | Liberado |
| DuckDuckGo | Liberada | Sem robô na base | Sem robô de treino na base |
| Common Crawl | Sem robô de busca na base | Sem robô na base | Liberado (arquivo aberto) |

- É o comportamento de quem não tem robots.txt ou tem um arquivo sem regras para robôs de IA.
- O conteúdo pode entrar no treino de modelos das empresas que coletam para isso, e pode ser lido em todas as buscas e visitas a pedido do usuário.

### Como bloquear o treino de IA e manter a busca?

**Os robôs e tokens de treino ficam sem acesso; os robôs de busca e de visita a pedido do usuário continuam liberados.** A marca continua citável na busca do ChatGPT, do Claude, do Perplexity, da Meta AI e nos AI Overviews; sai das próximas coletas de treino e da base (grounding) dos apps Gemini.

```text
# robots.txt modelo: Bloquear o treino e manter a busca
# Os robôs e tokens de treino ficam sem acesso; os robôs de busca e de visita a pedido do usuário continuam liberados.
# Gerado a partir da base aberta de robôs de IA da TRIWI, verificada em 09/11/2026:
# https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA
# Antes de publicar: troque o endereço do sitemap e acrescente as regras que o seu site já usa hoje.

# Treino de modelos de IA: sem acesso
User-agent: Google-Extended
User-agent: GPTBot
User-agent: ClaudeBot
User-agent: meta-externalagent
User-agent: Applebot-Extended
User-agent: Amazonbot
User-agent: MistralAI-Training
Disallow: /

# Arquivo aberto da web: sem acesso
User-agent: CCBot
Disallow: /

# Todos os outros robôs, inclusive os que não estão na base: liberados
# (Googlebot, Google-Agent, Google-GeminiNotebook, OAI-SearchBot, ChatGPT-User, Claude-SearchBot, Claude-User, Bingbot, PerplexityBot, Perplexity-User, meta-webindexer, meta-externalfetcher, Applebot, Amzn-SearchBot, Amzn-User, MistralAI-Index, MistralAI-User, DuckDuckBot, DuckAssistBot)
User-agent: *
Allow: /

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Arquivo para baixar: [modelos/robots-txt-bloquear-treino-manter-busca.txt](modelos/robots-txt-bloquear-treino-manter-busca.txt).

#### O que muda na presença da marca com o modelo bloquear o treino e manter a busca?

| Empresa | Busca e respostas da IA | Visitas a pedido do usuário | Treino de modelos |
|:---|:---|:---|:---|
| Google | Liberada | Liberadas | Bloqueado |
| OpenAI | Liberada | Liberadas | Bloqueado |
| Anthropic | Liberada | Liberadas | Bloqueado |
| Microsoft | Liberada | Sem robô na base | Sem robô de treino na base |
| Perplexity | Liberada | Liberadas | Sem robô de treino na base |
| Meta | Liberada | Liberadas | Bloqueado |
| Apple | Liberada | Sem robô na base | Bloqueado |
| Amazon | Liberada | Liberadas | Bloqueado |
| Mistral AI | Liberada | Liberadas | Bloqueado |
| DuckDuckGo | Liberada | Sem robô na base | Sem robô de treino na base |
| Common Crawl | Sem robô de busca na base | Sem robô na base | Bloqueado (arquivo aberto) |

- O `Google-Extended` controla, além do treino, o uso do conteúdo como base (grounding) das respostas dos apps Gemini e da Vertex AI. Bloqueá-lo não mexe nos AI Overviews nem no Modo IA, mas pode reduzir a presença da marca no app Gemini.
- O `meta-externalagent` também serve à indexação direta em produtos da Meta, não só ao treino.
- O `CCBot` entra no bloqueio porque alimenta um arquivo aberto da web, que qualquer pessoa pode baixar.
- O bloqueio vale para as coletas seguintes: não remove o conteúdo de modelos já treinados.

### Como bloquear as IAs e manter o Google e o Bing?

**Só `Googlebot`, `Bingbot`, `Applebot` e `DuckDuckBot` continuam com acesso; todos os outros robôs da base ficam bloqueados.** A marca continua no Google, inclusive nos AI Overviews e no Modo IA, e no Bing; sai da busca do ChatGPT, do Claude, do Perplexity, da Meta AI e da Mistral.

```text
# robots.txt modelo: Bloquear as IAs e manter os buscadores
# Só Googlebot, Bingbot, Applebot e DuckDuckBot continuam com acesso; todos os outros robôs da base ficam bloqueados.
# Gerado a partir da base aberta de robôs de IA da TRIWI, verificada em 09/11/2026:
# https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA
# Antes de publicar: troque o endereço do sitemap e acrescente as regras que o seu site já usa hoje.

# Treino de modelos de IA: sem acesso
User-agent: Google-Extended
User-agent: GPTBot
User-agent: ClaudeBot
User-agent: meta-externalagent
User-agent: Applebot-Extended
User-agent: Amazonbot
User-agent: MistralAI-Training
Disallow: /

# Busca das IAs: sem acesso
User-agent: OAI-SearchBot
User-agent: Claude-SearchBot
User-agent: PerplexityBot
User-agent: meta-webindexer
User-agent: Amzn-SearchBot
User-agent: MistralAI-Index
User-agent: DuckAssistBot
Disallow: /

# Visitas a pedido do usuário: sem acesso
# Google-Agent, Google-GeminiNotebook, ChatGPT-User, Perplexity-User, meta-externalfetcher, Amzn-User podem não seguir o robots.txt, segundo as próprias empresas;
# para barrar de fato, bloqueie também no servidor ou na CDN.
User-agent: Google-Agent
User-agent: Google-GeminiNotebook
User-agent: ChatGPT-User
User-agent: Claude-User
User-agent: Perplexity-User
User-agent: meta-externalfetcher
User-agent: Amzn-User
User-agent: MistralAI-User
Disallow: /

# Arquivo aberto da web: sem acesso
User-agent: CCBot
Disallow: /

# Todos os outros robôs, inclusive os que não estão na base: liberados
# (Googlebot, Bingbot, Applebot, DuckDuckBot)
User-agent: *
Allow: /

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Arquivo para baixar: [modelos/robots-txt-bloquear-ias-manter-buscadores.txt](modelos/robots-txt-bloquear-ias-manter-buscadores.txt).

#### O que muda na presença da marca com o modelo bloquear as IAs e manter os buscadores?

| Empresa | Busca e respostas da IA | Visitas a pedido do usuário | Treino de modelos |
|:---|:---|:---|:---|
| Google | Liberada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| OpenAI | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| Anthropic | Bloqueada | Bloqueadas | Bloqueado |
| Microsoft | Liberada | Sem robô na base | Sem robô de treino na base |
| Perplexity | Bloqueada | Bloqueadas, mas o robô pode não seguir | Sem robô de treino na base |
| Meta | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| Apple | Liberada | Sem robô na base | Bloqueado |
| Amazon | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| Mistral AI | Bloqueada | Bloqueadas | Bloqueado |
| DuckDuckGo | Em parte (`DuckAssistBot` bloqueado) | Sem robô na base | Sem robô de treino na base |
| Common Crawl | Sem robô de busca na base | Sem robô na base | Bloqueado (arquivo aberto) |

- Os AI Overviews e o Modo IA do Google continuam, porque usam as páginas que o `Googlebot` indexa. Para limitar o que aparece neles, o Google indica nosnippet, data-nosnippet, max-snippet e noindex.
- Os robôs de visita a pedido do usuário (`Google-Agent`, `Google-GeminiNotebook`, `ChatGPT-User`, `Perplexity-User`, `meta-externalfetcher` e `Amzn-User`) podem não seguir o bloqueio; para barrá-los, bloqueie também no servidor ou na CDN.
- A marca deixa de ser citada com link nas IAs que dependem dos próprios robôs de busca, e quem pergunta a essas IAs sobre o seu mercado passa a ver outras fontes.

### Como bloquear todos os robôs no robots.txt?

**Nenhum robô que siga o robots.txt pode rastrear o site.** O site sai do Google, do Bing e das IAs. Serve para ambiente de homologação, não para site em produção.

```text
# robots.txt modelo: Bloquear tudo
# Nenhum robô que siga o robots.txt pode rastrear o site.
# Gerado a partir da base aberta de robôs de IA da TRIWI, verificada em 09/11/2026:
# https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA
# Antes de publicar: troque o endereço do sitemap e acrescente as regras que o seu site já usa hoje.

# Atenção: este modelo tira o site do Google, do Bing e das IAs.
# Use só em homologação ou em site que não deve aparecer em busca nenhuma.
User-agent: *
Disallow: /

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Arquivo para baixar: [modelos/robots-txt-bloquear-tudo.txt](modelos/robots-txt-bloquear-tudo.txt).

#### O que muda na presença da marca com o modelo bloquear tudo?

| Empresa | Busca e respostas da IA | Visitas a pedido do usuário | Treino de modelos |
|:---|:---|:---|:---|
| Google | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| OpenAI | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| Anthropic | Bloqueada | Bloqueadas | Bloqueado |
| Microsoft | Bloqueada | Sem robô na base | Sem robô de treino na base |
| Perplexity | Bloqueada | Bloqueadas, mas o robô pode não seguir | Sem robô de treino na base |
| Meta | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| Apple | Bloqueada | Sem robô na base | Bloqueado |
| Amazon | Bloqueada | Bloqueadas, mas o robô pode não seguir | Bloqueado |
| Mistral AI | Bloqueada | Bloqueadas | Bloqueado |
| DuckDuckGo | Bloqueada | Sem robô na base | Sem robô de treino na base |
| Common Crawl | Sem robô de busca na base | Sem robô na base | Bloqueado (arquivo aberto) |

- O robots.txt impede o rastreamento, não remove páginas do índice: uma URL bloqueada pode continuar aparecendo, sem descrição, se tiver links apontando para ela. Para tirar uma página do Google, o caminho é o noindex.
- Um erro comum e caro em migração de site é este arquivo, usado na homologação, ir junto para o site em produção. Confira o robots.txt no dia de cada publicação.

## Qual modelo escolher?

| Situação da empresa | Modelo indicado | Por quê |
|:---|:---|:---|
| Quer ser encontrada e citada no Google e nas IAs (a maioria) | Liberar tudo, ou bloquear o treino e manter a busca | Os robôs de busca e de visita ficam liberados nos dois, e é deles que saem as citações com link |
| Vende o próprio conteúdo (editora, curso, base de dados paga) | Bloquear o treino e manter a busca, com o jurídico | O treino envolve uso do conteúdo; a busca continua trazendo leitores |
| Não quer aparecer nas IAs, mas precisa do Google | Bloquear as IAs e manter os buscadores | Sai das buscas próprias das IAs, mas continua nos AI Overviews e no Modo IA, que vêm do Googlebot |
| Ambiente de homologação ou intranet | Bloquear tudo | Nada deve ser rastreado; em produção, este modelo tira o site de toda busca |

Como resume o [Guia de GEO da TRIWI](https://triwi.com.br/guias/geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt), bloquear o treino é decisão de negócio, tomada com o jurídico, porque envolve o uso do conteúdo; bloquear a busca é decisão de visibilidade. Na dúvida, a TRIWI recomenda liberar os robôs de busca nas páginas feitas para serem encontradas e decidir o treino com calma, porque um robô de busca bloqueado por engano tira a marca das respostas sem nenhum aviso.

## Como testar antes de publicar?

1. Monte o arquivo no [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt) e use o testador de URLs para conferir quais regras valem para cada robô.
2. Depois de publicar, abra `https://www.seusite.com.br/robots.txt` no navegador e confira que o arquivo novo está no ar.
3. No Google Search Console, o relatório de robots.txt mostra a versão que o Google leu e se houve erro.
4. Nos dias seguintes, acompanhe os logs do servidor com o [Analisador de logs para SEO da TRIWI](https://triwi.com.br/ferramentas/analisador-de-logs-para-seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt) para ver quais robôs continuam visitando e quais pararam.

## Perguntas frequentes

<details>
<summary><strong>Onde fica o robots.txt?</strong></summary>

Na raiz do domínio, em `https://www.seusite.com.br/robots.txt`. Cada subdomínio tem o próprio arquivo, e o robô só lê o arquivo do endereço que está visitando.
</details>

<details>
<summary><strong>Posso misturar os modelos com as regras que o site já tem?</strong></summary>

Sim, e deve. Acrescente as áreas que já bloqueia hoje (como área administrativa, carrinho ou busca interna) no grupo `User-agent: *` e repita essas mesmas linhas em cada grupo com nome de robô que ficar liberado, porque o robô com grupo próprio não lê o grupo geral.
</details>

<details>
<summary><strong>Quanto tempo leva para a mudança valer?</strong></summary>

Depende da empresa. A OpenAI fala em cerca de 24 horas para a busca, a Meta em até 24 horas, o DuckDuckGo em 72 horas para o `DuckAssistBot`, e a Amazon usa uma cópia do arquivo de até 30 dias.
</details>

<details>
<summary><strong>O que acontece se o robots.txt der erro ou sair do ar?</strong></summary>

O comportamento varia por empresa. A Amazon, por exemplo, diz que, se não conseguir buscar o arquivo, age como se ele não existisse, o que libera tudo. Por isso o robots.txt merece monitoramento como qualquer outra página crítica do site.
</details>

<details>
<summary><strong>Bloquear as IAs protege o conteúdo?</strong></summary>

Só em parte. O robots.txt é um pedido que os robôs automáticos das empresas documentadas dizem seguir; ele não impede quem não segue as regras. Para proteção de verdade, o caminho é autenticação, bloqueio no servidor ou na CDN e, no caso do treino, decisão jurídica sobre o uso do conteúdo.
</details>

**Ver também na Base de Conhecimento da TRIWI:** [Crawling e Indexação: Como Garantir que o Google Encontre Seu Site](https://github.com/TRIWI-SEO/SEO-IA/blob/main/seo-tecnico/crawling-e-indexacao-como-garantir-que-o-google-encontre-seu-site.md), [Migração de Site Sem Perder Tráfego](https://github.com/TRIWI-SEO/SEO-IA/blob/main/seo-tecnico/migracao-de-site-sem-perder-trafego-guia-tecnico.md), [O Que é GEO](https://github.com/TRIWI-SEO/SEO-IA/blob/main/o-que-e-geo-generative-engine-optimization-guia-completo.md). No site da TRIWI: [Guia de SEO Técnico](https://triwi.com.br/guias/seo-tecnico/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt) e [Guia de GEO](https://triwi.com.br/guias/geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt).

**Ver também no Glossário da TRIWI:** [Robots.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt#seo-robots-txt), [Rastreadores de IA](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt#seo-rastreadores-de-ia), [AI Overviews](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt#seo-ai-overviews), [llms.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt#seo-llms-txt), [Grounding](https://triwi.com.br/glossario/inteligencia-artificial/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt#ia-grounding).

[Voltar para o início](README.md)

---

<p align="center">
  <strong>Quer saber se o seu robots.txt está tirando a sua marca das IAs?</strong><br>
  <a href="https://triwi.com.br/contato/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=modelos-robots-txt">Que tal um café com a TRIWI?</a>
</p>

<p align="center">
  <sub>Base publicada e mantida pela equipe da TRIWI, agência 100% especializada em SEO e Otimização para IAs.</sub>
</p>
