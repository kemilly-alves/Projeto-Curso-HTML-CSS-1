# Seção 2: HTML, principais tags e boas práticas

Esta seção reúne as principais tags do HTML, a diferença entre HTML e HTML5, e as boas práticas de formulários, mídia e semântica.

> Os atalhos de comentar código e Word Wrap no VS Code estão na [documentação de introdução](html5-css-introducao.md).

---

## 1. Principais tags

### 1.1 Estrutura básica da página

| Tag HTML | Para que serve |
| --- | --- |
| `<!DOCTYPE html>` | Define que o documento é HTML5 |
| `<html>` | Elemento raiz da página |
| `<head>` | Contém informações da página (metadados) |
| `<title>` | Título da página (aparece na aba do navegador) |
| `<meta>` | Define metadados (charset, viewport, etc.) |
| `<body>` | Conteúdo visível da página |

### 1.2 Texto e conteúdo

| Tag HTML | Para que serve |
| --- | --- |
| `<h1>` a `<h6>` | Títulos e subtítulos (hierarquia) |
| `<p>` | Parágrafo |
| `<br>` | Quebra de linha |
| `<hr>` | Linha horizontal |
| `<strong>` | Texto em negrito (semântico) |
| `<b>` | Negrito (visual) |
| `<em>` | Itálico (semântico) |
| `<i>` | Itálico (visual) |
| `<span>` | Texto inline (sem quebra de linha) |
| `<div>` | Container genérico (bloco) |

### 1.3 Links e navegação

| Tag HTML | Para que serve |
| --- | --- |
| `<a>` | Criar links |
| `<nav>` | Área de navegação |
| `<link>` | Importar arquivos externos (CSS, favicon, etc.) |

```html
<a href="https://github.com">GitHub</a>
```

### 1.4 Imagens e mídia

| Tag HTML | Para que serve |
| --- | --- |
| `<img>` | Inserir imagem |
| `<video>` | Inserir vídeo |
| `<audio>` | Inserir áudio |
| `<source>` | Fonte de mídia (vídeo/áudio) |

```html
<img src="foto.jpg" alt="Minha foto">
```

### 1.5 Listas

| Tag HTML | Para que serve |
| --- | --- |
| `<ul>` | Lista não ordenada |
| `<ol>` | Lista ordenada |
| `<li>` | Item da lista |

### 1.6 Tabelas

| Tag HTML | Para que serve |
| --- | --- |
| `<table>` | Criar tabela |
| `<thead>` | Cabeçalho da tabela |
| `<tbody>` | Corpo da tabela |
| `<tr>` | Linha da tabela |
| `<th>` | Célula de cabeçalho |
| `<td>` | Célula de dados |

### 1.7 Formulários

| Tag HTML | Para que serve |
| --- | --- |
| `<form>` | Formulário |
| `<input>` | Campo de entrada |
| `<textarea>` | Área de texto |
| `<button>` | Botão |
| `<label>` | Rótulo do campo |
| `<select>` | Lista suspensa |
| `<option>` | Opção do select |

### 1.8 Tags semânticas (HTML5) ⭐

| Tag HTML | Para que serve |
| --- | --- |
| `<header>` | Cabeçalho da página |
| `<main>` | Conteúdo principal |
| `<section>` | Seção do conteúdo |
| `<article>` | Artigo |
| `<aside>` | Conteúdo lateral |
| `<footer>` | Rodapé |

---

## 2. HTML e HTML5

**HTML** é a linguagem de marcação usada para criar páginas web. O termo pode se referir à linguagem como um todo ou às versões antigas (HTML4, XHTML etc.).

**HTML5** é a versão mais recente e evoluída do HTML. Ela trouxe muitos recursos novos.

### 2.1 Novas tags semânticas

Antes (HTML antigo):

```html
<div id="header"></div>
<div id="footer"></div>
```

HTML5:

```html
<header></header>
<footer></footer>
```

Novas tags: `<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` e `<nav>`.

Mais semântica significa código mais organizado e melhor para SEO.

### 2.2 Suporte nativo a áudio e vídeo

Antes era preciso usar Flash ou plugins. No HTML5:

```html
<video src="video.mp4" controls></video>
<audio src="som.mp3" controls></audio>
```

Sem plugins externos.

### 2.3 Novos tipos de input

Antes:

```html
<input type="text">
```

HTML5:

```html
<input type="email">
<input type="date">
<input type="number">
<input type="tel">
```

O navegador faz validação automática.

### 2.4 Armazenamento local (Web Storage)

O HTML antigo não tinha. O HTML5 trouxe `localStorage` e `sessionStorage`, que permitem salvar dados no navegador.

### 2.5 APIs novas

O HTML5 trouxe APIs como Geolocation (localização), Canvas (desenho gráfico), Drag and Drop e Web Workers.

### 2.6 Melhor suporte mobile

O HTML5 foi pensado para celulares, tablets e apps web. Isso resulta em uma melhor experiência para o usuário.

---

## 3. Tags em detalhe

### 3.1 `<img>`

Exibe imagens. Atributos principais:

- **`src`**: caminho ou URL da imagem
- **`alt`**: texto alternativo, exibido se a imagem não carregar. É importante para **acessibilidade** e **SEO**

```html
<img src="logo.png" alt="Logo da empresa">
```

### 3.2 `<a>` com `href`, `target` e `rel`

- **`href`**: define o link de destino
- **`target="_blank"`**: abre o link em uma nova aba
- **`rel`**: informa a relação entre a página atual e o link de destino

Exemplo usado no curso:

```html
<a href="https://google.com" target="_blank" rel="external">
  Ir para o Google
</a>
```

Como deve ser usado hoje:

```html
<a href="https://google.com" target="_blank" rel="noopener noreferrer">
  Ir para o Google
</a>
```

> Observação: `rel="external"` não é um valor oficial do HTML. Hoje, para links que abrem em nova aba, a prática recomendada é `rel="noopener noreferrer"`, que protege a página de origem.

**Para que serve a `<a>`:**

- Criar links
- Navegar entre páginas
- Apontar para seções da mesma página
- Baixar arquivos

### 3.3 `<ol>`, `<ul>` e `<li>`

- **`<ol>`**: lista ordenada (com números)
- **`<ul>`**: lista não ordenada (com pontos)
- **`<li>`**: item da lista (usado dentro de `ol` ou `ul`)

Atributos do `<ol>`:

- **`type`**: tipo de numeração
  - `1` (números)
  - `A` (letras maiúsculas)
  - `a` (letras minúsculas)
  - `I` (romanos)
- **`start`**: número a partir do qual a lista começa

```html
<ol type="A" start="3">
    <li>Item</li>
    <li>Item</li>
</ol>
```

```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>
```

### 3.4 `<tr>`, `<th>` e `<td>`

Usadas em tabelas:

- **`<tr>`**: linha da tabela
- **`<th>`**: célula de cabeçalho
- **`<td>`**: célula de dados

```html
<table>
    <tr>
        <th>Nome</th>
        <th>Idade</th>
    </tr>
    <tr>
        <td>Ana</td>
        <td>25</td>
    </tr>
</table>
```

### 3.5 `<br>`

Quebra a linha do conteúdo. Não é indicada para layout, sendo usada apenas em situações simples ou didáticas. Em projetos maiores, o espaçamento deve ser feito com **CSS**.

### 3.6 `<strong>`

Dá destaque semântico ao texto, indicando que ele é importante:

```html
<strong>Qual o seu nível como programador atualmente?</strong>
```

Além de deixar o texto em negrito, o `<strong>` comunica **importância** para leitores de tela.

---

## 4. Formulários

### 4.1 `<label>` e o atributo `for`

O `<label>` associa um texto descritivo a um campo de formulário. Quando o `for` do `<label>` tem o mesmo valor do `id` do `<input>`, cria-se uma ligação entre eles.

```html
<label for="email">E-mail</label>
<input type="email" id="email">
```

Benefícios:

- Melhora a acessibilidade (leitores de tela)
- Permite clicar no texto para focar no campo
- Torna o formulário mais semântico
- É uma boa prática recomendada pelo HTML5

### 4.2 Campos obrigatórios com `required`

Antigamente era comum usar um asterisco (*) ao lado do rótulo para indicar campo obrigatório. Essa abordagem **não é boa prática**, pois não garante validação automática nem acessibilidade.

A boa prática atual é usar o atributo **`required`** no próprio `<input>`:

```html
<input type="text" id="pnome" name="pnome" placeholder="Seu primeiro nome" required>
<input type="text" id="unome" name="unome" placeholder="Último nome" required>
```

Benefícios do `required`:

- Garante validação automática pelo navegador
- Melhora a acessibilidade
- Evita validações manuais desnecessárias em JavaScript
- Segue o padrão recomendado pelo HTML5

### 4.3 Campo de texto (`type="text"`)

Recebe informações textuais simples, como nome, sobrenome, cidade etc.

```html
<input type="text" id="unome" name="unome" placeholder="Último nome" required>
```

Atributos importantes:

- `id`: identifica o campo
- `name`: usado no envio dos dados do formulário
- `placeholder`: texto de ajuda dentro do campo
- `required`: torna o preenchimento obrigatório

### 4.4 Radio (escolha única)

Permite que o usuário escolha **apenas uma opção** dentro de um grupo.

```html
<input type="radio" name="nivel" value="iniciante">
```

Regras:

- Todos os radios do grupo devem ter o **mesmo `name`**
- Apenas **uma opção** pode ser selecionada
- O atributo `checked` define a opção padrão

```html
<input type="radio" name="nivel" value="iniciante" checked>
```

### 4.5 Checkbox (múltipla escolha)

Permite que o usuário selecione **uma ou mais opções ao mesmo tempo**. Cada checkbox funciona de forma independente.

```html
<input type="checkbox" id="tecnologia" name="tecnologia" value="HTML">
<label for="tecnologia">HTML</label>
```

Quando as opções fazem parte do mesmo assunto, use o **mesmo `name`** e um `value` diferente para cada uma. Isso facilita o tratamento dos dados no backend:

```html
<input type="checkbox" id="html" name="tecnologias" value="HTML">
<label for="html">HTML</label>

<input type="checkbox" id="css" name="tecnologias" value="CSS">
<label for="css">CSS</label>

<input type="checkbox" id="js" name="tecnologias" value="JavaScript">
<label for="js">JavaScript</label>

<input type="checkbox" id="php" name="tecnologias" value="PHP">
<label for="php">PHP</label>
```

### 4.6 Select e option

O `<select>` cria uma **lista suspensa**. Cada opção é definida com `<option>`.

Opção desabilitada como placeholder: é boa prática usar uma primeira opção **desabilitada** para forçar uma escolha válida. Com o `select` obrigatório, o formulário não é enviado sem essa escolha.

```html
<select id="escolaridade" name="escolaridade" required>
    <option selected disabled value="">Selecione</option>
    <option value="fundamental">Ensino fundamental</option>
    <option value="medio">Ensino médio</option>
    <option value="superior">Ensino superior</option>
</select>
```

### 4.7 Data e hora (`datetime-local`)

Permite selecionar **data e hora** por um componente nativo do navegador. Evita erros de digitação, padroniza o formato e melhora a experiência do usuário.

```html
<label for="nascimento">Data de nascimento:</label>
<input type="datetime-local" id="nascimento" name="nascimento">
```

### 4.8 Datalist (sugestões)

O `<datalist>` cria uma **lista de sugestões** para um `<input>`, funcionando como um autocomplete nativo. A ligação acontece quando o `list` do `<input>` tem o mesmo valor do `id` do `<datalist>`:

```html
<input list="carros" name="carro" placeholder="Procurando algum carro">
<datalist id="carros">
    <option value="Gol 1.6"></option>
    <option value="Golf 1.4"></option>
    <option value="BMW 1.0"></option>
    <option value="Onix 1.0"></option>
</datalist>
```

| Elemento | Permite digitar livremente? |
| --- | --- |
| `select` | ❌ Não |
| `datalist` | ✅ Sim |

O usuário pode escolher uma opção da lista ou digitar um valor diferente.

### 4.9 Comparação de escolhas

| Tipo | Permite múltiplas escolhas? |
| --- | --- |
| `radio` | ❌ Não |
| `checkbox` | ✅ Sim |
| `select` | ❌ Não (por padrão) |

### 4.10 Botão de envio

`input type="submit"` envia os dados do formulário:

```html
<input type="submit" value="Cadastrar">
```

Alternativa com `<button>`, que oferece mais flexibilidade de estilização e conteúdo:

```html
<button type="submit">Cadastrar</button>
```

---

## 5. Vídeo e áudio

### 5.1 `<video>`

Incorpora vídeos diretamente na página, usando recursos nativos do navegador:

```html
<video poster="thumb.png" width="420" height="340" controls loop muted autoplay>
    <source src="natureza.mp4" type="video/mp4">
</video>
```

Compatibilidade com múltiplos formatos: é possível adicionar vários `<source>`. O navegador usa o **primeiro formato compatível**.

```html
<video controls>
    <source src="natureza.mp4" type="video/mp4">
    <source src="natureza.webm" type="video/webm">
</video>
```

Atributos do `<video>`:

| Atributo | O que faz |
| --- | --- |
| `controls` | Exibe os controles nativos (play, pause, volume, tela cheia). Sem ele, o usuário não controla o vídeo |
| `autoplay` | Inicia automaticamente ao carregar. A maioria dos navegadores só permite se o vídeo estiver mutado |
| `muted` | Inicia sem som. Necessário para permitir o autoplay |
| `loop` | Recomeça automaticamente ao terminar. Muito usado em vídeos curtos ou demonstrativos |
| `poster` | Imagem de capa (thumbnail) exibida antes da reprodução |
| `width` / `height` | Largura e altura do player. Em projetos modernos, o tamanho costuma ser definido com CSS, mas esses atributos ainda são válidos |

O vídeo em si é definido pelo `<source>`, e o atributo `type` ajuda o navegador a identificar o formato.

### 5.2 `<audio>`

Incorpora arquivos de áudio na página:

```html
<audio controls>
    <source src="curso.mp3" type="audio/mpeg">
</audio>
```

Por padrão, o áudio **não é reproduzido automaticamente**; só toca quando o usuário clica em play.

Atributos do `<audio>`:

| Atributo | O que faz |
| --- | --- |
| `controls` | Exibe os controles nativos (play/pause, volume, barra de progresso) |
| `autoplay` | Inicia automaticamente. Navegadores modernos bloqueiam autoplay com som, então geralmente é usado com `muted` |
| `muted` | Inicia sem som. Necessário para permitir autoplay em muitos navegadores |
| `loop` | Recomeça após terminar. Muito usado em sons ambientes ou trilhas curtas |

Combinação de atributos:

```html
<audio controls autoplay muted loop>
    <source src="curso.mp3" type="audio/mpeg">
</audio>
```

Nesse caso, o áudio inicia sozinho, sem som, em repetição e com controles visíveis.

### 5.3 Resumo de mídia

- `<video>` e `<audio>` são recursos nativos do HTML5
- Dispensam plugins como Flash
- Oferecem melhor desempenho e acessibilidade
- Autoplay geralmente exige `muted`

---

## 6. `<details>` e `<summary>`

Criam seções que podem ser abertas ou fechadas pelo usuário, de forma nativa, sem JavaScript.

- **`<summary>`**: título clicável
- **`<details>`**: conteúdo exibido ou ocultado

```html
<details>
    <summary>Motor 1.6</summary>
    <p>O carro possui um motor super forte e rápido...</p>
</details>
```

O atributo **`open`** faz o conteúdo iniciar aberto. Sem ele, o conteúdo inicia fechado.

```html
<details open>
    <summary>Motor 1.6</summary>
    <p>O carro possui um motor super forte e rápido...</p>
</details>
```

Vários `<details>` na mesma página funcionam de forma independente:

```html
<details>
    <summary>Conforto</summary>
    <p>Carro de luxo com sensor de ré, câmeras e som de qualidade...</p>
</details>
```

Vantagens: não precisa de JavaScript, melhora a organização do conteúdo, é acessível (compatível com leitores de tela) e é ideal para FAQs, descrições e detalhes técnicos.

---

## 7. HTML semântico

HTML semântico é escrever HTML com **tags que descrevem o papel do conteúdo**. Isso ajuda navegadores, motores de busca, leitores de tela e outros desenvolvedores a entender melhor o site.

Semântica é o estudo do significado. No HTML, cada tag semântica tem um propósito: não serve só para organizar visualmente, mas para dar sentido ao conteúdo.

### 7.1 Como era antes do HTML5

Antes, era comum usar `<div>` para tudo:

```html
<div class="header"></div>
<div class="menu"></div>
<div class="conteudo"></div>
<div class="rodape"></div>
```

O navegador não entende o que é cabeçalho, menu ou rodapé. Vê apenas blocos genéricos.

### 7.2 Tags semânticas

**`<header>`**: cabeçalho da página ou de uma seção. Normalmente contém logo, título e menu de navegação.

```html
<header>
    <h1>Cabeçalho do meu site</h1>
</header>
```

**`<nav>`**: menus de navegação. Indica que aquele conteúdo é de navegação principal. Menus geralmente são estruturados com listas:

```html
<nav>
    <ul>
        <li>Home</li>
        <li>Contatos</li>
        <li>Sobre</li>
    </ul>
</nav>
```

Usar `<ul>` e `<li>` no menu melhora a organização, a acessibilidade e a leitura por leitores de tela.

**`<article>`**: conteúdo independente, que faz sentido sozinho. Pode ser um post, notícia, artigo ou card.

```html
<article>
    <h3>Seja bem-vindo ao meu site</h3>
    <p>Teste projeto HTML</p>
</article>
```

**`<aside>`**: conteúdo complementar, relacionado ao conteúdo principal. Geralmente usado para avisos, propagandas, informações extras ou barras laterais.

```html
<aside>
    Curso 100% na prática direto ao ponto.
</aside>
```

**`<footer>`**: rodapé da página ou seção. Normalmente contém direitos autorais, informações legais e links finais.

```html
<footer>
    <p>Todos os direitos reservados ao criador do site.</p>
</footer>
```

**`<div>`**: não é semântica, mas ainda é útil para agrupar elementos quando não existe uma tag semântica específica:

```html
<div>
    <article>...</article>
    <aside>...</aside>
</div>
```

### 7.3 Vantagens do HTML semântico

- Código mais organizado
- Melhor SEO (o Google entende melhor o conteúdo)
- Melhor acessibilidade
- Facilita a manutenção
- Código mais profissional

---

## 8. `type="submit"` e `type="button"`

### 8.1 `type="submit"`

Usado **dentro de um `<form>`** para enviar os dados do formulário.

```html
<form>
    <input type="text" name="nome">
    <button type="submit">Enviar</button>
</form>
```

Ou:

```html
<input type="submit" value="Enviar">
```

O que acontece:

- Envia os dados para o `action` do formulário
- Recarrega a página (se não houver JavaScript impedindo)
- Dispara o evento `submit`

### 8.2 `type="button"`

**Não envia o formulário**. Serve apenas para executar alguma ação via JavaScript.

```html
<button type="button" onclick="abrirModal()">
  Abrir Modal
</button>
```

O que acontece:

- Não envia nada
- Não recarrega a página
- Só faz algo se houver JavaScript

### 8.3 Botão sem `type` dentro de `<form>`

```html
<button>Enviar</button>
```

⚠️ Dentro de um `<form>`, o padrão é **`type="submit"`**. Isso pode causar bugs se você queria apenas um botão comum.

### 8.4 `<button>` ou `<input type="submit">`

| `<button>` | `<input type="submit">` |
| --- | --- |
| Pode ter HTML dentro (ícone, span etc.) | Só texto |
| Mais flexível | Mais simples |

Exemplo com ícone:

```html
<button type="submit">
    <i class="icon"></i> Enviar
</button>
```

Com `<input>`, isso não é possível.

---

## 9. Resumo de anotações

- HTML → **estrutura e significado**
- CSS → **aparência**
- JavaScript → **comportamento**
- Um formulário bem feito começa com **HTML semântico e acessível**
- Botão que envia formulário → `type="submit"`
- Botão que faz outra ação → `type="button"`
- Nunca deixe o botão sem `type` dentro de `<form>`
- `<details>` cria conteúdo expansível, `<summary>` é o título clicável, `open` deixa o bloco aberto por padrão
- `<datalist>` sugere valores, não obriga seleção
- `<video>` e `<audio>`: autoplay geralmente exige `muted`
