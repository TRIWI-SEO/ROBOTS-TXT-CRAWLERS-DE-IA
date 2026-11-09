# llms.txt: modelo em português e o que o arquivo faz pela marca nas IAs

**O llms.txt é um arquivo em markdown, na raiz do site, que dá às IAs um mapa curto e curado do conteúdo: o nome da empresa, um resumo e os links que importam. É uma proposta aberta de 2024, não um padrão: o Google diz que não é preciso criar arquivos novos para aparecer nos AI Overviews e no Modo IA, e o Guia de GEO da TRIWI recomenda tratá-lo como mapa opcional.**

Esta página traz o [modelo pronto](modelos/llms.txt), o formato da proposta e o que o arquivo faz e não faz. Ele complementa os [modelos de robots.txt](robots-txt-para-ia-modelos-prontos.md), que decidem o acesso dos robôs.

*Por equipe de SEO da TRIWI, com revisão de Ricardo Martins, fundador. Publicado em 09/11/2026. Atualizado em 09/11/2026.*

## Índice

- [Qual a diferença entre llms.txt e robots.txt?](#qual-a-diferença-entre-llmstxt-e-robotstxt)
- [Como é o formato do llms.txt?](#como-é-o-formato-do-llmstxt)
- [Modelo de llms.txt](#modelo-de-llmstxt)
- [Como preencher o modelo?](#como-preencher-o-modelo)
- [O que o llms.txt não faz?](#o-que-o-llmstxt-não-faz)
- [Perguntas frequentes](#perguntas-frequentes)

## Qual a diferença entre llms.txt e robots.txt?

| | robots.txt | llms.txt |
|:---|:---|:---|
| Para que serve | Dizer o que cada robô pode rastrear | Mostrar às IAs o que vale a pena ler |
| Situação | Padrão da IETF, a [RFC 9309](https://www.rfc-editor.org/rfc/rfc9309.html) | [Proposta aberta](https://llmstxt.org/), publicada em 2024 |
| Quem segue | Os robôs automáticos das empresas documentadas na [base](dados/robos-de-ia.csv) | Os agentes e ferramentas que decidirem ler |
| Formato | Grupos de `User-agent`, `Allow` e `Disallow` | Markdown: título, resumo e listas de links |
| Efeito na marca | Decide se a IA pode ler e citar o site | Organiza a visão do site, sem garantir citação |

## Como é o formato do llms.txt?

Pela [proposta](https://llmstxt.org/), o arquivo segue esta ordem:

1. Um título H1 com o nome do site ou da empresa. É a única parte obrigatória.
2. Um bloco de citação (a linha que começa com `>`) com um resumo curto.
3. Parágrafos ou listas com detalhes, sem novos títulos.
4. Seções H2, cada uma com uma lista de links no formato `[nome](url): nota sobre a página`.
5. Uma seção H2 chamada `Optional`, por convenção, com links secundários que a IA pode pular.

A proposta também sugere publicar uma versão em markdown das páginas importantes, no mesmo endereço com `.md` no fim. É opcional e pede trabalho de desenvolvimento.

## Modelo de llms.txt

```markdown
# Nome da Empresa

> Uma ou duas frases dizendo o que a empresa faz, para quem e onde atua. Use as mesmas palavras do site e dos perfis oficiais da marca.

Informações que ajudam a IA a descrever a empresa sem erro: segmento, região atendida, ano de fundação, o que a empresa não faz e como prefere ser chamada. Mantenha os mesmos fatos que estão no site.

## Produtos e serviços

- [Nome do serviço principal](https://www.seusite.com.br/servico/): o problema que ele resolve, em uma frase
- [Nome do segundo serviço](https://www.seusite.com.br/outro-servico/): para quem ele é

## Conteúdos de referência

- [Guia ou página mais completa sobre o tema da empresa](https://www.seusite.com.br/guia/): o que a página explica
- [Perguntas frequentes](https://www.seusite.com.br/perguntas-frequentes/): respostas diretas sobre serviços, atendimento e prazos

## Institucional

- [Sobre a empresa](https://www.seusite.com.br/sobre/): história, equipe e números públicos
- [Contato](https://www.seusite.com.br/contato/): canais oficiais de atendimento

## Optional

- [Blog](https://www.seusite.com.br/blog/): artigos de apoio, que a IA pode pular quando precisar de um contexto mais curto
```

Arquivo para baixar: [modelos/llms.txt](modelos/llms.txt).

## Como preencher o modelo?

- **Resumo igual ao do site.** A frase do bloco de citação deve dizer o mesmo que a página Sobre e os perfis oficiais da marca. Fato divergente entre fontes confunde a IA.
- **Poucos links, os melhores.** Liste as páginas que respondem às perguntas do seu mercado: serviços, guias, perguntas frequentes, sobre e contato. O llms.txt não é sitemap.
- **Uma nota útil por link.** Diga em uma frase o que a página resolve, com as palavras que o cliente usa.
- **Links que funcionam.** Use o endereço final de cada página, sem redirecionamento e sem parâmetro de campanha.
- **Revisão junto com o site.** Página nova importante entra no arquivo; página removida sai no mesmo dia.

## O que o llms.txt não faz?

Ele não controla o acesso dos robôs, que continua no robots.txt, e não garante citação. Segundo o [Guia de GEO da TRIWI](https://triwi.com.br/guias/geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt), nenhuma grande empresa de IA se comprometeu a ler o arquivo, e o que mais pesa para ser citado continua sendo conteúdo que responde, autoridade fora do site e robôs de busca liberados. O [Checklist de SEO para IA da TRIWI](https://triwi.com.br/checklist-de-seo-para-ia-50-pontos-para-dominar-o-geo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt) mostra os pontos que vêm antes.

Mesmo assim, o arquivo custa pouco: uma hora de trabalho e uma revisão a cada mudança grande no site. Para quem decide publicar, o modelo acima já segue a proposta.

## Perguntas frequentes

<details>
<summary><strong>O Google lê o llms.txt?</strong></summary>

O Google não precisa dele: a documentação [Recursos de IA e seu site](https://developers.google.com/search/docs/appearance/ai-features) diz que não é preciso criar arquivos novos legíveis por máquina, arquivos de texto para IA ou marcação especial para aparecer nos AI Overviews e no Modo IA. O que vale é a página estar indexada e apta a aparecer na Pesquisa com trecho.
</details>

<details>
<summary><strong>Onde coloco o llms.txt?</strong></summary>

Na raiz do site, em `https://www.seusite.com.br/llms.txt`. A proposta também aceita o arquivo numa subpasta, como `/docs/llms.txt`, cobrindo só as páginas daquele caminho.
</details>

<details>
<summary><strong>O llms.txt substitui o robots.txt?</strong></summary>

Não. O robots.txt diz o que cada robô pode ler; o llms.txt só organiza o que vale a pena ler. Um site pode ter os dois, e o que decide o acesso das IAs continua sendo o robots.txt, com os [modelos prontos](robots-txt-para-ia-modelos-prontos.md).
</details>

<details>
<summary><strong>O título da seção Optional fica em inglês?</strong></summary>

Sim. Pela proposta, a seção chamada `Optional` é a convenção para links secundários, que a IA pode pular quando precisa de um contexto mais curto. Traduzir o nome tira esse significado.
</details>

<details>
<summary><strong>Quem deve manter o arquivo?</strong></summary>

Quem cuida do conteúdo do site. O llms.txt envelhece como qualquer página: link quebrado ou serviço descontinuado no arquivo passa à IA uma informação errada sobre a empresa.
</details>

**Ver também na Base de Conhecimento da TRIWI:** [Como as LLMs Decidem o Que Citar](https://github.com/TRIWI-SEO/SEO-IA/blob/main/geo-seo-para-ia/como-as-llms-decidem-o-que-citar-arquitetura-de-informacao-para-ia.md), [Conteúdo Citável: Como Escrever para Ser Referenciado por LLMs](https://github.com/TRIWI-SEO/SEO-IA/blob/main/geo-seo-para-ia/conteudo-citavel-como-escrever-para-ser-referenciado-por-llms.md), [O Que é GEO](https://github.com/TRIWI-SEO/SEO-IA/blob/main/o-que-e-geo-generative-engine-optimization-guia-completo.md).

**Ver também no Glossário da TRIWI:** [llms.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt#seo-llms-txt), [Robots.txt](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt#seo-robots-txt), [GEO](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt#seo-geo), [Citação em IAs](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt#seo-citacao-em-ias), [Entidade](https://triwi.com.br/glossario/seo/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt#seo-entidade).

[Voltar para o início](README.md)

---

<p align="center">
  <strong>Quando alguém pergunta à IA sobre o seu mercado, ela cita a sua empresa?</strong><br>
  <a href="https://triwi.com.br/contato/?utm_source=github&utm_medium=referral&utm_campaign=repo-robots-txt-ia&utm_content=llms-txt">Que tal um café com a TRIWI?</a>
</p>

<p align="center">
  <sub>Base publicada e mantida pela equipe da TRIWI, agência 100% especializada em SEO e Otimização para IAs.</sub>
</p>
