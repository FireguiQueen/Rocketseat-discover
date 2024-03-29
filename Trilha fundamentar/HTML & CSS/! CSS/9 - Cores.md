# Cores
Usamos do CSS para alterar cores do nosso documento.
<a href="https://codepen.io/FireguiQueen/pen/KKBXwgW">Leia mais aqui </a>

## Tipos 
* background-color (cor do fundo das caixas)
* border-color (corda da borda)
* color (cor dos textos)

## Valores
#### Podemos definir o valor por: 
- palavra chave: _transparent.._
- nome da cor: _green, red, blue.._ 
- hexadecimal: _#000000  (red green blue)_
- funções: _rgb, rgba , hsl, hsla_


```css
    /* PALAVRA CHAVE */
    h1{
    color: transparent; /* A cor do h1 irá ficar transparente */
    }

    /* NOME DA COR */
    h1{
    color: red;      /* A cor do h1 irá ficar vermelha    */
    color: blue;     /* A cor do h1 irá ficar azul        */
    color: limegreen /* A cor do h1 irá ficar verde limão */
    }
```

## HEX (HEXADECIMAL) 
```css
    h1{
        color: #090;  /* Verde, pois é 0 para a cor vermelha, 9 para verde e 0 para o azul.  */ 
        
        
        color: #009900;     /* Verde novamente, mas com esta quantidade de números temos um controle maior em relação a esta cor */   
        color: #090f;       /* Verde transparente. Quando vemos uma letra no HEX, estamos trabalhando com a com sua opacidade    */


        /* 
        Para mudarmos a cor, temos "0" até "9"  
        Para a transparência (opacidade) desta cor, temos de "a" até "f".
        Sendo "a" com muita opacidade, e conforme subimos a letra, com menos opacidade, ou seja, menos transparente. 
        */ 
        color: #990000aa; 
        color: #990000dd; 
        color: #990000ff; 

        /* Caso você utilize da maneira mais curta (#0 0 0), você deve colocar somente uma letra alfabética ou três. */
        color: #600f;
        color: #600fff;

        /* Caso você utilize da maneira mais extensa (#00 00 00), será necessário colocar a letra alfabética duas vezes. */
        color: #109900ff;  
    }
```


## RGB 
```css
    h1{
        color: rgb(200, 00, 00); 
        /*  RGB: Red - Green - Blue                                         */    
        /*  O RGB vai de 0 até 225, ou seja, do mais escuro ao mais claro   */ 
    }            
```

## RGBA
```css
    h1{
        color: rgb(200, 00, 00, 0.7);
        /*  RGBA: Red - Green - Blue - Alpha                                                */
        /*  O alpha significa opacidade                                                     */
        /*  O RGBA é igual o RGB normal, porém você pode trabalhar com a opacidade da cor   */ 
        /*  "0.7" seria o nível da transparência (opacidade) desta cor                      */    
    }            
```


## HSL  
```css
    h1{
        color: hsl(45, 100%, 50%);
        /* HSL: hue - saturaion - lumiance/lightness */
        /*  As cores são expressas em graus de 0° até 360º, representando uma volta completa na borda do círculo cromático */  
        
        /* 
        O primeiro valor é o HUE, o HUE é a matiz (o termo matiz significa que eu consigo especificar a cor, como verde, 
        amarelo, azul e etc).
        --> hsl(primeiro valor, 0%, 0%);
        */


        /* 
        O segundo valor é a saturação. É basicamente a quantia de leite você pôe no seu achocolatado. Os valores são mostrados 
        em porcentagem, uma cor 100% saturada é viva, enquanto uma cor menos insaturada é uma cor mais morta. 
        --> hsl(0, segundo valor, 0%);
        */


        /* 
        O terceiro valor é a luminiosidade que esta cor vai receber. Quanto mais luz, mais clara esta cor será. 
        A cor com 100% de luz será branca, independente da matiz e da saturação. 0% de luz a cor será preta, pois não há luz para ela.
        --> hsl(0, 0%, terceiro valor);
        */
    }
```


## Globa values
```css
    h1{
        color: inherit; /* inherit significa herdar. Neste caso estamos herdando a cor do pai do h1.     */
        color: initial; /* Initial significa inicial. Ou seja, a cor inicial do documento (preto)         */
        color: unset;   /* Unset significa não definido/setado. Mas a cor acabaria sendo herdada da tag pai */
    }
```


<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color">Saiba mais </a>
