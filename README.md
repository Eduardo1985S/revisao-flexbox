# Exemplo de Página Usando Flexbox

Este repositório contém um exemplo de página web que utiliza Flexbox para criar um layout moderno e responsivo.

## Estrutura do Projeto

A página é composta pelos seguintes elementos:

- **Header**: Contém o título da página.
- **Navegação (Nav)**: Inclui links de navegação como Início, Sobre, Serviços e Contato.
- **Conteúdo Principal**: Dividido em duas partes:
  - **Barra Lateral (Sidebar)**: Contém links adicionais.
  - **Conteúdo (Content)**: A área principal da página com textos explicativos.
- **Footer**: Contém informações de direitos autorais.

## Revisão Completa Sobre Flexbox

O Flexbox (ou CSS Flexible Box Layout) é um módulo de CSS que fornece um layout eficiente e poderoso, tornando mais simples o alinhamento, o espaçamento e a distribuição de itens dentro de um container. Ele é ideal para projetar layouts que precisam se adaptar a diferentes tamanhos de tela. Vamos revisar os conceitos fundamentais e as propriedades do Flexbox.

### Estrutura Básica do Flexbox

O Flexbox se baseia em dois componentes principais:

- **Container Flexível** (`flex container`): É o elemento pai que contém itens flexíveis. Ele é definido com a propriedade `display: flex` ou `display: inline-flex`.
- **Itens Flexíveis** (`flex items`): São os elementos filhos diretos do container flexível e são os elementos que serão organizados e alinhados pelo Flexbox.

```html
<div class="flex-container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.flex-container {
  display: flex;
}
```

### Propriedades do Container Flexível

Essas propriedades são aplicadas ao **flex container** e determinam o comportamento dos itens dentro dele.

### 1. **display**

- `display: flex`: Define um elemento como um container flexível em bloco.
- `display: inline-flex`: Define um elemento como um container flexível em linha.

### 2. **flex-direction**

Define a direção principal do fluxo dos itens dentro do container.

- `row` (padrão): Da esquerda para a direita (na horizontal).
- `row-reverse`: Da direita para a esquerda (na horizontal).
- `column`: De cima para baixo (na vertical).
- `column-reverse`: De baixo para cima (na vertical).

```css
.flex-container {
  flex-direction: row;
}
```

### 3. **justify-content**

Controla o alinhamento dos itens ao longo do **eixo principal**.

- `flex-start` (padrão): Alinha os itens ao início do eixo principal.
- `flex-end`: Alinha os itens ao final do eixo principal.
- `center`: Centraliza os itens no eixo principal.
- `space-between`: Espaço igual entre os itens, com o primeiro alinhado ao início e o último ao final.
- `space-around`: Espaços iguais ao redor dos itens.

```css
.flex-container {
  justify-content: center;
}
```

### 4. **align-items**

Controla o alinhamento dos itens ao longo do **eixo cruzado**.

- `stretch` (padrão): Estica os itens para preencher o container.
- `flex-start`: Alinha os itens ao início do eixo cruzado.
- `flex-end`: Alinha os itens ao final do eixo cruzado.
- `center`: Centraliza os itens no eixo cruzado.
- `baseline`: Alinha os itens pela linha de base do texto.

```css
.flex-container {
  align-items: flex-start;
}
```

### 5. **flex-wrap**

Determina se os itens devem ou não "quebrar" para uma nova linha, quando necessário.

- `nowrap` (padrão): Os itens ficam em uma única linha.
- `wrap`: Os itens quebram para uma nova linha, quando necessário.
- `wrap-reverse`: Similar a `wrap`, mas a quebra ocorre em sentido reverso.

```css
.flex-container {
  flex-wrap: wrap;
}
```

### 6. **align-content**

Aplica-se quando há mais de uma linha de itens (ou seja, com `flex-wrap` ativado). Controla o alinhamento das linhas no eixo cruzado.

- `flex-start`: Alinha as linhas ao início do container.
- `flex-end`: Alinha as linhas ao final do container.
- `center`: Centraliza as linhas no eixo cruzado.
- `space-between`: Espaço igual entre as linhas.
- `space-around`: Espaços iguais ao redor das linhas.
- `stretch`: Estica as linhas para preencher o espaço disponível.

```css
.flex-container {
  align-content: space-between;
}
```

### Propriedades dos Itens Flexíveis

Estas propriedades são aplicadas diretamente aos **itens flexíveis**.

### 1. **flex-grow**

Determina a capacidade de um item crescer, caso haja espaço disponível no container.

- Valor padrão: `0` (o item não cresce além do seu tamanho definido).
- Exemplo: `flex-grow: 1;` fará com que um item cresça proporcionalmente para ocupar espaço disponível.

```css
.item {
  flex-grow: 1;
}
```

### 2. **flex-shrink**

Define a capacidade de um item encolher, caso necessário.

- Valor padrão: `1` (os itens podem encolher).
- `0` significa que o item não encolherá.

```css
.item {
  flex-shrink: 1;
}
```

### 3. **flex-basis**

Define o tamanho inicial do item antes da aplicação de `flex-grow` e `flex-shrink`.

- Pode ser em pixels, porcentagem ou outra unidade de medida.
- Exemplo: `flex-basis: 200px;`.

```css
.item {
  flex-basis: 200px;
}
```

### 4. **flex**

É uma propriedade abreviada que combina `flex-grow`, `flex-shrink` e `flex-basis`.

- Exemplo: `flex: 1 1 200px;`.

```css
.item {
  flex: 1 0 auto;
}
```

### 5. **align-self**

Permite que você sobreponha o alinhamento de um único item, diferente do alinhamento definido pelo `align-items`.

- Valores: `auto`, `flex-start`, `flex-end`, `center`, `baseline`, `stretch`.

```css
.item {
  align-self: center;
}
```

### Exemplos Práticos

Vamos ver um exemplo prático usando todas essas propriedades.

```html
<div class="flex-container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

```css
.flex-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.item {
  flex: 1 1 100px;
  align-self: flex-end;
  padding: 10px;
  margin: 5px;
  background-color: lightblue;
}
```

Nesse exemplo:

- O container possui itens dispostos em linha (`row`).
- Os itens são espaçados entre si (`justify-content: space-between`).
- Eles são alinhados no centro do eixo cruzado (`align-items: center`).
- Os itens têm uma base de 100px, mas podem crescer e encolher conforme necessário (`flex: 1 1 100px`).

### Conclusão

O Flexbox facilita a criação de layouts responsivos e complexos com menos código do que técnicas anteriores, como floats ou inline-block. As propriedades fornecem flexibilidade para definir o comportamento dos itens em diferentes contextos, seja em linha ou coluna, com controle preciso sobre espaçamento, alinhamento e ordem.

Lembre-se de que o Flexbox é mais adequado para layouts unidimensionais — ou seja, quando você precisa alinhar e distribuir elementos em uma única direção (linha ou coluna). Para layouts mais complexos que envolvem duas dimensões, como linhas e colunas ao mesmo tempo, o **CSS Grid Layout** é a alternativa recomendada.

---

## Código HTML

```html
<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo de Flexbox</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        html, body {
            height: 100%;
            margin: 0;
        }

        .container {
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        .main-content {
            display: flex;
            flex-grow: 1;
        }
    </style>
</head>

<body>
    <div class="container">
        <header>
            <h1>Exemplo de Página Usando Flexbox</h1>
        </header>

        <nav class="nav">
            <a href="#">Início</a>
            <a href="#">Sobre</a>
            <a href="#">Serviços</a>
            <a href="#">Contato</a>
        </nav>

        <div class="main-content">
            <aside class="sidebar">
                <h2>Barra Lateral</h2>
                <ul>
                    <li><a href="#">Link 1</a></li>
                    <li><a href="#">Link 2</a></li>
                    <li><a href="#">Link 3</a></li>
                    <li><a href="#">Link 4</a></li>
                </ul>
            </aside>

            <div class="content">
                <h2>Conteúdo Principal</h2>
                <p>
                    Este é um exemplo de conteúdo principal que usa Flexbox para definir o layout da página.
                    A área principal ocupa o espaço restante ao lado da barra lateral.
                </p>
                <p>
                    Flexbox torna mais fácil o alinhamento e distribuição de itens em uma página.
                    Você pode facilmente alinhar e ajustar o espaço de itens dependendo do espaço disponível.
                </p>
            </div>
        </div>

        <footer>
            <p>Todos os direitos reservados &copy; 2024</p>
        </footer>
    </div>
</body>

</html>
```

## Estilos CSS

Para estilizar a página, você pode adicionar o seguinte código ao arquivo `styles.css`:

```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background-color: #f0f0f0;
    color: #333;
}

header {
    background-color: #3b82f6;
    color: white;
    padding: 20px;
    text-align: center;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.nav {
    display: flex;
    justify-content: space-around;
    padding: 15px;
    background-color: #1e40af;
}

.nav a {
    color: white;
    text-decoration: none;
    padding: 10px;
    transition: background-color 0.3s ease;
}

.nav a:hover {
    background-color: #3b82f6;
    border-radius: 5px;
}

.main-content {
    display: flex;
    flex-grow: 1;
    padding: 20px;
    gap: 20px;
}

.sidebar {
    flex: 1;
    padding: 20px;
    background-color: #e2e8f0;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.content {
    flex: 2;
    padding: 20px;
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

footer {
    background-color: #3b82f6;
    color: white;
    text-align: center;
    padding: 15px;
    box-shadow: 0 -4px 6px rgba(0, 0, 0, 0.1);
    margin-top: 20px;
}
```

## Como Executar

1. Crie um arquivo HTML (`index.html`) e copie o código HTML acima.
2. Crie um arquivo CSS (`styles.css`) e copie o código CSS fornecido.
3. Abra o arquivo `index.html` no seu navegador para visualizar o layout.

## Licença

Todos os direitos reservados &copy; 2024.
