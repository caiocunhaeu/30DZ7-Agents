# CLAUDE.md

Regra mor deste repositório. `30dz7-agents` é a casa dos agentes e skills que Caio constrói para Claude Code voltados aos **materiais internos de design da Trinta Dezessete (30DZ7)** — a produtora. Não é o repositório de marca pessoal do Caio (isso vive em `caio-agents`) nem o de trabalho específico de cliente, como Furla (isso vive em `Furla-Agents`). Todo agente, subagente ou skill novo criado aqui segue o mesmo framework de `agent-architect` (skill homônima em `caio-agents`; carregue-a antes de desenhar um agente novo, quando disponível na sessão).

## Domínio

Materiais internos de design da Trinta Dezessete: documentos de posicionamento e análise, apresentações/decks, artefatos HTML (dashboards, relatórios visuais), peças pontuais de social. Tudo precisa respeitar a identidade visual 30DZ7 com o acabamento limpo, suave e acessível de interfaces nativas da Apple. Trabalho específico de um cliente da produtora (ex. Furla) fica no repositório daquele cliente, não aqui.

## Comandos

Sem build nem teste automatizado — os agentes deste repositório são skills em Markdown. Antes de entregar uma skill nova, valide manualmente: front matter YAML válido com `name` e `description`; `description` com gatilhos em linguagem natural reconhecíveis; `SKILL.md` abaixo de ~200 linhas, com detalhe pesado movido para `references/`.

## Arquitetura e convenções

Cada agente vive em `.claude/skills/<nome-em-kebab-case>/SKILL.md`. Tokens de marca e material de referência extenso vão em `.claude/skills/<nome>/references/*`, nunca inline no `SKILL.md`. Mesma terminologia do `agent-architect`: "agente" = uma skill do Claude Code; "subagente" = uma chamada da ferramenta `Agent`, isolada da conversa principal; "orquestrador" = o próprio Claude Code decidindo qual skill/subagente acionar.

## Diretrizes de "teste"

Antes de entregar uma skill nova: teste mentalmente 2-3 frases de gatilho reais contra a `description`; confirme que toda ferramenta citada existe de fato nesta sessão; confirme que existe uma seção "nunca fazer" sempre que o domínio tiver modos de falha conhecidos (ex.: usar cor fora da paleta, publicar por cima de um link já compartilhado).

## Estilo

Conteúdo em português. Sem travessão em-dash em nenhum arquivo. Nome de pasta em kebab-case igual ao campo `name` da skill.

## Fluxo de git

Repositório de uso individual: commits vão direto para `main` enquanto não houver necessidade de revisão por terceiros. Mensagem de commit descreve o porquê, não só o quê.

## Limites estritos

Nunca invente cor, fonte ou proporção fora do documentado em `marca.md`/`tokens.css` sem sinalizar que é extrapolação e pedir confirmação. Nunca publique ou sobrescreva um artefato já compartilhado com terceiros sem confirmação explícita do Caio. Nunca hardcode segredo ou chave de API em nenhum arquivo aqui. Nunca trate a fonte do wordmark (stencil geométrico) como fonte de corpo de texto.
