# Metodologia SMACSS

Scalable and Modular Architecture for CSS -- https://smacss.com/

O core do "smacks" é categorizar as regras do CSS. O propósito de se categorizar é para codificar padrões — Coisas que irão se repetir dentro do nosso design. Com a repetição, conseguimos reutilizar os componentes, resultando em: menos código, maior facilidade para manter o código e maior consistência para nossos users. Existem cinco tipos de categoria:


## Base

Contém os estilos globais para serem aplicados em todo documento. Como tipografia (font-family, size, etc), button, ul, variáveis, etc.

```css
html, body, form { margin: 0; padding: 0; }
input[type=text] { border: 1px solid #999; }
a { color: #039; }
a:hover { color: #03C; }
```

## Layout

Divide a página em seções. Os layouts mantêm um ou mais módulos juntos. Nós damos aos layouts um ID pois eles não se repetem ao longo da nossa página. Porém existem layouts que se repetem ao longo da página e que para isso acontecer, se usa classes no lugar do id. Por exemplo, o uso de um layout grid. 

```css
#header, #article, #footer {
    width: 960px;
    margin: auto;
}

#article {
    border: solid #CCC;
    border-width: 1px 0 0;
}

/* Outro exemplo com prefixo -- Neste exemplo, quando aplicado mudamos o layout
  de um layout fluído para fixo */
#article {
    width: 80%;
    float: left;
}

#sidebar {
    width: 20%;
    float: right;
}

.l-fixed #article {
    width: 600px;
}

.l-fixed #sidebar {
    width: 200px;
}
```

Geralmente se usa o prefixo `l- || layout-` para identificar mais facilmente que o elemento é um layout e não um módulo por exemplo. Pode se usar também o prefixo `grid-` que é claro suficiente para indicar que aquilo é um layout e não um outro estilo.

## Module

São as partes reutilizáveis e modulares do nosso design. Os módulos devem estar dentro dos componentes de `Layout` e algumas vezes dentro de outros `Modules`. Como são componentes reutilizáveis, eles devem ser desenhados para existir como um componente autônomo. São barras de navegação, cards, buttons, as listas de produtos e assim por diante.

```html
<div class="fld">
  <span>Folder Name</span>
</div>
```

```css
/* The Folder Module */
.fld > span {
    padding-left: 20px;
    background: url(icon.png);
}
```

Quando precisamos ter o mesmo módulo em diferente sections o que precisamos usar é a abordagem de subclassing. Por exemplo:

```html
<div class="pod pod-constrained">...</div>
<div class="pod pod-callout">...</div> 
```
```css
.pod { 
    width: 100%; 
} 
.pod input[type=text] { 
    width: 50%; 
}
.pod-constrained input[type=text] { 
    width: 100%; 
}

.pod-callout { 
    width: 200px; 
}
.pod-callout input[type=text] { 
    width: 180px; 
}
```

## State

Descreve qual visual que os módulos ou layouts vão ter em um determinado estado. Se o elemento está escondido, ativo, inativo, expandido, etc.

São aplicados no layout ou no elemento base de um módulo.

```html
<div id="header" class="is-collapsed">
    <form>
        <div class="msg is-error">
            There is an error!
        </div>
        <label for="searchbox" class="is-hidden">Search</label>
        <input type="search" id="searchbox">
    </form>
</div>
```

```css
/* Estado específico para um módulo */

.tab {
    background-color: purple;
    color: white;
}

.is-tab-active {
    background-color: white;
    color: black;
}
```

## Theme

Define as regras de estilos do tema para os elementos. Por exemplo: Como o button padrão, primário, secondário, etc aparenta ser. Com as regras de tema é fácil fazer customizações para as marcas.