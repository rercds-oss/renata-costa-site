# Site Pessoal da Renata Costa (HTML/CSS) Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Construir o site pessoal de página única da Renata Costa como HTML/CSS estático, seguindo o design aprovado em `docs/superpowers/specs/2026-07-22-site-pessoal-design.md`.

**Architecture:** Página única (`index.html`) com 7 seções empilhadas verticalmente (Nav, Hero, Sobre, Serviços, Depoimentos, Contato, Footer), estilizada por um único `css/style.css`. Layout em coluna central (max-width ~520px), o que reproduz naturalmente o visual de "página de links" da inspiração tanto no celular quanto no desktop, sem precisar de breakpoints separados. Sem JavaScript e sem framework — é conteúdo estático, então não há teste automatizado de lógica; a verificação de cada tarefa é abrir `index.html` no navegador e conferir visualmente contra os critérios listados, mais checagens `grep` de que os elementos esperados existem no HTML.

**Tech Stack:** HTML5, CSS3 puro, Google Fonts (Playfair Display, Quicksand). Nenhuma dependência de build.

## Global Constraints

- Cores: sálvia `#5F7052` / sálvia escuro `#4B5940`, terracota `#C97B4A`, creme `#F5F0E6`, bege `#EDE7D6`, texto escuro `#3d4a35`, texto corpo `#6b7563`, texto mudo `#5b5b52`, texto claro `#8a8a7d`, divisor `#e5ddc8`, rodapé `#3d4a35`.
- Tipografia: `Playfair Display` (títulos/nome), `Quicksand` (corpo/labels/botões) — carregadas via Google Fonts.
- Direção visual: editorial clean — fundos claros predominantes (creme/branco/bege), cor só em detalhes (linha fina, labels, texto/borda de botão). Nenhum bloco de cor escura cheio, nenhum overlay pesado sobre foto.
- Link do WhatsApp: `https://wa.me/5544988325654` (usado no botão do Hero e do Contato).
- Instagram: `@renatacosta.to`.
- Fotos (já existem em `assets/site/`): `01-hero-renata-sentada.jpg`, `02-sobre-atividade-terapeutica.jpg`, `03-servicos-salvia.jpg`.
- Projeto ainda não é um repositório git — será inicializado na Task 1.

---

### Task 1: Inicializar repositório e scaffold do projeto (HTML skeleton + design tokens CSS)

**Files:**
- Create: `index.html`
- Create: `css/style.css`
- Create: `.gitignore`

**Interfaces:**
- Produces: estrutura `<head>` com fontes carregadas e `<link rel="stylesheet" href="css/style.css">`; `<body>` com `<main class="page">` vazio pronto para receber as seções nas próximas tasks; variáveis CSS (`--sage`, `--sage-dark`, `--terracotta`, `--cream`, `--beige`, `--white`, `--text-dark`, `--text-body`, `--text-muted`, `--text-light`, `--divider`, `--footer-bg`) e classe `.container` (max-width 520px, centralizado) que as próximas tasks reutilizam.

- [ ] **Passo 1: Inicializar o git**

```bash
cd "C:/Users/rercd/projects/renata-costa-site"
git init
```

Expected: `Initialized empty Git repository in .../renata-costa-site/.git/`

- [ ] **Passo 2: Criar `.gitignore`**

```
.superpowers/
.DS_Store
```

- [ ] **Passo 3: Criar `index.html`**

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Renata Costa | Terapeuta Ocupacional</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital@0;1&family=Quicksand:wght@400;500;600&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>
  <main class="page">
  </main>
</body>
</html>
```

- [ ] **Passo 4: Criar `css/style.css` com os design tokens e base**

```css
:root {
  --sage: #5F7052;
  --sage-dark: #4B5940;
  --terracotta: #C97B4A;
  --cream: #F5F0E6;
  --beige: #EDE7D6;
  --white: #ffffff;
  --text-dark: #3d4a35;
  --text-body: #6b7563;
  --text-muted: #5b5b52;
  --text-light: #8a8a7d;
  --divider: #e5ddc8;
  --footer-bg: #3d4a35;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: 'Quicksand', sans-serif;
  color: var(--text-dark);
  background: var(--cream);
}

.page {
  max-width: 520px;
  margin: 0 auto;
  background: var(--cream);
  min-height: 100vh;
}

.section {
  padding: 30px 24px;
}

.label {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 12px;
}

.label__line {
  width: 22px;
  height: 2px;
  background: var(--terracotta);
}

.label__text {
  font-size: 10px;
  letter-spacing: 2px;
  color: var(--sage);
  text-transform: uppercase;
}

.heading {
  font-family: 'Playfair Display', Georgia, serif;
  color: var(--text-dark);
  margin: 0 0 10px;
}

.btn {
  display: inline-block;
  font-family: 'Quicksand', sans-serif;
  font-size: 12.5px;
  padding: 10px 22px;
  border-radius: 2px;
  text-decoration: none;
}

.btn--outline {
  border: 1.5px solid var(--terracotta);
  color: var(--terracotta);
}

.btn--solid {
  background: var(--terracotta);
  color: #fff;
}
```

- [ ] **Passo 5: Verificar renderização inicial**

Abrir `index.html` no navegador.
Expected: página em branco com fundo creme, coluna central (a `<main>` ainda está vazia, então não há mais conteúdo visível — isso é esperado nesta etapa).

- [ ] **Passo 6: Commit**

```bash
git add index.html css/style.css .gitignore
git commit -m "chore: scaffold static site with design tokens"
```

---

### Task 2: Seção Nav + Hero

**Files:**
- Modify: `index.html` (dentro de `<main class="page">`)
- Modify: `css/style.css` (adicionar ao final)

**Interfaces:**
- Consumes: variáveis CSS e classes `.section`, `.label`, `.label__line`, `.label__text`, `.heading`, `.btn`, `.btn--outline` da Task 1.
- Produces: classes `.nav`, `.hero`, `.hero__photo`, `.hero__name`, `.hero__subtitle` — reaproveitadas apenas visualmente (não por outras seções).

- [ ] **Passo 1: Adicionar Nav e Hero dentro de `<main class="page">` em `index.html`**

```html
    <nav class="nav">
      <div class="nav__name">Renata Costa</div>
      <div class="nav__links">Sobre · Serviços · Depoimentos · Contato</div>
    </nav>

    <section class="section hero">
      <div class="label">
        <div class="label__line"></div>
        <div class="label__text">Terapeuta Ocupacional</div>
      </div>
      <div class="hero__photo">
        <img src="assets/site/01-hero-renata-sentada.jpg" alt="Renata Costa, terapeuta ocupacional" />
      </div>
      <h1 class="heading hero__name">Renata Costa</h1>
      <p class="hero__subtitle">Integração sensorial e seletividade alimentar — cuidado clínico que faz sentido pra sua família.</p>
      <a class="btn btn--outline" href="https://wa.me/5544988325654">Fale no WhatsApp</a>
    </section>
```

- [ ] **Passo 2: Adicionar os estilos de Nav e Hero ao final de `css/style.css`**

```css
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 14px 20px;
  background: var(--cream);
  border-bottom: 1px solid var(--divider);
}

.nav__name {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 15px;
  color: var(--text-dark);
}

.nav__links {
  font-size: 10px;
  color: var(--text-body);
  letter-spacing: 0.5px;
}

.hero {
  background: var(--cream);
}

.hero__photo {
  width: 100%;
  aspect-ratio: 4 / 5;
  border-radius: 6px;
  overflow: hidden;
  margin-bottom: 18px;
}

.hero__photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 15%;
}

.hero__name {
  font-size: 34px;
}

.hero__subtitle {
  font-size: 13px;
  color: var(--text-body);
  max-width: 280px;
  line-height: 1.5;
  margin: 0 0 16px;
}
```

- [ ] **Passo 3: Verificar no navegador**

Abrir `index.html`.
Expected: barra de nav com "Renata Costa" à esquerda e os 4 links à direita; abaixo, seção hero com label "TERAPEUTA OCUPACIONAL", foto da Renata em proporção retrato com cantos arredondados, nome grande "Renata Costa" em serifada, subtítulo, e botão contornado "Fale no WhatsApp".

- [ ] **Passo 4: Verificar que o link do WhatsApp está correto**

```bash
grep -o 'https://wa.me/[0-9]*' index.html
```

Expected: `https://wa.me/5544988325654` aparece pelo menos uma vez.

- [ ] **Passo 5: Commit**

```bash
git add index.html css/style.css
git commit -m "feat: add nav and hero sections"
```

---

### Task 3: Seção Sobre + Serviços

**Files:**
- Modify: `index.html` (após a seção `.hero`)
- Modify: `css/style.css`

**Interfaces:**
- Consumes: `.section`, `.label`, `.heading` (Task 1).
- Produces: `.sobre`, `.sobre__photo`, `.servicos`, `.servicos__list`, `.servicos__item` — não reaproveitadas por outras seções.

- [ ] **Passo 1: Adicionar Sobre e Serviços em `index.html`, logo após `</section>` do hero**

```html
    <section class="section sobre" style="background: var(--white);">
      <div class="label">
        <div class="label__line"></div>
        <div class="label__text">Sobre</div>
      </div>
      <h2 class="heading" style="font-size:22px;">Quem é Renata</h2>
      <div class="sobre__photo">
        <img src="assets/site/02-sobre-atividade-terapeutica.jpg" alt="Renata Costa em atendimento" />
      </div>
      <p class="sobre__text">Formação em Terapia Ocupacional, especialização em integração sensorial e anos de experiência com crianças e famílias enfrentando seletividade alimentar. Uma escuta acolhedora, apoiada em evidência clínica.</p>
    </section>

    <section class="section servicos">
      <div class="label">
        <div class="label__line"></div>
        <div class="label__text">Serviços</div>
      </div>
      <h2 class="heading" style="font-size:22px;">Como posso ajudar</h2>
      <ul class="servicos__list">
        <li class="servicos__item"><span>Seletividade alimentar</span><span class="servicos__arrow">→</span></li>
        <li class="servicos__item"><span>Integração sensorial</span><span class="servicos__arrow">→</span></li>
        <li class="servicos__item"><span>Avaliações (EASI, PEDI)</span><span class="servicos__arrow">→</span></li>
        <li class="servicos__item servicos__item--last"><span>AVDs — autonomia no dia a dia</span><span class="servicos__arrow">→</span></li>
      </ul>
    </section>
```

- [ ] **Passo 2: Adicionar os estilos ao final de `css/style.css`**

```css
.sobre__photo {
  width: 100%;
  aspect-ratio: 4 / 5;
  border-radius: 6px;
  overflow: hidden;
  margin: 14px 0;
}

.sobre__photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 15%;
}

.sobre__text {
  font-size: 12.5px;
  color: var(--text-muted);
  line-height: 1.6;
  max-width: 520px;
  margin: 0;
}

.servicos {
  background: var(--cream);
}

.servicos__list {
  list-style: none;
  padding: 0;
  margin: 16px 0 0;
}

.servicos__item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 14px 0;
  border-bottom: 1px solid var(--divider);
  font-size: 13px;
  font-weight: 600;
  color: var(--text-dark);
}

.servicos__item--last {
  border-bottom: none;
}

.servicos__arrow {
  color: var(--terracotta);
  font-size: 16px;
  font-weight: 400;
}
```

- [ ] **Passo 3: Verificar no navegador**

Abrir `index.html`.
Expected: seção "Sobre" com fundo branco, foto e parágrafo de bio; seção "Serviços" com fundo creme e lista de 4 itens com seta terracota e linha divisória entre eles (o último item sem linha).

- [ ] **Passo 4: Verificar que os 4 serviços estão presentes**

```bash
grep -c "servicos__item" index.html
```

Expected: `4` (uma ocorrência por `<li>`, contando a classe extra do último item — se o grep contar `servicos__item--last` junto, o total pode aparecer maior; confirme visualmente que são exatamente 4 `<li>` na lista).

- [ ] **Passo 5: Commit**

```bash
git add index.html css/style.css
git commit -m "feat: add sobre and servicos sections"
```

---

### Task 4: Seção Depoimentos + Contato + Footer

**Files:**
- Modify: `index.html` (após a seção `.servicos`)
- Modify: `css/style.css`

**Interfaces:**
- Consumes: `.section`, `.label`, `.heading`, `.btn`, `.btn--solid` (Task 1).
- Produces: `.depoimentos__quote`, `.contato`, `.contato__handle`, `.footer` — fim da página, nenhuma task depende delas.

- [ ] **Passo 1: Adicionar Depoimentos, Contato e Footer em `index.html`, logo após `</section>` de serviços**

```html
    <section class="section depoimentos" style="background: var(--white);">
      <div class="label">
        <div class="label__line"></div>
        <div class="label__text">Depoimentos</div>
      </div>
      <h2 class="heading" style="font-size:22px;">O que dizem as famílias</h2>
      <blockquote class="depoimentos__quote">Espaço reservado — depoimento a adicionar aqui depois.</blockquote>
    </section>

    <section class="section contato" style="background: var(--beige); text-align:center;">
      <h2 class="heading" style="font-size:24px;">Vamos conversar</h2>
      <p class="contato__subtitle">Tire suas dúvidas e agende uma conversa inicial</p>
      <a class="btn btn--solid" href="https://wa.me/5544988325654">Fale no WhatsApp</a>
      <div class="contato__handle">@renatacosta.to</div>
    </section>

    <footer class="footer">© Renata Costa · Terapeuta Ocupacional</footer>
```

- [ ] **Passo 2: Adicionar os estilos ao final de `css/style.css`**

```css
.depoimentos__quote {
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  color: var(--text-muted);
  font-size: 13px;
  line-height: 1.6;
  border-left: 2px solid var(--terracotta);
  padding: 4px 0 4px 16px;
  margin: 0;
}

.contato__subtitle {
  font-size: 12.5px;
  color: var(--text-body);
  margin: 0 0 18px;
}

.contato__handle {
  font-size: 11px;
  color: var(--text-light);
  margin-top: 16px;
}

.footer {
  background: var(--footer-bg);
  color: rgba(245, 240, 230, 0.7);
  font-size: 10px;
  text-align: center;
  padding: 12px 24px;
}
```

- [ ] **Passo 3: Verificar no navegador**

Abrir `index.html`.
Expected: seção "Depoimentos" com fundo branco e citação em itálico com borda terracota à esquerda; seção "Contato" com fundo bege, título centralizado, botão sólido terracota, e handle do Instagram abaixo; rodapé verde escuro com copyright centralizado.

- [ ] **Passo 4: Verificar que os dois links de WhatsApp e o handle do Instagram estão presentes**

```bash
grep -c 'wa.me/5544988325654' index.html
grep -c '@renatacosta.to' index.html
```

Expected: primeiro comando retorna `2` (hero + contato); segundo retorna `1`.

- [ ] **Passo 5: Commit**

```bash
git add index.html css/style.css
git commit -m "feat: add depoimentos, contato and footer sections"
```

---

### Task 5: Revisão final contra o spec

**Files:**
- Modify: `index.html` ou `css/style.css` (se algum gap for encontrado)

**Interfaces:**
- Consumes: `docs/superpowers/specs/2026-07-22-site-pessoal-design.md` (spec aprovado), `index.html` e `css/style.css` completos das Tasks 1-4.

- [ ] **Passo 1: Checar as 7 seções contra a "Estrutura da página" do spec**

Abrir o spec e o `index.html` lado a lado. Confirmar que aparecem, na ordem: Nav, Hero, Sobre, Serviços, Depoimentos, Contato, Footer.

- [ ] **Passo 2: Checar que nenhum bloco de cor escura cheio foi introduzido**

```bash
grep -n "background: var(--sage" css/style.css
```

Expected: nenhuma ocorrência (a direção "editorial clean" usa sálvia só em `--label__text` e na linha de divisor visual dos mockups anteriores, não como fundo de seção — confirmar visualmente que nenhuma seção usa `--sage`/`--sage-dark` como `background`).

- [ ] **Passo 3: Abrir `index.html` no navegador e conferir a rolagem completa de cima a baixo**

Expected: a leitura da página inteira corresponde à ordem e ao conteúdo do guia `docs/superpowers/plans/2026-07-22-canva-build-guide.md` (mesmo texto, mesmas cores, mesma ordem — esse arquivo continua servindo de referência de conteúdo mesmo não sendo mais usado para montagem no Canva).

- [ ] **Passo 4: Commit final**

```bash
git add -A
git commit -m "docs: final review pass on static site against spec"
```
