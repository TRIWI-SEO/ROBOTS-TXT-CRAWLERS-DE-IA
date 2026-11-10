# Robots.txt: o que é, como funciona e exemplos para WordPress e e-commerce

**O robots.txt é um arquivo de texto na raiz do site, em `seusite.com.br/robots.txt`, que diz aos robôs dos buscadores e das IAs quais páginas eles podem rastrear. Ele segue a norma RFC 9309: cada grupo começa com `User-agent` e traz regras `Disallow` (não rastrear) e `Allow` (pode rastrear). O arquivo orienta o rastreamento, mas não tira páginas do Google.**

Esta página traz a sintaxe, as regras da norma que decidem o resultado, exemplos prontos para WordPress e e-commerce e como juntar tudo com as regras para os robôs de IA, que estão na [base aberta da TRIWI](README.md).

*Por equipe de SEO da TRIWI, com revisão de Ricardo Martins, fundador. Publicado em 09/11/2026. Atualizado em 09/11/2026.*

## Índice

- [Como funciona o robots.txt?](#como-funciona-o-robotstxt)
- [Quais regras decidem o resultado?](#quais-regras-decidem-o-resultado)
- [Exemplo de robots.txt para WordPress](#exemplo-de-robotstxt-para-wordpress)
- [Exemplo de robots.txt para e-commerce](#exemplo-de-robotstxt-para-e-commerce)
- [Como juntar com as regras para IAs?](#como-juntar-com-as-regras-para-ias)
- [Quais são os erros mais comuns?](#quais-são-os-erros-mais-comuns)
- [Perguntas frequentes](#perguntas-frequentes)

## Como funciona o robots.txt?

O arquivo é lido pelo robô antes de rastrear o site. Ele é dividido em grupos, e cada grupo vale para os robôs nomeados nas linhas `User-agent` dele.

| Linha | Para que serve | Exemplo |
|:---|:---|:---|
| `User-agent` | Nome do robô a que o grupo se aplica; `*` vale para todos os que não têm grupo próprio | `User-agent: Googlebot` |
| `Disallow` | Caminho que o robô não deve rastrear | `Disallow: /checkout/` |
| `Allow` | Exceção dentro de um caminho bloqueado | `Allow: /wp-admin/admin-ajax.php` |
| `Sitemap` | Endereço do sitemap XML; vale para o arquivo todo e é lido pelos principais buscadores | `Sitemap: https://www.seusite.com.br/sitemap.xml` |
| `#` | Comentário, ignorado pelos robôs | `# área do cliente` |
| `*` no caminho | Qualquer sequência de caracteres | `Disallow: /*?q=` |
| `$` no fim | Marca o fim do endereço | `Disallow: /*.pdf$` |

Os nomes dos robôs, e o que cada um faz, estão na [Lista de robôs de IA](lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md). Se o site ainda não tem sitemap, o [Gerador de sitemap XML da TRIWI](https://triwi.com.br/ferramentas/gerador-de-sitemap-xml/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt) monta o arquivo.

## Quais regras decidem o resultado?

A [RFC 9309](https://www.rfc-editor.org/rfc/rfc9309.html), da IETF, define como o robô interpreta o arquivo:

1. **O grupo com o nome do robô vence o geral.** O robô segue o grupo que cita o nome dele e ignora o `User-agent: *`. Se houver mais de um grupo com o mesmo nome, as regras se somam.
2. **O nome do robô não diferencia maiúscula.** `Googlebot` e `googlebot` são o mesmo robô.
3. **A regra mais específica vence.** Quando `Allow` e `Disallow` valem para o mesmo endereço, vence a de caminho mais longo; em empate, vence o `Allow`.
4. **O robô lê pelo menos 500 KiB.** Regras além desse tamanho podem ser ignoradas.
5. **Erro no arquivo muda tudo.** Resposta 4xx, como 404, deixa o robô rastrear tudo; resposta 5xx obriga o robô a tratar o site como totalmente bloqueado.

## Exemplo de robots.txt para WordPress

As mesmas regras que o WordPress gera sozinho quando o site não tem arquivo próprio, mais o sitemap. O WordPress gera esse conteúdo quando não existe um arquivo físico na raiz, segundo a [referência da função do_robots](https://developer.wordpress.org/reference/functions/do_robots/). Ter o arquivo próprio serve para acrescentar o sitemap e as regras para IAs.

```text
# robots.txt modelo: WordPress
# As mesmas regras que o WordPress gera sozinho quando o site não tem arquivo próprio, mais o sitemap.
# Modelo da TRIWI, publicado em 09/11/2026:
# https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA
# Antes de publicar: troque o endereço do sitemap e confira os caminhos do seu site.

User-agent: *
Disallow: /wp-admin/
Allow: /wp-admin/admin-ajax.php

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Arquivo para baixar: [modelos/robots-txt-wordpress.txt](modelos/robots-txt-wordpress.txt). Renomeie para `robots.txt` e publique na raiz do domínio, no lugar do arquivo atual, juntando as regras que o seu site já usa.

## Exemplo de robots.txt para e-commerce

Carrinho, checkout, conta do cliente e busca interna fora do rastreamento; produtos e categorias liberados. Os caminhos são exemplos: cada plataforma de loja usa os seus, e eles precisam ser trocados antes de publicar.

```text
# robots.txt modelo: E-commerce
# Carrinho, checkout, conta do cliente e busca interna fora do rastreamento; produtos e categorias liberados.
# Modelo da TRIWI, publicado em 09/11/2026:
# https://github.com/TRIWI-SEO/ROBOTS-TXT-CRAWLERS-DE-IA
# Antes de publicar: troque o endereço do sitemap e confira os caminhos do seu site.

User-agent: *
# Troque os caminhos abaixo pelos da sua plataforma de loja.
Disallow: /carrinho/
Disallow: /checkout/
Disallow: /minha-conta/
# Busca interna: troque q pelo parâmetro que a sua loja usa.
Disallow: /*?q=
Disallow: /*&q=
Allow: /

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Arquivo para baixar: [modelos/robots-txt-ecommerce.txt](modelos/robots-txt-ecommerce.txt). Renomeie para `robots.txt` e publique na raiz do domínio, no lugar do arquivo atual, juntando as regras que o seu site já usa.

- **Não bloqueie produto nem categoria.** São as páginas que trazem venda pela busca e que as IAs citam.
- **Filtros pedem cuidado.** Filtros que geram milhares de combinações podem sair do rastreamento, mas só depois de conferir que nenhuma combinação tem busca própria, como "tênis de corrida masculino".
- **Busca interna fica fora.** Ela gera páginas quase infinitas e sem valor para o buscador.

## Como juntar com as regras para IAs?

Os grupos dos robôs de IA entram no mesmo arquivo, antes do grupo geral. Exemplo com as regras do WordPress e o treino de IA bloqueado, a partir do modelo [Bloquear o treino e manter a busca](robots-txt-para-ia-modelos-prontos.md#como-bloquear-o-treino-de-ia-e-manter-a-busca):

```text
# robots.txt modelo: WordPress sem treino de IA
# Regras do WordPress para todos os robôs, com os robôs e tokens de treino de IA sem acesso.
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
Disallow: /wp-admin/
Allow: /wp-admin/admin-ajax.php

Sitemap: https://www.seusite.com.br/sitemap.xml
```

Os robôs com grupo próprio e `Disallow: /` não precisam das regras do WordPress, porque já estão fora do site inteiro. Se você criar um grupo para liberar um robô com regras diferentes, repita nele as regras gerais, porque ele deixa de ler o grupo `User-agent: *`.

## Quais são os erros mais comuns?

| Erro | O que acontece | Como corrigir |
|:---|:---|:---|
| Usar o robots.txt para tirar página do Google | A URL pode continuar indexada, sem descrição | Usar noindex e deixar a página ser rastreada |
| Levar o robots.txt da homologação para a produção | O site inteiro sai da busca e das IAs | Conferir o arquivo no dia de cada publicação |
| Bloquear arquivos CSS e JavaScript | O buscador não consegue montar a página como o usuário vê | Liberar os recursos de que a página precisa para ser exibida |
| Deixar o servidor responder com erro 5xx no robots.txt | Pela norma, o robô deve tratar o site como totalmente bloqueado | Monitorar o endereço do arquivo como página crítica |
| Criar grupo para um robô sem repetir as regras gerais | O robô ignora o grupo geral e passa a rastrear o que deveria estar bloqueado | Repetir as regras gerais em cada grupo com nome de robô |
| Bloquear um robô de busca de IA achando que é de treino | A marca some das respostas daquela IA | Conferir a função de cada robô na [Lista de robôs de IA](lista-de-robos-de-ia-gptbot-claudebot-perplexitybot.md) |

## Perguntas frequentes

<details>
<summary><strong>Todo site precisa de robots.txt?</strong></summary>

Não é obrigatório. Pela [RFC 9309](https://www.rfc-editor.org/rfc/rfc9309.html), se o endereço do arquivo responde 404, o robô pode rastrear tudo. Mesmo assim, vale ter o arquivo: é nele que se indica o sitemap e que se decide o acesso de cada robô de IA, como mostram os [modelos para IA](robots-txt-para-ia-modelos-prontos.md).
</details>

<details>
<summary><strong>O robots.txt tira uma página do Google?</strong></summary>

Não. Ele impede o rastreamento, e uma URL bloqueada pode continuar no índice, sem descrição, se tiver links apontando para ela. Para tirar uma página do Google, use a tag noindex e deixe a página ser rastreada, para o robô conseguir ler a tag.
</details>

<details>
<summary><strong>O WordPress já vem com robots.txt?</strong></summary>

Sim. Quando o site não tem um arquivo próprio na raiz, o WordPress gera um robots.txt com o grupo geral, o bloqueio da área administrativa e a liberação do `admin-ajax.php`, como mostra a [referência da função do_robots](https://developer.wordpress.org/reference/functions/do_robots/). Desde a versão 5.3, a opção de desencorajar os mecanismos de busca deixou de escrever `Disallow: /` no arquivo e passou a usar a tag robots nas páginas.
</details>

<details>
<summary><strong>Qual o tamanho máximo do robots.txt?</strong></summary>

A norma diz que os robôs devem ler pelo menos os primeiros 500 KiB do arquivo. Regras depois desse limite podem ser ignoradas, então arquivos muito longos, com uma linha por URL, são um risco.
</details>

<details>
<summary><strong>Onde criar e testar o robots.txt?</strong></summary>

O [Gerador de robots.txt da TRIWI](https://triwi.com.br/ferramentas/gerador-de-robots-txt/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt) tem atalhos para WordPress e e-commerce, monta as regras para os robôs de IA e testa quais regras valem para cada URL e cada robô. Depois de publicar, o relatório de robots.txt do Google Search Console mostra a versão que o Google leu.
</details>

**Ver também na Base de Conhecimento da TRIWI:** [Crawling e Indexação: Como Garantir que o Google Encontre Seu Site](https://github.com/TRIWI-SEO/SEO-IA/blob/main/seo-tecnico/crawling-e-indexacao-como-garantir-que-o-google-encontre-seu-site.md), [Migração de Site Sem Perder Tráfego](https://github.com/TRIWI-SEO/SEO-IA/blob/main/seo-tecnico/migracao-de-site-sem-perder-trafego-guia-tecnico.md). No site da TRIWI: [Guia de SEO Técnico](https://triwi.com.br/guias/seo-tecnico/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt).

**Ver também no Glossário da TRIWI:** [Robots.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt#seo-robots-txt), [Rastreadores de IA](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt#seo-rastreadores-de-ia), [llms.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt#seo-llms-txt).

[Voltar para o início](README.md)

---

<p align="center">
  <strong>Quer saber se o seu robots.txt está tirando a sua marca do Google e das IAs?</strong><br>
  <a href="https://triwi.com.br/contato/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=exemplos-robots-txt">Que tal um café com a TRIWI?</a>
</p>

<p align="center">
  <sub>Base publicada e mantida pela equipe da TRIWI, agência 100% especializada em SEO e Otimização para IAs.</sub>
</p>
