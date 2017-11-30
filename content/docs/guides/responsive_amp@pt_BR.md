---
$title: Estilo e layout
---
[TOC]

O estilo e o layout nas páginas AMP em HTML são muito semelhantes aos de páginas HTML normais. Nos dois casos, você usará CSS.

No entanto, as AMP limitam o uso de CSS por motivos de desempenho e usabilidade ao mesmo tempo em que ampliam os recursos do design responsivo com recursos como [marcadores e substitutos](/pt_br/docs/guides/responsive/placeholders.html), [direção artística avançada por meio de srcset](/pt_br/docs/guides/responsive/art_direction.html) e o [atributo de layout](/pt_br/docs/guides/responsive/control_layout.html) para controlar melhor a forma que os elementos são exibidos.

{% call callout('Dica', type='success') %}
É muito fácil tornar os elementos responsivos nas AMP. Simplesmente coloque `layout="responsive"` neles. Para saber mais sobre o design responsivo nas AMP, acesse [Criar páginas AMP responsivas](/pt_br/docs/guides/responsive/responsive_design).
{% endcall %}

{{ youtube('y6kA3u3GIws', 480, 270, caption='Veja o que a equipe da UpperQuad tem a dizer sobre a reforma do site AMPproject e os desafios de usar AMP pela primeira vez.') }}

## Adicionar estilos a uma página

Adicione todos os CSS dentro de uma tag `<style amp-custom>` no cabeçalho do documento. Por exemplo:

[sourcecode:html]
<!doctype html>
<head>
  ...
  <style amp-custom>
    /* any custom styles go here. */
    body {
      background-color: white;
    }

    amp-img {
      border: 5px solid black;
    }

    amp-img.grey-placeholder {
      background-color: grey;
    }
  </style>
  ...
</head>
[/sourcecode]

{% call callout('Importante', type='caution') %}
Sua página pode ter somente uma tag `<style amp-custom>`, pois não é permitido ter mais de uma nas AMP.
{% endcall %}

Defina os estilos de componentes com seletores de classe ou elemento usando propriedades CSS comuns. Por exemplo:

[sourcecode:html]
<body>
  <p>Hello, Kitty.</p>
  <amp-img
    class="grey-placeholder"
    src="https://placekitten.com/g/500/300"
    srcset="/img/cat.jpg 640w,
           /img/kitten.jpg 320w"
    width="500"
    height="300"
    layout="responsive">
  </amp-img>
</body>
[/sourcecode]

{% call callout('Importante', type='caution') %}
Verifique se os seus estilos são compatíveis com as AMP. Alguns estilos não são por motivos de desempenho (veja também [CSS compatível](/pt_br/docs/guides/responsive/style_pages.html)).
{% endcall %}

## Elementos de layout responsivos

Especifique o tamanho e a posição de todos os elementos AMP visíveis fornecendo os atributos `width` e `height`. Esses atributos indicam a proporção do elemento, que pode ser dimensionado com o contêiner.

Defina o layout como responsivo. Isso dimensionará o elemento para a largura do seu elemento de contêiner e redimensionará a altura automaticamente para a proporção indicada nos atributos de largura e altura.

{% call callout('Leia mais', type='read') %}
Saiba mais sobre [os layouts compatíveis com as AMP](/pt_br/docs/guides/responsive/control_layout.html)
{% endcall %}

## Use marcadores e substitutos

A compatibilidade interna com marcadores e substitutos permite que seus usuários nunca precisem olhar novamente para uma tela em branco.

{% call callout('Leia mais', type='read') %}
Saiba mais sobre [Marcadores e substitutos](/pt_br/docs/guides/responsive/placeholders.html)
{% endcall %}

## Seja o diretor de arte das suas imagens

As AMP são compatíveis com os atributos `srcset` e `sizes` para que você tenha controle preciso sobre as imagens que serão carregadas em cada cenário.

{% call callout('Leia mais', type='read') %}
Saiba mais sobre [a direção artística com srcset e tamanhos](/pt_br/docs/guides/responsive/art_direction.html)
{% endcall %}

## Validar seus estilos e layout

Use o validador de AMP para testar o CSS e os valores de layout da sua página.

O validador confirma se o CSS da sua página não ultrapassa o limite de 50 mil bytes, verifica os estilos desativados e garante que o layout da página seja compatível e formatado corretamente. Veja também esta lista completa de [erros de estilo e layout](/pt_br/docs/reference/validation_errors.html#style-and-layout-errors).

Exemplo de erro no console de uma página com CSS que ultrapassa o limite de 50 mil bytes:

<amp-img src="/static/img/docs/too_much_css.png" width="1404" height="334" layout="responsive"></amp-img>

{% call callout('Leia mais', type='read') %}
Saiba mais sobre como [validar e corrigir suas páginas AMP](/pt_br/docs/guides/validate.html)
{% endcall %}
