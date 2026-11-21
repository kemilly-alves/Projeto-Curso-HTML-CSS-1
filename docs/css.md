# Seção 3: CSS

Esta seção reúne os seletores, as principais propriedades, as formas de aplicar CSS, cores, fontes, espaçamento, posicionamento, Flexbox, `z-index` e unidades.

---

## 1. Seletores (quem você está estilizando)

| Seletor CSS | Para que serve |
| --- | --- |
| `*` | Seleciona todos os elementos |
| `tag` | Seleciona uma tag (ex: `p`, `div`) |
| `.classe` | Seleciona elementos por classe |
| `#id` | Seleciona elementos por id |
| `tag, tag` | Seleciona vários elementos |
| `tag > tag` | Seleciona filhos diretos |
| `tag tag` | Seleciona descendentes |
| `tag:hover` | Estilo ao passar o mouse |
| `tag::before` / `tag::after` | Pseudo-elementos |

---

## 2. Propriedades principais

### 2.1 Layout e box model

| Propriedade CSS | Para que serve |
| --- | --- |
| `width` | Largura |
| `height` | Altura |
| `max-width` | Largura máxima |
| `min-height` | Altura mínima |
| `margin` | Espaçamento externo |
| `padding` | Espaçamento interno |
| `border` | Borda |
| `box-sizing` | Modelo de caixa (`border-box`) |

### 2.2 Posicionamento

| Propriedade CSS | Para que serve |
| --- | --- |
| `position` | Tipo de posicionamento (`static`, `relative`, `absolute`, `fixed`, `sticky`) |
| `top`, `right`, `bottom`, `left` | Posição do elemento |
| `z-index` | Ordem de sobreposição |
| `overflow` | Controle de conteúdo excedente |

### 2.3 Display e visibilidade

| Propriedade CSS | Para que serve |
| --- | --- |
| `display` | Tipo de exibição (`block`, `inline`, `inline-block`, `flex`, `grid`, `none`) |
| `visibility` | Visibilidade (`visible`, `hidden`) |
| `opacity` | Transparência |

### 2.4 Flexbox

| Propriedade CSS | Para que serve |
| --- | --- |
| `display: flex` | Ativa o flexbox |
| `flex-direction` | Direção (`row`, `column`) |
| `justify-content` | Alinhamento no eixo principal |
| `align-items` | Alinhamento no eixo cruzado |
| `align-content` | Alinhamento de linhas |
| `gap` | Espaço entre itens |
| `flex-wrap` | Quebra de linha |
| `flex` | Proporção do item |

### 2.5 Grid Layout

| Propriedade CSS | Para que serve |
| --- | --- |
| `display: grid` | Ativa o grid |
| `grid-template-columns` | Define colunas |
| `grid-template-rows` | Define linhas |
| `gap` | Espaçamento entre linhas e colunas (`grid-gap` é o nome antigo) |
| `grid-column` | Posição na coluna |
| `grid-row` | Posição na linha |

### 2.6 Texto e fontes

| Propriedade CSS | Para que serve |
| --- | --- |
| `color` | Cor do texto |
| `font-size` | Tamanho da fonte |
| `font-family` | Tipo de fonte |
| `font-weight` | Espessura da fonte |
| `text-align` | Alinhamento do texto |
| `text-decoration` | Sublinhado, etc. |
| `line-height` | Altura da linha |
| `letter-spacing` | Espaçamento entre letras |

### 2.7 Cores e fundo

| Propriedade CSS | Para que serve |
| --- | --- |
| `background` | Fundo (cor, imagem, etc.) |
| `background-color` | Cor de fundo |
| `background-image` | Imagem de fundo |
| `background-size` | Tamanho da imagem |
| `background-position` | Posição da imagem |

### 2.8 Bordas e sombras

| Propriedade CSS | Para que serve |
| --- | --- |
| `border-radius` | Bordas arredondadas |
| `box-shadow` | Sombra do elemento |
| `text-shadow` | Sombra do texto |

### 2.9 Animações e efeitos

| Propriedade CSS | Para que serve |
| --- | --- |
| `transition` | Transição suave |
| `transform` | Transformações (`scale`, `rotate`, `translate`) |
| `animation` | Animações com keyframes |

---

## 3. Dica de dev

Se você dominar bem:

- display / flex / grid
- margin / padding / border
- position
- font / color / background

você já está muito bem em CSS.

---

## 4. CSS e CSS3

**CSS** é a linguagem de estilo para HTML. Assim como no HTML, o termo pode se referir à linguagem em geral ou às versões antigas.

**CSS3** é a evolução do CSS, com muitos recursos novos.

### 4.1 Bordas arredondadas

Antes, só era possível com imagens. No CSS3:

```css
border-radius: 10px;
```

### 4.2 Sombras

Antes, era difícil de fazer. No CSS3:

```css
box-shadow: 0 0 10px black;
text-shadow: 2px 2px 5px gray;
```

### 4.3 Gradientes

Antes, eram feitos com imagens. No CSS3:

```css
background: linear-gradient(red, blue);
```

### 4.4 Animações e transições

Antes, eram feitas com JavaScript ou Flash. No CSS3:

```css
transition: 0.3s;
transform: scale(1.1);
```

### 4.5 Layout moderno (Flexbox e Grid)

Antes, o layout era feito com `float` e `table`. No CSS3:

```css
display: flex;
display: grid;
```

### 4.6 Responsividade (media queries)

```css
@media (max-width: 768px) {
    body { background: red; }
}
```

### 4.7 Resumo

- HTML → linguagem
- HTML5 → versão moderna do HTML
- CSS → linguagem
- CSS3 → versão moderna do CSS

Hoje, quando falamos de "HTML" e "CSS", geralmente já estamos falando de HTML5 e CSS3.

---

## 5. Formas de aplicar CSS

Existem três maneiras principais de aplicar estilos em um documento HTML.

### 5.1 CSS inline

O CSS é aplicado diretamente na tag, usando o atributo `style`.

```html
<h1 style="color: red; font-size: 14px;">
    Bem-vindo ao meu projeto!
</h1>
```

Não é boa prática, porque:

- Mistura conteúdo (HTML) com estilo (CSS)
- Dificulta a manutenção
- Não permite reaproveitamento de estilos

### 5.2 CSS interno

O CSS fica dentro do próprio arquivo HTML, na tag `<style>`, geralmente dentro do `<head>`.

```html
<style>
    h1 {
        color: green;
        font-size: 14px;
    }
</style>
```

Também não é boa prática, porque:

- O estilo fica limitado a apenas aquela página
- Pode deixar o HTML grande e confuso em projetos maiores

### 5.3 CSS externo (melhor prática)

O CSS fica em um arquivo separado `.css`, importado no HTML com a tag `<link>`.

Arquivo `styles.css`:

```css
h1 {
    color: blue;
    font-size: 14px;
}
```

No arquivo HTML:

```html
<link rel="stylesheet" href="styles.css">
```

É a melhor prática, porque:

- Mantém o código organizado
- Facilita a manutenção
- Permite reutilizar estilos em várias páginas
- Segue o padrão profissional de desenvolvimento

Sempre que possível, use CSS externo, principalmente em projetos reais.

### 5.4 Classe e ID

**Classe (`class`)**

- Seleciona um ou mais elementos
- Pode ser reutilizada várias vezes na mesma página
- No CSS, usa ponto (`.`)
- No HTML, usa o atributo `class`

```css
.primeiro-h1 {
    color: red;
}
```

**ID (`id`)**

- Seleciona apenas um elemento
- Não deve ser repetido na mesma página
- No CSS, usa hashtag (`#`)
- No HTML, usa o atributo `id`

```css
#titulo {
    color: blue;
}
```

Resumo rápido:

- `.` → classe → vários elementos
- `#` → id → um único elemento

---

## 6. Cores no CSS

### 6.1 Nome da cor

- Nome em inglês
- Simples, sem transparência

```css
color: red;
color: blue;
```

Existem cerca de 148 nomes de cores no CSS. Na prática de projetos reais, quase não são usados.

### 6.2 Hexadecimal (`#`)

- Começa com `#`
- Forma mais usada
- Formato `#RRGGBB` (vermelho, verde, azul)

```css
color: #ff0000;       /* vermelho */
background: #1e90ff;
color: #fff;          /* branco (forma abreviada) */
```

Vantagens: muito comum em design systems, fácil de copiar do Figma e compacto.

### 6.3 RGB

- Valores de 0 a 255 para vermelho, verde e azul
- Sem transparência

```css
color: rgb(255, 0, 0);
```

### 6.4 RGBA

- RGB + transparência
- Opacidade de 0 (transparente) a 1 (opaco)

```css
background: rgba(0, 0, 0, 0.5);
```

Sintaxe moderna, com barra e porcentagem:

```css
background: rgb(0 0 0 / 50%);
```

### 6.5 HSL e HSLA

- **HSL**: matiz, saturação e luminosidade
- **HSLA**: HSL + transparência

```css
color: hsl(200, 100%, 50%);
color: hsla(240, 100%, 50%, 0.3);
```

Muito bom para criar variações de uma mesma cor. Por exemplo, para escurecer:

```css
color: hsl(200, 100%, 40%);
```

### 6.6 Resumo de cores

| Formato | Quando usar |
| --- | --- |
| `#hex` | Uso padrão e comum |
| `rgb()` | Quando precisa de transparência |
| `hsl()` | Quando quer controlar variações |
| `red`, `blue` | Apenas para testes rápidos |

Em projetos reais, normalmente se usa:

- `#hex` para cores fixas
- `rgba()` para overlays
- `hsl()` em design systems

---

## 7. Fontes

### 7.1 `font-size` e `font-family`

- **`font-size`** controla o tamanho da letra

```css
font-size: 16px;
font-size: 1.2rem;
```

- **`font-family`** define qual fonte será usada. Pode ter várias opções: a fonte principal e as alternativas

```css
font-family: Arial, Helvetica, sans-serif;
```

### 7.2 Usando Google Fonts

1. No **Google Fonts**, escolha a fonte desejada.
2. Copie o **código de importação** fornecido pelo site.
3. Cole esse código no arquivo HTML, dentro da tag `<head>`, **antes do link do CSS**.

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
```

4. Logo abaixo, adicione o link do arquivo CSS:

```html
<link rel="stylesheet" href="style.css">
```

### 7.3 Aplicando a fonte no CSS

```css
font-family: "Roboto", sans-serif;
```

Aplicado a uma classe:

```css
.primeiro-h1 {
    color: red;
    font-family: "Roboto", sans-serif;
}
```

Observações:

- O nome da fonte deve ser exatamente o mesmo informado pelo Google Fonts
- `sans-serif` é uma **fonte de fallback**, usada caso a Roboto não carregue

---

## 8. Espaçamento e borda

### 8.1 Margin (espaço externo)

A **margin** cria espaço **fora do elemento**, afastando-o de outros elementos.

Margin auto: centraliza o elemento **horizontalmente**. Geralmente é usado com `width`.

```css
margin: auto;
```

Margin com valor específico:

```css
margin: 50px;
```

Margens individuais:

```css
margin-top: 20px;      /* topo */
margin-right: 10px;    /* direita */
margin-bottom: 15px;   /* baixo */
margin-left: 5px;      /* esquerda */
```

Shorthand:

```css
margin: 20px;                 /* todos os lados */
margin: 10px 20px;            /* vertical | horizontal */
margin: 10px 20px 30px 40px;  /* top | right | bottom | left */
```

### 8.2 Padding (espaço interno)

O **padding** cria espaço **dentro do elemento**, entre o conteúdo e a borda.

⚠️ `padding: auto` **não existe** no CSS.

```css
padding: 50px;

padding-top: 20px;      /* topo */
padding-right: 10px;    /* direita */
padding-bottom: 15px;   /* baixo */
padding-left: 5px;      /* esquerda */

padding: 20px;                  /* todos os lados */
padding: 10px 20px;             /* vertical | horizontal */
padding: 10px 20px 30px 40px;   /* topo | direita | baixo | esquerda */
```

### 8.3 Border (borda)

A **border** cria uma linha ao redor do elemento. A ordem é: espessura, tipo e cor.

```css
border: 5px solid red;
```

`border-radius` arredonda as bordas:

```css
border-radius: 10px;  /* arredonda os cantos */
border-radius: 50%;   /* deixa redondo (ex: círculo) */
```

### 8.4 Resumo rápido

- **margin** → espaço externo
- **padding** → espaço interno
- **border** → borda do elemento
- **margin: auto** → centraliza horizontalmente
- **padding não usa auto**

---

## 9. `box-sizing`

O `box-sizing` define **se o `width` e o `height` consideram apenas o conteúdo ou também o padding e a borda**.

- **`content-box`** (padrão): `width` = somente o conteúdo. `padding` e `border` são somados depois, e isso pode quebrar o layout.
- **`border-box`** (mais usado): `width` = conteúdo + padding + border. O tamanho total do elemento não muda, e o layout fica mais previsível.

Por isso, na prática, quase todo projeto começa com:

```css
* {
    box-sizing: border-box;
}
```

Referência: [MDN: box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/box-sizing)

### 9.1 Comparando os três casos

**1) `content-box` sem padding e border**

```css
box-sizing: content-box;
width: 100%;
```

O `width` vale apenas para o conteúdo. Não há padding nem borda, então o elemento ocupa exatamente 100% do container.

**2) `content-box` com padding e border**

```css
box-sizing: content-box;
width: 100%;
border: 10px solid #5b6dcd;
padding: 5px;
```

O `width` continua sendo só do conteúdo. Padding e border são somados ao tamanho final, então o elemento fica maior que 100% e pode estourar o layout.

**3) `border-box` com padding e border**

```css
box-sizing: border-box;
width: 100%;
border: 10px solid #5b6dcd;
padding: 5px;
```

O `width` inclui conteúdo, padding e border. O tamanho total continua sendo 100%, e o layout fica organizado.

---

## 10. `:hover`

O `:hover` cria interações visuais sem JavaScript: muda cor, tamanho, adiciona sombra ou indica que algo é clicável.

```css
button:hover {
    background-color: blue;
    color: white;
}
```

Quando o mouse passa sobre o botão, o estilo muda.

É muito usado em botões, links (`a:hover`), cards e menus.

Resumo: `:hover` = estilo quando o mouse passa por cima.

---

## 11. `position`

A propriedade `position` define como um elemento será posicionado na página.

### 11.1 `static` (padrão)

- Segue o fluxo normal do HTML
- Fica exatamente onde aparece no código
- ❌ Não funciona com `top`, `bottom`, `left` e `right`

Resumo: posição normal do documento, sem controle de deslocamento.

### 11.2 `relative`

- Continua no fluxo normal do documento
- Pode ser movido com `top`, `bottom`, `left` e `right`
- O deslocamento é feito **a partir da posição original**

Resumo: move o elemento em relação à sua própria posição original.

Muito usado para servir de referência para elementos `absolute`.

### 11.3 `absolute`

- Sai do fluxo normal do documento
- É posicionado em relação ao **elemento pai mais próximo que tenha** `relative`, `absolute` ou `fixed`
- Se não houver, usa o `<html>` como referência
- Usa `top`, `bottom`, `left` e `right`

Resumo: posiciona o elemento em relação ao pai posicionado mais próximo.

Dica: para controlar um `absolute`, normalmente coloca-se `position: relative` no elemento pai.

### 11.4 `fixed`

- Sai do fluxo normal
- É posicionado em relação à **janela do navegador**
- Não se move quando a página rola

Resumo: fica fixo na tela, mesmo com scroll.

Muito usado para botão "voltar ao topo", menu fixo e chat flutuante.

### 11.5 `sticky`

- Começa como `relative`
- Quando atinge um ponto definido (ex: `top: 0`), passa a se comportar como `fixed`
- Depende da rolagem da página
- Precisa de pelo menos um valor (`top`, `bottom`, etc.) para funcionar

Resumo: fica normal até certo ponto, depois gruda na tela.

Muito usado para cabeçalhos de tabela e menus que "grudam" ao rolar.

### 11.6 Comparação rápida

| Tipo | Sai do fluxo? | Referência |
| --- | --- | --- |
| Static | ❌ Não | Fluxo normal |
| Relative | ❌ Não | Própria posição |
| Absolute | ✅ Sim | Pai posicionado |
| Fixed | ✅ Sim | Janela do navegador |
| Sticky | Parcialmente | Scroll + posição original |

---

## 12. Reset básico no `body`

Alguns elementos HTML já têm estilos padrão do navegador, como `margin`, `padding` e `outline` (em `h1`, `p`, `ul`, `body` etc.). Esses estilos variam de navegador para navegador e podem atrapalhar o alinhamento do layout.

```css
body {
    margin: 0;
    padding: 0;
    outline: 0;
}
```

- `margin: 0;` → remove o espaçamento externo padrão
- `padding: 0;` → remove o espaçamento interno padrão
- `outline: 0;` → remove a borda de foco padrão

Isso dá mais controle e previsibilidade ao layout.

⚠️ Atenção: remover o `outline` esconde o indicador de foco, que é usado por quem navega com teclado. Se fizer isso, é importante criar outro indicador de foco (por exemplo, com `:focus-visible`).

Resumo: reset CSS = remover estilos automáticos do navegador para começar o layout do zero.

---

## 13. Flexbox

O Flexbox organiza os itens dentro de um container, controlando alinhamento e distribuição de espaço.

### 13.1 Estrutura base

```css
body {
    font-family: 'Roboto', sans-serif;
    height: 180vh; /* 180% da altura da tela (viewport height) */
}
```

- `1vh` = 1% da altura da tela
- `100vh` = altura total da tela
- `180vh` = 1,8x a altura da tela (gera scroll)

### 13.2 Container com Flexbox

```css
.container {
    background-color: #121212;
    height: 500px;
    margin: 50px;

    display: flex;
    flex-direction: column-reverse;
}
```

**`display: flex`** ativa o Flexbox no container. Os elementos filhos passam a ser chamados de **flex items**. O padrão é `flex-direction: row` (itens lado a lado).

**`flex-direction`** define a direção dos itens:

| Valor | Comportamento |
| --- | --- |
| `row` | Itens lado a lado (padrão) |
| `row-reverse` | Lado a lado, invertendo a ordem |
| `column` | Um embaixo do outro |
| `column-reverse` | Um embaixo do outro, invertendo a ordem |

### 13.3 Estilo dos itens

HTML:

```html
<div class="container">
    <div class="area item-1"></div>
    <div class="area item-2"></div>
    <div class="area item-3"></div>
</div>

<div class="container2">
    <div class="area2 item-4"></div>
    <div class="area2 item-5"></div>
    <div class="area2 item-6"></div>
</div>
```

CSS:

```css
.area {
    width: 100px;
    height: 100px;
}

.item-1 { background-color: red; }
.item-2 { background-color: blue; }
.item-3 { background-color: darkgreen; }
```

Cada item tem tamanho fixo.

### 13.4 Distribuição de espaço com `flex`

```css
.container2 {
    background-color: #121212;
    height: 500px;
    margin: 50px;

    display: flex;
    flex-direction: row;
}

.item-4 { background-color: red;       flex: 1; }
.item-5 { background-color: blue;      flex: 2; }
.item-6 { background-color: darkgreen; flex: 1; }
```

`flex: 1` é a forma abreviada de:

```css
flex-grow: 1;
flex-shrink: 1;
flex-basis: 0%;
```

Na prática, o espaço disponível é dividido proporcionalmente. Com `1 | 2 | 1`, o item do meio ocupa o dobro de espaço, e a divisão fica 25% / 50% / 25%.

### 13.5 `flex-basis`, `flex-grow` e `flex-shrink`

```css
.area3 {
    width: 100px;
    height: 100px;

    flex-basis: 400px;
    flex-grow: 1;
}
```

- **`flex-basis`**: tamanho inicial do item no eixo principal, antes da distribuição do espaço. Com `flex-direction: row`, controla a **largura**. Com `column`, controla a **altura**. No exemplo, o item começa com 400px.
- **`flex-grow`**: quanto o item pode **crescer** se houver espaço disponível. Com `1`, `1` e `2`, o terceiro item cresce o dobro dos outros.
- **`flex-shrink`**: quanto o item pode **encolher** quando o espaço do container for menor que o necessário. O padrão é `1`. Se um item tiver `flex-shrink: 2`, ele encolhe duas vezes mais que os outros.

```css
.item-7 { background-color: red;       flex-shrink: 1; }
.item-8 { background-color: blue;      flex-shrink: 1; }
.item-9 { background-color: darkgreen; flex-shrink: 2; }
```

Se faltar espaço no container, o `.item-9` reduz mais que os outros.

### 13.6 `flex` (forma abreviada)

```css
flex: 1;   /* equivale a flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
```

⚠️ Se você declarar:

```css
flex-basis: 400px;
flex: 1;
```

o `flex: 1` **sobrescreve** o `flex-basis`, porque redefine os três valores. Por isso, use `flex: 1` ou controle `flex-grow`, `flex-shrink` e `flex-basis` separadamente.

Resumo: `flex-basis` = tamanho inicial, `flex-grow` = quanto cresce, `flex-shrink` = quanto encolhe, `flex` = forma resumida que redefine os três.

### 13.7 `order`

`order` define a **ordem visual** dos itens dentro de um container flex. Não altera o HTML, só a posição na tela.

- Valor padrão: `order: 0`
- Menor valor aparece primeiro; maior valor aparece depois

```html
<div class="container4">
    <div class="area4 item-10">10</div>
    <div class="area4 item-11">11</div>
    <div class="area4 item-12">12</div>
</div>
```

```css
.item-10 { order: 3; }
.item-11 { order: 2; }
.item-12 { order: 1; }
```

Resultado visual: item-12, depois item-11, depois item-10, mesmo que no HTML estejam em outra ordem.

Regras:

- ✔️ Só funciona em elementos dentro de `display: flex`
- ✔️ Pode receber valores negativos
- ✔️ Não altera a estrutura do DOM
- ❌ Não é recomendado para reorganizar o layout principal (é melhor organizar no HTML)

Use `order` para pequenos ajustes visuais, layouts responsivos e mudança de posição em versões mobile. Evite usá-lo para "corrigir" HTML mal estruturado.

### 13.8 `justify-content`

`justify-content` define **como os itens são distribuídos no eixo principal**.

- `row` → eixo principal é **horizontal**
- `column` → eixo principal é **vertical**

```css
.container5 {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}
```

| Valor | Comportamento |
| --- | --- |
| `flex-start` (padrão) | Alinha os itens no início do container |
| `flex-end` | Alinha os itens no final do container |
| `center` | Centraliza os itens no eixo principal |
| `space-between` | Espaço igual **entre** os itens. O primeiro encosta no início e o último no final |
| `space-around` | Espaço ao redor de cada item. O espaço das extremidades fica menor que o do meio |
| `space-evenly` | Distribui o espaço igualmente entre todos, inclusive nas extremidades |

### 13.9 `align-items`

`align-items` define como os itens são alinhados no **eixo cruzado**.

- `flex-direction: row` → eixo principal horizontal, eixo cruzado vertical
- `flex-direction: column` → eixo principal vertical, eixo cruzado horizontal

```css
.container6 {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}
```

Com `row`, `justify-content` alinha horizontalmente e `align-items` alinha verticalmente.

| Valor | Comportamento |
| --- | --- |
| `flex-start` | Alinha os itens no início do eixo cruzado |
| `center` | Centraliza os itens no eixo cruzado |
| `flex-end` | Alinha os itens no final do eixo cruzado |
| `stretch` (padrão) | Estica os itens para ocupar todo o eixo cruzado. Só funciona se o item não tiver altura (ou largura, conforme o eixo) fixa |

Centralização perfeita:

```css
align-items: center;
justify-content: center;
```

Os itens ficam centralizados horizontal e verticalmente. Muito usado para centralizar conteúdo na tela inteira.

| Propriedade | Atua em qual eixo? |
| --- | --- |
| `justify-content` | Eixo principal |
| `align-items` | Eixo cruzado |

#### Combinações com `flex-direction: row`

Com `row`, `justify-content` mexe na horizontal e `align-items` mexe na vertical.

| CSS | Resultado |
| --- | --- |
| `align-items: center; justify-content: flex-end;` | Colados à direita, centralizados na altura |
| `align-items: flex-end; justify-content: flex-end;` | Canto inferior direito |
| `align-items: flex-end; justify-content: center;` | Centro da largura, na parte de baixo |
| `align-items: flex-start; justify-content: center;` | Centro da largura, na parte de cima |

#### Combinações com `flex-direction: column`

Com `column`, os eixos invertem: `justify-content` controla a vertical e `align-items` controla a horizontal.

| CSS | Resultado |
| --- | --- |
| `align-items: center; justify-content: flex-end;` | Centro horizontal, embaixo |
| `align-items: flex-end; justify-content: flex-end;` | Canto inferior direito |
| `align-items: flex-end; justify-content: center;` | Meio vertical, à direita |
| `align-items: flex-start; justify-content: center;` | Meio vertical, à esquerda |

Regra de ouro:

- `flex-direction: row` → justify = horizontal, align = vertical
- `flex-direction: column` → justify = vertical, align = horizontal

Truque mental: pergunte sempre "qual é o meu eixo principal agora?". `justify-content` sempre trabalha no eixo principal, e `align-items` sempre trabalha no eixo cruzado.

### 13.10 `align-self`

`align-self` alinha **um item individualmente**, ignorando o `align-items` do container. Atua no **eixo cruzado**.

| Propriedade | Aplica em |
| --- | --- |
| `align-items` | Todos os itens |
| `align-self` | Apenas um item específico |

Exemplo com `flex-direction: row` (move o item para cima ou para baixo):

```css
.container7 {
    display: flex;
    flex-direction: row;
    align-items: center;
}

.item-21 { align-self: flex-end; }   /* parte inferior */
.item-22 { align-self: flex-start; } /* parte superior */
```

Exemplo com `flex-direction: column` (move o item para a esquerda ou para a direita):

```css
.container8 {
    display: flex;
    flex-direction: column;
}

.item-25 { align-self: flex-end; }   /* direita */
.item-26 { align-self: flex-start; } /* esquerda */
```

Valores: `flex-start`, `center`, `flex-end`, `stretch`.

Regras:

- ✔ Funciona apenas em elementos dentro de `display: flex`
- ✔ Sobrescreve o `align-items`
- ✔ Atua sempre no eixo cruzado

Resumo: com `row`, `align-self` move verticalmente. Com `column`, move horizontalmente.

---

## 14. `z-index`

`z-index` controla a **ordem de empilhamento** dos elementos no eixo Z (profundidade). Define quem fica na frente e quem fica atrás quando elementos se sobrepõem.

- Quanto **maior o número**, mais na frente o elemento fica
- ⚠️ Só funciona se o elemento tiver `position` diferente de `static` (`relative`, `absolute`, `fixed` ou `sticky`)

### Exemplo prático

HTML:

```html
<div class="caixa caixa1">Caixa 1</div>
<div class="caixa caixa2">Caixa 2</div>
```

CSS:

```css
body {
    margin: 0;
    height: 100vh;
    background-color: #111;
}

/* Estilo base */
.caixa {
    width: 200px;
    height: 200px;
    position: absolute; /* Necessário para o z-index funcionar */
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
}

/* Caixa vermelha */
.caixa1 {
    background-color: #e63946;
    top: 100px;
    left: 100px;
    z-index: 1;
}

/* Caixa azul */
.caixa2 {
    background-color: #1d3557;
    top: 150px;
    left: 150px;
    z-index: 9;
}
```

As duas caixas se sobrepõem. Como `z-index: 9` é maior que `z-index: 1`, a Caixa 2 fica na frente.

---

## 15. Unidades

### 15.1 `px` (pixels)

Unidade **fixa**. Sempre terá o mesmo tamanho, independentemente do pai ou da tela.

```css
div { width: 300px; }
```

- Boa para bordas, ícones e detalhes pequenos
- Não é tão responsiva

### 15.2 `%` (porcentagem)

Depende do **elemento pai**.

```css
div { width: 50%; }
```

Ocupa 50% da largura do elemento pai. É relativa e ajuda na responsividade. Muito usada em layouts flexíveis.

### 15.3 `vh` (viewport height)

Depende da **altura da tela**.

```css
section { height: 100vh; }
```

- `100vh` = 100% da altura da tela
- `50vh` = metade da tela

Muito usada em telas fullscreen e landing pages.

### 15.4 `vw` (viewport width)

Depende da **largura da tela**.

```css
div { width: 100vw; }
```

`100vw` = largura total da tela.

### 15.5 `rem`

Relativa ao tamanho da fonte do `<html>`.

```css
p { font-size: 2rem; }
```

Se o `<html>` tiver 16px, `2rem` = 32px. Escala melhor e é ótima para acessibilidade.

### 15.6 `em`

Relativa ao elemento pai.

```css
div { font-size: 20px; }
p   { font-size: 2em; } /* 40px */
```

Pode virar uma "bola de neve" se não for controlada, porque cada nível herda o valor do anterior.

### 15.7 Resumo

| Unidade | Depende de quê? | Fixa ou relativa? |
| --- | --- | --- |
| `px` | Nada | Fixa |
| `%` | Elemento pai | Relativa |
| `vh` | Altura da tela | Relativa |
| `vw` | Largura da tela | Relativa |
| `rem` | `<html>` | Relativa |
| `em` | Elemento pai | Relativa |

Regra prática:

- Layout responsivo → `%`, `vh`, `vw`
- Texto moderno → `rem`
- Ajustes pequenos → `px`

---

## 16. Resumo final

- `display: flex` ativa o Flexbox
- `flex-direction` define a direção dos itens
- `flex` controla como os itens ocupam o espaço disponível
- `justify-content` trabalha no eixo principal, e `align-items` no eixo cruzado
- `z-index` só funciona com `position` diferente de `static`
- `margin` é espaço externo, `padding` é espaço interno, e `border` é a borda
- `box-sizing: border-box` é o mais usado na prática
- CSS externo é a melhor prática
- Se você dominar display/flex/grid, margin/padding/border, position e font/color/background, já está muito bem em CSS
