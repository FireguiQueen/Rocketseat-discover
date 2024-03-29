# Fonts

Tipografia transmite uma mensagem. 
Tipografia é o jeito que escrevemos algo, por exemplo.:

- Negrito
> serve para dar destaque a letras ou a palavras. Para darmos destaque a algum trecho do texto..

- Tamanho 
> serve para mostrarmos o que é referente ao que. Então geralmente um título terá seu tamanho grande, enquanto isso o parágrafo deste título terá um tamanho menor

- Estilo 
> Serve para dar um visual mais chamativo ao nosso texto, mudando o estilo da fonte, podemos deixar mais leve dependendo do contexto do texto. 

</br>
</br>

## Propriedades mais utilizadas

### <code>font-family </code>
* __Valores:__ _Arial, Verdana, 'Courier  New'.._ </br>
Define o tipo de fonte que será utilizada, ou seja, como será o estilo de escrita.
Esta propriedade incluir "fallback", ou seja, caso não consiga utilizar da primeira fonte, ela irá colocar outra fonte que você vai passar como valor.
Sempre que a fonte possuir espaço entre as letras, ela irá ficar entre aspas (" "), por isso algumas fontes não usam aspas, pois elas não precisam (porque possuem apenas uma palavra).
```css
p{
    font-family: 'Time News Roman', Times, serif;
    /* Caso a fonte "Time News Roman" não consiga ser colocada, a fonte "times" irá aparecer, caso também não apareça, a fonte "serif" irá aparecer. */

    /* Serif: Uma fonte "serificada" é aquela fonte que possui "dobras" (como se fossem um suporte horizontal) quando se começa uma letra, uma fonte "sans-serif" é uma fonte sem essa dobra, sem este "suporte horizontal" */ 
}
```

</br>
</br>
</br>

### <code>font-weight</code>
* __Valores:__ _bolder, bold, light, lightner, 500, 400.._ </br>
* Define o "peso" da fonte..
* Podemos usar tanto valor númerico quanto palavras chaves. As palavras chaves podem ser representadas em formatos númericos.. Bold = 700, light = 300, normal = 400 (por padrão vem assim) 
Dependendo da família da fonte, a gente não consegue colocar determinado "peso" para ela. Por exemplo.:

```css
p{
    font-family: 'Time News Roman', Times, serif;
    font-weight: 300;

    /* OU -- */ 
    font-family: 'Time News Roman', Times, serif;
    font-weight: 100;

    /* Nesta fonte (times new roman), independente do weight que você colocar (entre 300 ou 100), ela vai mantar a mesma espessura. Isso nos mostra que, algumas fontes trabalham com 
    weights mais especificos. Por exemplo, pode existir uma fonte que não possua o valor "bold", ou que possua o valor "bold", mas não há diferença entre o "bold" e o "bolder" dela. O Google fonts funciona justamente desta maneira, quando você selecionar uma fonte, ele vai pedir em qual weight você quer, caso você queira a maior variedade possível, você terá que pegar todos os links de cada weight */
}
```

</br>
</br>
</br>

### <code>font-style</code> 
* __Valores:__ _normal, Italic, oblique_  </br>
* Define o estilo da fonte, por padrão é "normal", Italic é aquela letra mais deitada e "oblique" é extremamente parecida com a "italic". 

```css
p{
    font-style: italic; 
}
```

</br>
</br>
</br>

### <code>font-size</code>
* __Valores:__ _xx-small, x-small, medium, x-large, 1px, 1rem.._ </br>
* A unidade de medida mais utilizada é o pixel.

```css
p{
    font-size: 20px;
}
```

</br>
</br>
</br>


### Web fonts & local fonts

</br>

#### Web fonts 
São as fontes que veem da web, em grande parte das vezes você irá usar o google fonts.
* @import (NÃO RECOMENDO - IRÁ IR PARA O ARQUIVO .CSS E DEPOIS ELE SERÁ PUXADO PELO HTML)
* link (RECOMENDADO - IRÁ IR DIRETO NO ARQUIVO .HTML)

</br>
</br>

#### Local fonts 
São as fontes que já estão instaladas em nossa máquina
* @font-face 
```css
@font-face{
    font-family: de_um_nome_a_fonte_aqui
    src: url(onde/ela/se/encontra/na/sua/maquina)
}
```

</br>
</br>
</br>

## <code>font-variant </code>
* __Valores:__ _normal, small-caps, common-ligatures, no-common-ligatures_ </br>
Permite que você defina todas as variantes de fonte para uma fonte.
São pequenas variações que você pode fazer na sua fonte.
> NEM TODAS AS FONTES POSSUEM ESTA PROPRIEDADE 
```css
p{
    /* Deixa a fonte mais "amassada", "rebaixada" (haha) */
    font-variant: small-caps;
}
```
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant">Teste aqui </a>


</br>
</br>
</br>


## <code>font-stretch</code> 
* __Valores:__ _condensed, expanded, ultra-expanded, 50%, 100% e 150%._ </br>
Seleciona uma face normal, condensada ou expandida de uma fonte.
É como se fosse um "zoom" na fonte
> NEM TODAS AS FONTES POSSUEM ESTA PROPRIEDADE 
```css
p{
    font-stretch: condensed;
}
```
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch">Teste aqui </a>

</br>
</br>
</br>

## <code>letter-spacing</code>
* __Valores:__ _1px, 1rem, 1em._ </br>
Apliaca um espaço entre as letras
```css
p{
    letter-spacing: 4px;
}
```

</br>

## <code>word-spacing</code>
* __Valores:__ _1px, 1rem, 1em._ </br>
Aplica um espaço entre as palavras
```css
p{
    word-spacing: 2em;
}
```

</br>
</br>
</br>

## <code>line-height</code>
* __Valores:__ _1px, 1rem, 1em, 1.5, 2.6_ </br>
Apliaca um espaço entre linhas, como se aumentassemos a distância entre linhas de um caderno
```css
p{
    line-height: 2.2;
}
```
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-height">Teste aqui </a>

</br>

## <code>text-transform</code>
* __Valores:__ _capitalize, uppercase, lowercase, none_ </br>
Aplica determinada transformação ao nosso elemento de texto
```css
p{
    /* Deixa tudo em maiúsculo */
    text-transform: uppercase;

    /* Deixa tudo em minúsculo */
    text-transform: lowercase;

    /* Inicial de cada palavra será com letra maiúscula */
    text-transform: capitalize;

    /* Tira todas as transformações feitas no texto */
    text-transform: none; 
}
```
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform">Teste aqui </a>

</br>

## <code>text-decoration</code> 
* __Valores:__ _underline, overline, line-through_  </br>
* __Estilos:__ _wavy, dashed, double.._
* __Cor:__ _qualquer cor que desejar.._
Aplica uma decoração ao texto, mais de uma decoração pode ser aplicada e também podemos adicionar um estilo a esta decoração. Algumas tags aplicam text-decoration ao seu texto, como por exemplo a tag &<code>&lt;li&gt;</code>

```css
p{
    /* Cria um sublinhado */
    text-decoration: underline;

    /* Cria um sublinhado em formato de onda */
    text-decoration: underline wavy;


    /* Cria um sublinhado e um "subilnhado" que fica acima do texto */
    text-decoration: underline overline;

    /* Cria um subilinhado e um "subilinhado" que fica ao meio do texto com um estilo de onda */
    text-decoration: underline line-through wavy;
}
``` 

</br>
</br>
</br>

## <code>text-align</code>
* __Valores:__ _left, center, right, justify_  </br>
Alinha seu texto para determinada direção.
É um conceito bem simples, é igualzinho no Word (do windows), você tem as opções de alinhar o texto na tela. Mas lembre-se, o text-align não serve para POSICIONAR e sim para ALINHAR seus textos (alinhar o texto seria basicamente modificar sua estrutura). 
```css
p{
    /* Alinha pra esquerda - vem por padrão assim */
    text-align: left;

    /* Alinha pro centro */ 
    text-align: center;

    /* Alinha pra direita  */
    text-align: right;  

    /* Alinha como se o texto fosse um bloco, só é vísivel caso o texto seja relativamente grande */
    text-align: justify;
} 
```
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-align">Teste aqui </a>


</br>
</br>
</br>

## <code>text-shadow</code>
* __Valores:__ _`length X` `length Y` `length blur` color_ </br>
Podemos criar sombras para os nossos textos. O primeiro valor é parao eixo X (horizontal), o segundo valor para o eixo Y (vertical), o terceiro valor para o blur (desfoque) desta sombra, e o quarto é a cor desejada. Caso a cor não seja definada, ela será currentcolor por padrão, ou seja, a cor da sombra é a cor da propriedade <code>color: ;</code>
> Vale lembrar que, números positivos vão para a direita e para baixo, números negativos para a esquerda e para cima
```css
p{
    /* Uma sombra vermelha um pouco para o lado direito e para baixo com um desfoque de 2px */ 
    text-shadow: 3px 3px 2px red;
}

/* Podemos adicionar infinitas sombras a um texto usando vírgula (,) */
p{
    text-shadow: 3px 3px 2px red,
    2px 2px 7px green,
    3px 3px 2px yellow;
}
```

</br>
</br>
</br>

## Shorthand
Por mim podemos utilizar do short-hand para agrupar todas as propriedades, por exemplo..
```css
    /* style, variant, weight, stretch, size, line-height & family */   
    /* Size e line-height precisam ser separados por barra (/) */
    font: italic normal bold normal 3em/1.5 Times, Arial, sans-serif;
```
