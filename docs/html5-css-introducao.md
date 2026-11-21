# HTML5 e CSS: aprendendo a criar sites do zero na prática

Esta documentação reúne anotações práticas do curso: atalhos do editor, quebra de linha e o uso de `id` e `class` no HTML e no CSS.

---

## 1. Comentários em código no VS Code

Para **comentar ou descomentar rapidamente** um trecho de código no Visual Studio Code, use o atalho:

- **Windows / Linux:** `Ctrl + /`
- **Mac:** `Cmd + /`

O VS Code identifica automaticamente a linguagem e aplica o tipo correto de comentário.

### Exemplo em HTML

```html
<!-- <audio controls>
    <source src="curso.mp3" type="audio/mpeg">
</audio> -->
```

### Indentação

- **Tab**: empurra o código para a direita (indenta)
- **Shift + Tab**: puxa o código de volta para a esquerda (desindenta)

---

## 2. Word Wrap no VS Code

O **Word Wrap** quebra linhas longas automaticamente, evitando a rolagem horizontal.

### O que ele faz

- Ajusta o texto à largura da tela
- Não altera o código, apenas a visualização
- Facilita a leitura de linhas grandes

### Resumo

**Word Wrap = quebra visual de linha**

### Atalho

- **Alt + Z**: ativa/desativa o Word Wrap

---

## 3. Atributos `id` e `class`

### 3.1 `id`

- Deve existir **apenas uma vez** na página
- É único
- Tem maior especificidade no CSS

```html
<header id="cabecalho"></header>
```

```css
#cabecalho {
  background: blue;
}
```

**Quando usar:**

- Âncoras (`#contato`)
- Identificar uma seção única
- Manipulação específica no JavaScript
- Estruturas principais (header, footer, etc.)

### 3.2 `class`

- Pode ser usada **várias vezes**
- Serve para reaproveitar estilo

```html
<button class="botao-primario">Salvar</button>
<button class="botao-primario">Enviar</button>
```

```css
.botao-primario {
  background: green;
  color: white;
}
```

**Quando usar:**

- Estilização
- Componentes reutilizáveis
- Layout
- Padrões visuais

Em projetos profissionais, a maior parte do CSS usa `class`.

---

## 4. Diferença de especificidade

No CSS, `id` é mais forte que `class`.

```css
#caixa {
  background: red;
}

.caixa {
  background: blue;
}
```

Se o elemento tiver os dois, o `id` vence. Por isso, evitar `id` em excesso ajuda a não criar conflitos.

---

## 5. Regra prática

- Use **`class` para quase tudo**
- Use **`id` apenas quando realmente for único**

---

## 6. Várias classes no mesmo elemento

Você pode colocar várias classes no mesmo elemento, separadas por espaço:

```html
<div class="card destaque sombra"></div>
```

Isso deixa o código mais organizado e escalável.
