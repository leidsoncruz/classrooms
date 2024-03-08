# Metodologia BEM

Blocks, Elements and Modifiers -- https://getbem.com/introduction/

> The reason I choose BEM over other methodologies comes down to this: it is less confusing than the other methods (i.e. SMACSS) but still provides us the good architecture we want (i.e. OOCSS) and with a recognizable terminology. - Mark McDonnell, Maintainable CSS with BEM


## Block

Uma entidade que tenha um sentido sozinha, sem precisar de nenhum outro elemento auxiliar.

Exemplos:
 - header
 - container
 - menu
 - checkbox
 - input

## Element

Parte de um bloco que faz sentido apenas dentro daquele bloco, sozinho não conseguimos identificar muito bem o seu sentido.

Examplos:
- menu item
- list item
- checkbox caption
- header title

## Modifier

Uma bandeira em um bloco ou elemento que é usado para mudar a aparência ou o comportamento dos mesmos.

Examplos:
- disabled
- highlighted
- checked
- fixed
- size big
- color yellow