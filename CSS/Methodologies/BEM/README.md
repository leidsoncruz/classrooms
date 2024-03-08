# Metodologia BEM

Blocks, Elements and Modifiers -- https://getbem.com/introduction/

> The reason I choose BEM over other methodologies comes down to this: it is less confusing than the other methods (i.e. SMACSS) but still provides us the good architecture we want (i.e. OOCSS) and with a recognizable terminology. - Mark McDonnell, Maintainable CSS with BEM


## Block

Uma entidade que tenha um sentido sozinha, sem precisar de nenhum outro elemento auxiliar. Ou seja, é uma entidade autônoma que representa um componente reusável.

Os blocos podem conter elementos mas não podem depender de outros blocos. Eles representam uma unidade independente de funcionalidade ou apresentação.

Exemplos:
 - header
 - container
 - menu
 - checkbox
 - input

Sintaxe: .card, .header, .footer, etc.

## Element

Parte de um bloco que faz sentido apenas dentro daquele bloco, sozinho não conseguimos identificar muito bem o seu sentido. Em outras palavras um elemento sempre faz parte de um bloco e está semanticamente vinculado ao seu bloco. Eles não existem fora do contexto do seu bloco.

Não é uma boa prática elementos dependerem de outros elementos, mas é possível se encontrar em algumas páginas. Mas não é recomendado.

Examplos:
- menu item
- list item
- checkbox caption
- header title

Sintaxe: Usamos o underline (__) para separar o elemento do bloco --  .card__header, .card__title, .card__footer, etc.

## Modifier

Uma bandeira em um bloco ou elemento que é usado para mudar a aparência ou o comportamento dos mesmos.

Examplos:
- disabled
- highlighted
- checked
- fixed
- size big
- color yellow

Sintaxe: Usamos dois traços para separar o modificador de um bloco ou elemento -- .card__header-disabled, .card--color-yellow, .card--fixed  