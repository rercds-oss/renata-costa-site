# Site Pessoal da Renata Costa — Plano de Montagem (Canva Sites)

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Preparar todo o conteúdo, fotos e um passo a passo detalhado para que a Renata monte o site pessoal sozinha no editor do Canva Sites, seguindo o design aprovado em `docs/superpowers/specs/2026-07-22-site-pessoal-design.md`.

**Architecture:** Este não é um projeto de código — o Canva não expõe API/MCP para criar ou editar Canva Sites (confirmado via Canva Help em 2026-07-22), então a montagem final é 100% manual no editor do Canva. O trabalho aqui é preparar tudo que a Renata precisa (fotos organizadas, texto final pronto pra copiar/colar, cores/fontes exatas, passo a passo de UI) para que a montagem manual seja rápida e sem decisões pendentes.

**Tech Stack:** Canva Sites (editor web, plano gratuito). Nenhuma dependência de código.

## Global Constraints

- Paleta: verde-sálvia `#5F7052` (escuro `#4B5940`), terracota `#C97B4A`, creme `#F5F0E6`, bege contato `#EDE7D6`, texto escuro `#3d4a35`.
- Fontes: **Playfair Display** (títulos), **Quicksand** (corpo de texto) — ambas devem estar disponíveis nas opções de fonte do Canva; aplicar manualmente em cada caixa de texto (Canva Free não tem fonte global).
- Direção visual: editorial clean — fundo claro predominante, cor só em detalhes (linha fina, labels, texto/borda de botão). Sem blocos escuros cheios ou overlay pesado sobre foto.
- Todo texto de conteúdo é em português (pt-BR).
- Botão de WhatsApp deve linkar para `https://wa.me/55` + número de telefone da Renata (a definir por ela — placeholder `[NUMERO]` até ela confirmar).

---

### Task 1: Organizar as fotos em uma pasta de assets pronta pra upload

**Files:**
- Create: `assets/site/01-hero-renata-sentada.jpg` (cópia de `A93A9291.jpg`)
- Create: `assets/site/02-sobre-atividade-terapeutica.jpg` (cópia de `A93A9501.jpg`)
- Create: `assets/site/03-servicos-sálvia.jpg` (cópia de `A93A9385.jpg`)

**Interfaces:**
- Consumes: fotos originais em `C:\Users\rercd\OneDrive\Imagens\Documents\Área de Trabalho\FOTOS\`
- Produces: pasta `assets/site/` com nomes semânticos indicando em qual seção do site cada foto deve ser usada — Task 2 referencia esses nomes de arquivo diretamente.

- [ ] **Passo 1: Copiar as 3 fotos escolhidas com nomes semânticos**

```bash
cp "C:/Users/rercd/OneDrive/Imagens/Documents/Área de Trabalho/FOTOS/A93A9291.jpg" "C:/Users/rercd/projects/renata-costa-site/assets/site/01-hero-renata-sentada.jpg"
cp "C:/Users/rercd/OneDrive/Imagens/Documents/Área de Trabalho/FOTOS/A93A9501.jpg" "C:/Users/rercd/projects/renata-costa-site/assets/site/02-sobre-atividade-terapeutica.jpg"
cp "C:/Users/rercd/OneDrive/Imagens/Documents/Área de Trabalho/FOTOS/A93A9385.jpg" "C:/Users/rercd/projects/renata-costa-site/assets/site/03-servicos-sálvia.jpg"
```

- [ ] **Passo 2: Verificar que as 3 fotos existem na pasta de destino**

Run: `ls -la "C:/Users/rercd/projects/renata-costa-site/assets/site/"`
Expected: 3 arquivos `.jpg` listados, cada um com tamanho > 0 bytes.

---

### Task 2: Escrever o guia de montagem completo (conteúdo + estilo + passos de UI, seção por seção)

**Files:**
- Create: `docs/superpowers/plans/2026-07-22-canva-build-guide.md`

**Interfaces:**
- Consumes: fotos nomeadas em `assets/site/` (Task 1), paleta/fontes definidas em Global Constraints, estrutura de seções do spec aprovado.
- Produces: documento único, lido de cima a baixo pela Renata durante a montagem manual no Canva — cada seção do site tem seu próprio bloco no guia com texto pronto, foto a usar, cores/fontes e os cliques exatos no editor.

- [ ] **Passo 1: Escrever o guia com todas as seções, na ordem aprovada**

Conteúdo completo do arquivo `docs/superpowers/plans/2026-07-22-canva-build-guide.md`:

```markdown
# Guia de montagem — Site Renata Costa no Canva Sites

Antes de começar: Compartilhar > Canva Sites > **Criar Website**. Isso abre o editor de rolagem única.

## 1. Nav (topo, fixo)
- Texto à esquerda: `Renata Costa` — fonte Playfair Display, ~20px, cor #3d4a35
- Texto à direita: `Sobre · Serviços · Depoimentos · Contato` — fonte Quicksand, ~12px, cor #6b7563
- Fundo da barra: #F5F0E6, borda inferior fina #e5ddc8

## 2. Hero
- Fundo da seção: #F5F0E6
- Label pequena acima da foto: linha terracota (#C97B4A, ~22px de largura, 2px altura) + texto `TERAPEUTA OCUPACIONAL` (Quicksand, 10px, maiúsculas, espaçamento entre letras, cor #5F7052)
- Foto: fazer upload de `assets/site/01-hero-renata-sentada.jpg` — inserir com proporção retrato (~4:5), cantos levemente arredondados
- Nome abaixo da foto: `Renata Costa` — Playfair Display, ~34px, cor #3d4a35
- Subtítulo: `Integração sensorial e seletividade alimentar — cuidado clínico que faz sentido pra sua família.` — Quicksand, 13px, cor #6b7563
- Botão: `Fale no WhatsApp` — apenas contorno (sem preenchimento), borda #C97B4A 1.5px, texto #C97B4A, cantos levemente arredondados. Linkar para `https://wa.me/55[NUMERO]`

## 3. Sobre
- Fundo da seção: branco (#ffffff)
- Label: linha terracota + `SOBRE` (mesmo estilo da label do hero)
- Título: `Quem é Renata` — Playfair Display, ~22px, cor #3d4a35
- Foto opcional ao lado do texto: `assets/site/02-sobre-atividade-terapeutica.jpg`
- Corpo: `Formação em Terapia Ocupacional, especialização em integração sensorial e anos de experiência com crianças e famílias enfrentando seletividade alimentar. Uma escuta acolhedora, apoiada em evidência clínica.` — Quicksand, 12.5px, cor #5b5b52

## 4. Serviços
- Fundo da seção: #F5F0E6
- Label: linha terracota + `SERVIÇOS`
- Título: `Como posso ajudar` — Playfair Display, ~22px, cor #3d4a35
- Lista de 4 itens, cada um numa linha com uma seta terracota (→) à direita e uma linha divisória fina (#e5ddc8) abaixo:
  1. Seletividade alimentar
  2. Integração sensorial
  3. Avaliações (EASI, PEDI)
  4. AVDs — autonomia no dia a dia
- Fonte dos itens: Quicksand, 13px, negrito, cor #3d4a35

## 5. Depoimentos
- Fundo da seção: branco (#ffffff)
- Label: linha terracota + `DEPOIMENTOS`
- Título: `O que dizem as famílias` — Playfair Display, ~22px, cor #3d4a35
- Citação com borda esquerda terracota (2px), texto placeholder em itálico: `"Espaço reservado — depoimento a adicionar aqui depois."` — Playfair Display itálico, 13px, cor #5b5b52
- (Renata substitui esse texto por um depoimento real assim que tiver um)

## 6. Contato
- Fundo da seção: bege suave #EDE7D6
- Título: `Vamos conversar` — Playfair Display, ~24px, cor #3d4a35, centralizado
- Subtítulo: `Tire suas dúvidas e agende uma conversa inicial` — Quicksand, 12.5px, cor #6b7563, centralizado
- Botão sólido: `Fale no WhatsApp` — fundo #C97B4A, texto branco, cantos levemente arredondados. Linkar para `https://wa.me/55[NUMERO]`
- Abaixo do botão: `@renatacosta.to` (ajustar para o handle real do Instagram), Quicksand, 11px, cor #8a8a7d

## 7. Footer
- Fundo: verde escuro #3d4a35
- Texto centralizado: `© Renata Costa · Terapeuta Ocupacional` — Quicksand, 10px, cor #F5F0E6 (opacidade reduzida)

## Publicar
1. Clique em **Compartilhar** no canto superior do editor.
2. Clique em **Publicar Website**.
3. Escolha o subdomínio (ex: `renatacosta.my.canva.site`).
4. Clique em **Publicar Website** para confirmar.
```

- [ ] **Passo 2: Confirmar com a Renata o número de WhatsApp e o handle do Instagram**

O guia usa `[NUMERO]` como placeholder no link do WhatsApp e `@renatacosta.to` como placeholder do Instagram — perguntar a ela os valores reais e substituir no arquivo antes de considerar o guia pronto para uso.

---

### Task 3: Autorrevisão do guia contra o spec aprovado

**Files:**
- Modify: `docs/superpowers/plans/2026-07-22-canva-build-guide.md` (se algum gap for encontrado)

**Interfaces:**
- Consumes: `docs/superpowers/specs/2026-07-22-site-pessoal-design.md` (spec aprovado), guia escrito na Task 2.
- Produces: confirmação de que todas as 7 seções do spec têm um bloco correspondente no guia, sem texto placeholder esquecido (exceto os explicitamente combinados: depoimento e número de WhatsApp).

- [ ] **Passo 1: Checar cobertura seção por seção**

Ler `docs/superpowers/specs/2026-07-22-site-pessoal-design.md`, seção "Estrutura da página", e confirmar que os 7 itens (Nav, Hero, Sobre, Serviços, Depoimentos, Contato, Footer) aparecem no guia com conteúdo real (não "TBD").

- [ ] **Passo 2: Checar consistência de cores/fontes**

Comparar os hex codes e nomes de fonte usados no guia com a seção "Global Constraints" deste plano — devem ser idênticos em todas as 7 seções.

- [ ] **Passo 3: Marcar como pronto**

Se os passos 1 e 2 não encontrarem gaps, o guia está pronto para a Renata seguir. Reportar a ela que o material está completo e onde encontrá-lo.
