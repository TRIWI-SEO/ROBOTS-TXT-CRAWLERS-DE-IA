# Dicionário de Dados: Base Aberta de Robôs de IA e dos Buscadores da TRIWI

Este dicionário descreve a base [robos-de-ia.csv](robos-de-ia.csv), a versão em dados do repositório [Robots.txt e crawlers de IA](../README.md): o que cada coluna significa, como o arquivo é formatado e como a base é mantida. A base está sob licença [CC BY 4.0](../LICENSE): o reuso é livre, inclusive comercial, desde que a TRIWI seja citada como fonte.

*Por equipe de SEO da TRIWI. Atualizado em 09/11/2026.*

## Quais bases existem?

| Arquivo | O que traz | Linhas |
|:---|:---|:---|
| [robos-de-ia.csv](robos-de-ia.csv) | Robôs das IAs e dos buscadores, com empresa, produto, função, se segue o robots.txt, efeito do bloqueio, documentação oficial e data da verificação | 27 |

## Como abrir o arquivo?

O arquivo segue o mesmo padrão das outras bases abertas da TRIWI: codificação UTF-8, colunas separadas por vírgula, quebra de linha CRLF e datas no formato AAAA-MM-DD.

Se o Excel mostrar os acentos embaralhados, abra pelo menu Dados, opção De Texto/CSV, e escolha a codificação UTF-8.

## O que significa cada coluna?

| Coluna | Significado |
|:---|:---|
| empresa | Empresa dona do robô |
| produto | Produto ou serviço em que o uso do robô aparece, como a empresa descreve |
| user_agent | Nome do robô como deve ser escrito na linha `User-agent` do robots.txt |
| funcao | Treino; Busca; Visita a pedido do usuário; Arquivo aberto da web (ver abaixo) |
| respeita_robots_txt | Sim, declarado; Bloqueio documentado; Pode não seguir; Em geral não segue; Não se aplica (ver abaixo) |
| trecho_da_documentacao | Trecho curto da documentação oficial, no original em inglês, que sustenta o valor de respeita_robots_txt |
| efeito_do_bloqueio | O que acontece quando o robô é bloqueado, segundo a documentação |
| observacao | Detalhe da documentação que muda a decisão, como prazo para valer ou regra especial |
| exemplo_user_agent | Frase do user-agent como aparece no log do servidor, copiada da documentação; n/d quando a empresa não publica ou quando é token de controle |
| verificacao | Link da lista oficial de IPs ou do método de verificação do robô; texto quando a empresa descreve um método sem link; n/d quando não publica |
| documentacao_oficial | Página oficial da empresa que documenta o robô |
| verificado_em | Data em que a documentação oficial foi conferida |

## O que significa cada função?

| Valor | Significado |
|:---|:---|
| Treino | Coleta conteúdo que pode ser usado para treinar modelos de IA, ou é o token que controla esse uso |
| Busca | Rastreia e indexa páginas para a busca do buscador ou da IA, de onde saem as citações e os links |
| Visita a pedido do usuário | Abre uma página na hora em que uma pessoa pede, sem rastrear a web por conta própria |
| Arquivo aberto da web | Coleta páginas para um arquivo público da web, aberto a qualquer pessoa |

## O que significa cada valor de respeita_robots_txt?

| Valor | Significado |
|:---|:---|
| Sim, declarado | A documentação afirma que o robô segue o robots.txt |
| Bloqueio documentado | A documentação ensina a bloquear o robô pelo robots.txt, mas não afirma que ele segue o arquivo |
| Pode não seguir | A empresa avisa que, por ser acionado pelo usuário, o robô pode não seguir as regras |
| Em geral não segue | A empresa diz que o robô, em geral, ignora o robots.txt |
| Não se aplica | É um token de controle, não um robô: não rastreia nada, só é lido pelos robôs da empresa |

**Critério de contagem:** cada linha é um nome de robô ou de token de controle que a empresa documenta com função própria. Variantes que respondem ao mesmo nome no robots.txt (como as versões para celular e computador) contam como uma linha. Token substituído não ganha linha própria: fica registrado na observação do token novo, como o `Google-NotebookLM` na linha do `Google-GeminiNotebook`. Ficam fora os robôs sem documentação oficial e os de anúncio, de prévia de link e de verificação de propriedade, porque não decidem a presença da marca nas buscas e nas IAs.

**Sobre a frase do user-agent:** quando a versão do navegador muda, a documentação usa o marcador W.X.Y.Z, e a base mantém o marcador. Quando a empresa publica só o trecho que identifica o robô, como a OpenAI no `OAI-SearchBot`, a base traz esse trecho. Para procurar o robô no log, basta o nome dele, que aparece em todas as variantes.

**Por que documentacao_oficial e verificado_em, e não fonte e atualizado_em, como nas outras bases da TRIWI?** Porque aqui o que sustenta a linha é a conferência: a coluna diz em que página oficial o robô foi conferido e quando, e não de onde um dado foi tirado. Uma linha com data antiga não está errada, mas pede nova conferência.

## Como a base é mantida?

A base é conferida pela equipe da TRIWI uma vez por mês e sempre que uma empresa muda a documentação. Robô novo entra com a data da verificação; robô aposentado sai, e a mudança fica no histórico do README. Os modelos de robots.txt para IAs da pasta [modelos](../modelos/robots-txt-liberar-tudo.txt) são gerados a partir desta base e mudam junto com ela. Correções e sugestões chegam por [issue](../../../issues/new).
