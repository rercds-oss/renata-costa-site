# Site pessoal da Renata Costa — Design

## Objetivo

Site pessoal de página única (estilo "link in bio" avançado), inspirado no site da Marina Braga (`marinabraga.my.canva.site`), mas com identidade visual e fotos próprias da Renata. Serve como ponto central de contato/apresentação profissional, substituindo/complementando o link na bio do Instagram.

## Plataforma

**Código (HTML/CSS), construído pela Claude.** Decisão revisada em 2026-07-22: a escolha inicial foi Canva Sites, mas o Canva não expõe API/MCP para criar ou editar um Canva Site — a montagem é 100% manual no editor do Canva (confirmado via Canva Help). Depois de ver o trabalho manual necessário, Renata preferiu que o site seja construído em código por completo, aceitando pedir ajustes pontuais depois em vez de montar/editar sozinha.

Alternativas consideradas e descartadas:
- **Canva Sites** — ela editaria sozinha depois, mas exige montagem manual inicial extensa no editor (motivo do abandono).
- Outras ferramentas no-code (Framer, Wix, Carrd) — mesmo problema de montagem manual, só que numa ferramenta nova pra aprender.

## Identidade visual (já estabelecida, ver memória do projeto)

- Paleta: verde-sálvia (~#5F7052 / #4B5940), terracota (~#C97B4A) como accent, creme/off-white (~#F5F0E6) como fundo claro.
- Tipografia: serifada elegante (Playfair Display/estilo) para títulos, sans-serif arredondada (Quicksand/estilo) para corpo de texto.
- Direção visual definida nesta sessão: **editorial clean** — fundo claro predominante (creme/branco), cor usada só em detalhes (linha fina, labels, texto/borda de botão), não em blocos de cor cheios. Sem overlays escuros pesados sobre foto (testado e rejeitado).

## Fotos

Fonte: `C:\Users\rercd\OneDrive\Imagens\Documents\Área de Trabalho\FOTOS` (ensaio profissional de 27/09/2025, fundo claro/neutro, compatível com a paleta).

- **Hero:** `A93A9291.jpg` — foto sentada, sorriso solto, escolhida entre 3 opções testadas.
- Demais seções (Sobre, Serviços) podem reaproveitar outras fotos do mesmo ensaio para manter consistência de luz/tom (ex.: `A93A9501.jpg`, que mostra atividade prática de terapia com material colorido, é candidata forte pra seção de Serviços/Sobre).

## Estrutura da página (ordem aprovada)

1. **Nav** — nome "Renata Costa" à esquerda, links (Sobre · Serviços · Depoimentos · Contato) à direita, fundo creme, borda inferior fina.
2. **Hero** — label pequena "TERAPEUTA OCUPACIONAL" com linha terracota, foto grande (proporção ~4:5, cantos levemente arredondados), nome "Renata Costa" grande em serifada abaixo da foto, subtítulo curto (integração sensorial + seletividade alimentar), botão outline "Fale no WhatsApp".
3. **Sobre** — label + título "Quem é Renata", parágrafo de bio (formação em TO, especialização em integração sensorial, anos de experiência, abordagem acolhedora baseada em evidência).
4. **Serviços** — label + título "Como posso ajudar", lista de 4 itens com seta terracota (não cards com ícones): Seletividade alimentar, Integração sensorial, Avaliações (EASI, PEDI), AVDs — autonomia no dia a dia.
5. **Depoimentos** — label + título "O que dizem as famílias", citação com borda lateral terracota (placeholder — conteúdo real a ser adicionado depois por ela).
6. **Contato** — bloco em bege suave (não verde escuro cheio), título "Vamos conversar", botão sólido terracota "Fale no WhatsApp", handle do Instagram.
7. **Footer** — barra escura fina, copyright.

## Fora de escopo nesta rodada

- Textos finais de bio/depoimentos (placeholders aprovados, conteúdo real fica a cargo dela ou de uma rodada futura).
- Fotos definitivas de todas as seções além do hero (a definir durante a montagem).
- Domínio próprio / SEO / analytics.
