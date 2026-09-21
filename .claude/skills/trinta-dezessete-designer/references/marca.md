# Identidade visual — Trinta Dezessete (30DZ7)

> Status: reconstruído em 21/09/2026, em ambiente novo, a partir do logo oficial (raster) e das decisões tomadas nesta conversa. As cores foram medidas por pixel-sampling do logo, não extraídas de um arquivo vetorial — ver "Pendências" no fim.

## Referência de estilo

O objetivo declarado pelo Caio: peças que respeitem a identidade da Trinta Dezessete, mas com o acabamento limpo, suave e acessível dos apps/sites/sistemas nativos da Apple. Na prática isso significa:

- Hierarquia por peso, tamanho e espaço em branco — não por decoração.
- Cor de destaque usada com moderação (ver seção de acessibilidade), nunca como fundo de blocos grandes de texto.
- Cantos arredondados suaves, sombras discretas e nunca duras.
- Tipografia de sistema (a mesma lógica de "usar a fonte nativa da plataforma antes de uma fonte customizada", da skill `apple-design`).
- Modo claro e escuro sempre definidos juntos, nunca só um.

Todos os tokens abaixo estão implementados em `tokens.css` (mesma pasta).

## Cores

| Token | Hex | Papel |
|---|---|---|
| `--color-brand-carvao` | `#373536` | Fundo escuro de marca (o fundo do logo) |
| `--color-brand-branco` | `#FFFFFF` | Base clara / texto sobre escuro |
| `--color-brand-verde` | `#57A795` | Verde-água de destaque (a cor do "DZ7" no logo) |

A cor de destaque foi expandida numa escala de 10 passos (`--color-accent-50` a `--color-accent-900`) e o carvão numa escala neutra de 12 passos, para cobrir fundo, texto, bordas e estados de hover sem inventar cores fora da família da marca.

### Regras de acessibilidade (contraste WCAG, verificado nesta sessão)

- **Texto de corpo/links sobre fundo claro:** use `--color-accent-700` (`#3F796C`), 5.0:1 sobre branco — passa AA.
- `--color-accent-600` (3.6:1) e `--color-accent-500` (2.7:1) **não** têm contraste suficiente para texto de corpo em fundo branco; reserve-os para texto grande (≥24px), ícones, gráficos ou fundos escuros.
- **Verde de marca (`--color-accent-500`) sobre o carvão (`--color-brand-carvao`)**, como no próprio logo: 4.3:1 — está no limite do AA para texto pequeno; para texto de apoio use `--color-accent-300` (7.0:1).
- Branco sobre carvão: 12.2:1 — sobra folga, pode ser texto principal em qualquer tamanho.

Não use o verde de destaque como cor de fundo de blocos extensos de texto nem crie tons fora da escala gerada sem recalcular o contraste.

## Tipografia

- **Corpo e títulos:** pilha de fonte de sistema (`-apple-system, BlinkMacSystemFont, "SF Pro Text/Display", system-ui`) — decisão explícita do Caio, alinhada à skill `apple-design` (usar a fonte nativa da plataforma, não uma custom sem motivo).
- **Wordmark "30DZ7":** fonte display geométrica em estilo stencil (vãos internos nas letras), como aparece no logo oficial. Uso restrito ao logotipo — não usar essa fonte em corpo de texto ou títulos de documentos.
- Tracking e leading variam por tamanho (nunca um valor fixo único) — valores em `tokens.css` (`--text-display-*`, `--text-heading-*`, `--text-body-*`, `--text-caption-*`).

## Tom e uso

- Tom: **estratégico/institucional** — sóbrio, executivo, direto. Não é uma marca de tom descontraído/social por padrão.
- Materiais mais frequentes: documentos de posicionamento e análise (ex.: "Posicionamento Furla") e apresentações/decks internos ou para cliente.
- Confiabilidade e clareza pesam mais que ornamento — craft (skill `apple-design`, princípio 7) antes de efeito visual.

## Pendências conhecidas

1. **Cores por pixel, não por vetor.** Os hex acima vêm de amostragem de pixel de um PNG do logo. Se o Caio tiver o SVG/PDF original da marca, os valores devem ser conferidos contra ele (anti-aliasing em PNG pode desviar levemente as bordas, embora os preenchimentos sólidos amostrados aqui tenham alta confiança).
2. Este arquivo e `tokens.css` foram recriados nesta sessão, sem acesso ao `~/.claude/design/trinta-dezessete/marca.md` de uma sessão anterior na máquina local do Caio (ambiente diferente, sem sincronização). Se aquela versão local tiver decisões adicionais que não estão aqui, precisam ser mescladas manualmente.
3. A versão 2 do artefato "Posicionamento Furla" com a identidade 30DZ7, redesenhada numa sessão anterior, ainda não foi validada pelo Caio em desktop nem no restante do mobile (só o topo em celular escuro foi conferido).
