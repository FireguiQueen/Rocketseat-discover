# <code>Form</code>
Representa uma seção de um documento que contém controles interativos que permitem ao usuário submeter informação a um determinado servidor web.

- Captura dados (informações) de entrada (input)
> Por exemplo, pegar o nome do cliente e armazenar numa variável JS

</br>

- Interação com a página
> Por exemplo, clicar no botão '1' (interação) e em outro número para fazer um cálculo na calculadora que está no seu site.

</br>

- Controle 
> Por exemplo, criar mais controles para uma tag vídeo, você poder aumentar, diminiuir o volume e etc..

</br>

# <code>Inputs</code>
São usados para criar controles interativos para formulários baseados na web para receber dados do usuário. A semântica de um <code>&lt;input&gt;</code> varia consideravelmente dependendo do valor de seu atributo type. Um atributo muito utilizado junto ao `input` é o atributo `autocomplete=".."`, ele faz com que seja permitido o browser do usuário sugerir texto no input. É igual quando vamos colocar o nosso email para se registrar em algum site, mas ao clicar na caixa do input, o nosso browser já nos sugere colocar o email que sempre colocamos. O `autocomplete` possui diversos valores, e cada valor é para determinada coisa.
```html
<!-- Para autocompletar o campo com o email do usuário -->
<input autocomplete="email" type="email"/>

<!-- Para autocompletar o campo com o endereço do usuário -->


```
## Valores do `type`
- file
> Para o usuário poder selecionar um arquivo de sua máquina

</br>

- text
> Para o usuário poder digitar um texto no input

</br>

- number
> Apenas números serão aceitas no input

</br>

- date
> Input de data, dia, mês e ano

</br>

- time
> Input para horário, horas e minutos.. 

</br>

- password
> Input para se colocar senha (seja para login ou register). Sua senha irá ficar em formato de "***"

> Muito utilizado com os atributos.: `minlent`, `maxlenth`, `size`, `pattern`. Veja para o que cada atributo serve <a href="#Explicando-atributos">aqui</a>



</br>

- email
> Input para emails. É parecido com o input do tipo "text", porém este input só irá aceitar a resposta do usuário caso ela contenha "@"


</br>

______________________________________________________________________________

## FORM: Atrbituos básicos

### Method
Quando criamos a tag <code>&lt;form&gt;</code> temos dois valores principais para o atributo <code>method</code>, sendo.: 
* get
> Método mais rápido para o backend receber as informações e é o valor padrão caso você não defina este atributo. Em geral, quando você faz uma pesquisa, você pode perceber que o que você digitou fica na URL do seu browser, e a mesma coisa acontece quando você preenche um formulário. Após colocar informações no formulário, eles irão ficar na sua URL. O valor "GET" é apenas recomendado caso o formulário possua perguntas não confidênciais, tais como.: nome da pessoa, sobrenome, idade e etc.. 

</br>

* post
> É o metódo mais seguro, porém mais lento ao se comunicar com o resto da aplicação. Após colocar informações no formulário, eles NÃO irão ficar na sua URL. O valor "POST" é recomendado caso o formulário tenha perguntas confidênciais, como: cpf, cartão de crédito, senha, usuário e etc..

</br>

______________________________________________________________________________

## FORM: tags filhas

#### <code>fieldset</code>
É usado para agrupar vários controles de input, bem como rótulos (&lt;label&gt;) dentro de um formulário da Web. Em outras palavras, iremos utilizar o <code>fieldset</code> para agrupar diversas questões de formulário, e definir que elas pertencem ao mesmo grupo (o atributo `name=""` não é obrigatório, mas é extremamente recomendado para definir um nome para aquele grupo), ou seja, vamos utilizar do fieldset para dizermos que todas os inputs tem o mesmo propósito.. E este propósito pode varir, pode ser inputs de texto, número, email e tudo isso para fazer seu login. 
No exemplo abaixo, os 3 <code>inputs</code> foram colocado na tag <code>fieldset</code> pois pertencem ao mesmo grupo (o propósito do grupo é ser as informações de contato). O Fieldset é muito utilizado com a tag <code>legend</code>, pois é ela quem dirá o nome agrupamento. 
```html
<!-- EXEMPLO 01: -->
<form>
    <fieldset name="inf-de-contato">       <!-- Define um grupo-->
        <legend>Contato </legend>         <!-- Define o nome do agrupamento -->

        Nome: <input type="text" />       <!-- Formulário pertencente ao grupo -->
        Sobrenome: <input type="text" />  <!-- Formulário pertencente ao grupo -->
        CPF: <input type="numer" />       <!-- Formulário pertencente ao grupo -->
    </fieldset> 



    <!-- Caso você queira que determinado grupo de formulário fique desabilitado 
    ou que um input específico fique desabilitado, 
    você pode adicionar o atributo "disabled". O "disabled" 
    só pode ser adicionado numa tag "INPUT" 
    (desabilitando um input especifico) na tag "FIELDSET" (desabilitando todo o grupo, ou seja, todos os inputs que estão neste grupo) -->

    <fieldset name="inf-de-endereço">   <!-- Define um grupo-->
        <legend>Contato </legend>       <!-- Define o nome do agrupamento -->

        Nome: <input type="text"/>      <!-- Formulário pertencente ao grupo -->
        Sobrenome: <input type="text"/> <!-- Formulário pertencente ao grupo -->
        Email: <input diabled type="text"/>     <!-- Foi desativado, porém ainda é visível na página -->
    </fieldset> 
</form>


<!-- EXEMPLO 02: -->
<form>
    <fieldset> <!-- Define um grupo-->
        <legend>Falsificador de CPF </legend> <!-- Define o nome do grupo -->

        Nome<input type="text">           <!-- Formulário pertencente ao grupo -->
        Sobrenome<input type="text">      <!-- Formulário pertencente ao grupo -->
        Estado <input type="text">        <!-- Formulário pertencente ao grupo -->
    </fieldset>
</form>
```
> RECOMENDADO O USO DA TAG <code>h2</code> ou <code>h1</code> PARA DEFINIR UM NOME DO FORMULÁRIO CASO A TAG <code>legend</code> não atenda suas necessidades.

</br>

O fieldset também pode ficar fora do formulário, porém o atributo `form=""` será necessário na tag <code>&lt;fieldset&gt;</code>. E o atributo `id=" "` será necessário na tag <code>&lt;form&gt;</code>.
```html
<form id="login">

</form>

<fieldset form="login">
    <legend>Login </code>
    User:     <input type="text"/> 
    Password: <input type="password"/> 
    Email:    <input type="email"/>
</fieldset> 
```

</br>
</br>
</br>

__________________________________________________________________________


#### <code>label</code>
Representa uma legenda para um item em uma interface do usuário. Em outras palavras, você associa um nome a um input.
```html
<!-- JEITO ERRADO -->
<form>
    Name:     <input type="text"/> 
    Password: <input type="password"/> 
</form>



<!-- JEITO RECOMENDADO -->
<form>
    <!-- O label faz com que a string "name" seja referente ao input de texto, e quando clicamos nesta mesma string, o HTML entende que queremos digitar naquele input, então já podemos começar a digitar -->
    <label> Name:     <input type="text"/>      </label>
    <label> Password: <input type="password"/>  </label>
</form>

<!-- JEITO RECOMENDADO 02 -->
<form>
    <!-- Podemos usar o "label" como atributo também, é menos recomendado, porém é melhor deixar com atributo do que deixar sem a tag label. Este atributo não será vísivel na página, será apenas lido pelo user agent do usuário. -->
    <input type="text" aria-label="Digite seu nome" />        
    <input type="password" aria-label="Digite sua senha"/> 
</form>

<!-- Não é necessário deixar o input dentro da tag LABEL, mas o atributo  FOR=" "  será necessário --> <!-- Mas o atributo for só funciona com ELEMENTOS específicos.: button, input, meter, output, progress, select textarea. -->
<form>
    <label for="nome-da-pessoa">Name </label>

    <input id="nome-da-pessoa" placeholder="digite seu nome" type="text">
    <!-- O atributo "placeholder" serve para dizer ao HTML que uma string deve ficar no input, e assim o usuário interaje com este input, a string do placeholder irá sumir. O placeholder NÃO substitui a tag "label"! -->
</form>
```

</br>
</br>
</br>

__________________________________________________________________________

## <code>BUTTON</code>
* Representa um botão
* Geralmente utilizado para enviar formulários 

### Buttom: atrbituos básicos
* __TYPE:__ _submit, reset, button_
 > O "reset" faz com que os inputs voltem aos seus valores iniciais, então caso queira que seu formulário resete ao clicar no botão, é importante colocar o atributo VALUE="" em todos os inputs.
 
 > O "submit" envia os dados do formulário para o servidor. Esse é o padrão se o atributo não for especificado para botões associados a um , ou se o atributo for um valor vazio ou inválido.
 
 > O "button" não tem comportamento padrão e não faz nada quando pressionado por padrão. Ele pode fazer com que os scripts do lado do cliente ouçam os eventos do elemento, que são acionados quando os eventos ocorrem.

</br>

* __FORM__ 

* __AUTOFOCUS__ 

* __DISABLED__ 

* __NAME__ 

* __VALUE__ 

</br>
</br>
</br>

_____________________________________________________________________________

# <code>datalist</code>
Contém um conjunto de elementos <code>&lt;option&gt;</code> que representam as opções permitidas ou recomendadas disponíveis para escolher nos inputs. Uma `datalist` é obrigada a estar linkada em algum input, pois como já sabemos, a `datalist` é utilizada para sugerir opções, e para sugerimos opções, precisamos linkar ela a algum input.

* O usuário pode selecionar um dos valores ou colocar um valor diferente da sugestão
* Utilize o atributo `value=".."` dentro da `option` para sugerir um valor principal, coloque o valor "secundário" entre as tags option.
* Utilizamos o atributo `list=".."` para linkar uma `datalist` a um input.

```html
<!-- Sugerindo uma fruta -->
<input list="fruit" type="text" name="my-favorite-fruit">
<datalist id="fruit">
    <option value="Apple">A red fruit</option>
    <option value="Banana">A yellow fruit</option>
    <option value="Mango">A yellow-red-orange fruit</option>
    <option value="Watermelon">A green-red fruit</option>
</datalist>


<!-- Sugerindo um horário -->
<input list="WhatTime" type="time" /> 
<datalist id="WhatTime">
    <option value="01:30"> </option>
</datalist>
```
> Vale lembrar que, o atributo `value=""` só pode receber o que condiz com o "type" do input. Ou seja, se colocarmos que o input é do tipo "time", só podemos colocar números e caracteres de horas (:) no `value=""`. Como pode ver, o exemplo acima foi utilizado um input do tipo "time", então, somos obrigados a colocar o `value=""` com um horário e com ":" para especificar qual valor são as horas, e qual valor são os minutos.

> No exemplo abaixo, estarei utilizando um input do `type="color"`, perceba que na datalist não pode haver strings, somente hexadecimais.
```html
<input type="color" list="ChooseColor">
<datalist id="ChooseColor">
    <!-- Pelo fato do nosso input ser do tipo "color", o value só pode possuir cores HEXADECIMAIS, nada além disto.-->
    <option value="#994553"> </option> 
    <option value="#191499"> </option>
</datalist>
```

> Tipos de input não suportados pelo datalist.: </br> hidden, password, checkbox, radio, file ou qualquer tipo de button.


</br>
</br>

_______________________________________________________________________________

# <code>textarea</code> 
* __Atributos principais:__ _name, rows, columns, wrap, minlentgh, maxlentgh_
O elemento HTML representa um controle de edição para uma caixa de texto, útil quando você quer permitir ao usuário informar um texto extenso em formato livre, como um comentário ou formulário de retorno.
```html
<textarea wrap="soft" rows="10" columns="8"> </textarea>
```

</br>
</br>

_______________________________________________________________________________

# <code>select</code>
Representa um controle que fornece um menu de opções. Diferente da tag `datalist`, as opções da tag `select` são obrigatórias, ou seja, o usuário será obrigado a escolher uma ou mais das opções, enquanto o `datalist` é apenas para dar sugestões de repostas em um input. Utilizamos do atributo `value` para facilitar a leitura quando estes dados chegarem ao nosso backend.   
```html 
<label for="SonyConsoles">Console </label>
<select id="SonyConsoles" name="console-favorito">
    <option>Selecione um modelo</option>
    <option value="ps1">Playstation 1 </option>
    <option value="ps3">Playstation 3 </option>
    <option value="ps4">Playstation 4 </option> 
    <option value="switch">Nintendo Switch </option> 
    <option value="3ds">Nintendo 3Ds </option> 
    <option value="Xbox360">Xbox 360 </option> 
</select>

<!-- Usamos do atributo "multiple" para informar que podemos escolher mais de uma resposta -->
<!-- Podemos utilizar so "size" para definir quantas opções a tag select vai mostrar inicialmente -->
<label for="jogos">Jogo(s) favorito(s) </label>
<select name="favorite-games" id="jogos" multiple size="3">
    <option>Selecione um ou mais jogos</option>
    <option>Far Cry 3 </option>
    <option>The last of us I </option>
    <option>Ori and the blind forest </option> 
    <option>Uncharted 4 </option> 
    <option>Shadow of the colossus </option> 
</select>
```


## <code>OPTGROUP</code>
Cria um agrupamento de opções dentro de um elemento `select`.
Usamos também o atributo `label=".."` para dar nome ao grupo que fizemos.
```html
<label for="carro-modelos">Escolha um carro </label>

<select id="carro-modelos">
    <optgroup label="TESLA">
        <option>Model X</option>
        <option>Model 3</option>
        <option>Model Y</option>
        <option>Cybertruck</option>
    </optgroup>

    <optgroup label="FIAT">
        <option>Pulse </option>
        <option>Fastback </option>
        <option>Argo </option>
        <option>Cronos </option>
    </optgroup>
</select>
```

_______________________________________________________________________________

## Explicando atributos

* __FORM__ 
 > Indica o formulário que é o proprietário do elemento. Em outras palavras, caso um botão/input esteja fora de um formulário, você pode fazer com que o botão/input seja referente a aquele determinado formulário.
 ```html
<form id="contato">
    <fieldset>
        NOME: <input type="text" name="nome-da-pessoa"/>
        EMAIL: <input type="text" name="nome-da-pessoa"/>
    </fieldset>
</form>
 
<button form="contato" type="submit">Enviar informações de contato</button>
```

</br>

* __AUTOFOCUS__ 
> O elemento deve ser focado automaticamente após a página ser carregada. O atributo só podeser utilizada uma vez por página.

</br>

* __DISABLED__ 
 > Desabiltia um elemento, porém o mesmo continua vísivel na página, mas com uma aparência mais transparente.

 </br>

* __VALUE__ 
> Define o valor padrão na qual será mostrado no elemento no carregar da página. Utilizamos muito do `value=""` junto a um botão que reseta os campos do formulário, pois o `reset` serve para os campos voltarem o VALOR padrão, e o valor padrão só será "nada" quando definirmos um `value` vazio.

* __NAME__ 
 > É um atributo muito importante para os campos do tipo input/button. Serve para identificar o valor daquela variável no nosso backend. Também é possível dar um name para um formulário, mesmo que o mesmo não seja processado pelo servidor. </br> 
 > É possível fazer isso:
```html
<form name="matricula">

</form>
```
Assim, podemos acessar esse formulário facilmente pelo Javascript:
```js
document.matricula.submit();
```

</br>

* __MINLENGTH__ & __MAXLENGTH__
> Atributos utilizados para o input do tipo "password", pois através desses atributos podemos fazer com que o usuário coloque uma senha com no mínimo 4 caracteres e no máximo 50 caracteres por exemplo. Em geral, é recomendado pedir no minimo 8 caracteres e JAMAIS limitar o número de caracteres de uma senha (por mais que algumas empresas grandes façam isto). É importante ressaltar que, caso o usuário coloque uma senha com menos ou mais caracteres do que foi permitido, após dar "submit", irá aparecer uma mensagem em inglês informando que o mínimo de caracteres não foi atingido ou que o máximo de caracteres foi atingido.
```html
<!-- A senha pede no mínimo 8 caracteres -->
<input type="password" minlength="8">

<!-- A senha pede no mínimo 12 caracteres e só aceita até 30 caracteres -->
<input type="password" minlength="12" maxlength="30" title="Por favor coloque no mínimo 12 e no máximo 30 caracteres em sua senha!" />
```

</br>

* __SIZE__
> Define o tamanho do input
```html
<input type="password" size="12">
```

</br>

* __REQUIRED__
> Define que é obrigatório preencher determinado input. Caso o input não seja preenchido, após dar submit ele irá retornar uma mensagem informando ao usuário que o input deve ser preenchido. 
```html
<input type="text" required>
```

</br>

* __PATTERN__ 
> Define quais e quantos caracteres serão aceitos no input. Podemos dizer que apenas números serão aceitos, ou apenas letras, ou apenas letras maiúsculas e assim por diante. Este atributo também é muito colocado junto ao atributo `title`, assim, caso o que foi colocado pelo usuário não seja permitido, a mensagem que foi colocada no `title` irá aparecer. O pattern é geralmente muito utilizado num input onde possui um `text-transform="lowercase"`, assim o usuário não consegue digitar em letras maiúsculas (geralmente em inputs de email).
```html
<!-- Estamos dizendo que o input irá aceitar da letra "b" até "z" (ou seja, a letra "a" não será aceita), e colocamos que o minimo de caracter aceito é 1 e o máximo é 100. EM NENHUM MOMENTO DEVE HAVER ESPAÇOS DENTRO DOS COLCHETES E NAS CHAVES. -->
<input pattern="[a-z]{1,100}" />


<!-- Estamos dizendo que o input irá aceitar da letra "a" até "z" e também da letra "A" até "Z" em maiúsculo. Também informamos que deve conter no mínimo 1 caracter e no máximo 50 caracteres -->
<input pattern="[a-zA-Z]{1,50}" />

<!-- Se colocarmos somente um número entre chaves, significa que é o mínimo de caracter e o máximo ao mesmo tempo, não pode ser menos do que 1, mas também pode ser mais do que 1. -->
<input pattern="[a-z]{1}" />

```

</br>

* __INPUTMODE__ 
> Utilizado para os smartphones, se colocarmos inputmode="numeric" por exemplo, o teclado numérico do usuário será aberto em seu celular caso interaja com o input.
```html
<input inputmode="numeric" type="text" placeholder="Digite um número" />
```

</br>

* __AUTOCOMPLETE__ 
> Permite especificar se vai haver permissão do "user agent" fornecer assistência automatizada no preenchimento de valores de campo de formulário, bem como orientação para o navegador quanto ao tipo de informação esperada no campo. O atributo pode ser usado tanto para um input específico ou para todo o formulário (todos os campos).

> ON: especifica que o "auto completar" está permitido, e assim o preenchimento de determinado campo pode ser feito de maneira "automizada" pelo usuário (pois seu próprio browser irá sugerir um email/senha por exemplo).

> OFF: especifica que o "auto completar" não está permitido. Ele dirá para o navegador parar de salvar dados inseridos pelo usuário em formulários para um futuro autocomplete (Isso varia de navegador para navegador). Isso fará o navegador parar de fazer caching dos dados do formulário na session history do navegador. Quando um dado é armazenado no cache no session history, os dados preenchidos pelo usuário serão mostrados para ele no caso dele submeter o formulário e clicar no botão Voltar e retornar à página original do formulário.

```html
<!-- Poderá colocar senhas salvas do usuário de forma automática neste input -->
<input type="password" autocomplete="on">

<!-- Será sugerido uma nova senha (criada pelo próprio browser) -->
<input type="password" autocomplete="new-password">

<!-- Também existe outros valores como..: email, family-name, address, country e diversos outros.
Utilize-os para o usuário preencher o campo de maneira mais rápida -->
```

</br>

* __MULTIPLE__ 
> O campo pode receber mais de um valor, que deve ser separado por vírgula. Raramente utilizado, podemos utilizar do mesmo num input do tipo "email". Também serve para aceitar multiplos arquivos quando usamos do input do tipo "file".
```html
<!-- Agora no input o usuário será permitido colocar por exemplo:
"fireguiquenbr@gmail.com, floraEd@gmail.com -->
<input type="email" multiple />
```

</br>

* __SPELLCHECK__ 
> Verificação ortográfica para determinado input ou para um formulário como um todo. Caso a palavra não exista, será colocado um subilhado embaixo da mesma. 
```html
<input type="text" spellcheck="true">
```

</br>

* __ACCEPT__ 
> Colocado para especificar quais arquivos você aceita num input do tipo "file"
```html
<!-- Só irá aceitar arquivos do tipo ".PDF" -->
<input type="file" accept=".pdf">

<!-- Só irá aceitar arquivos do tipo ".JS" -->
<input type="file" accept=".js">

<!-- Aceita apenas arquivos de imagem. Irá aceitar qualquer arquivo de imagem por conta do "*" -->
<input type="file" accept="imagem/*">
```

</br>

* __ENCTYPE__
> ``enctype='multipart/form-data'`` é um tipo de codificação que permite que os arquivos sejam enviados por meio de um POST. Muito simplesmente, sem essa codificação, os arquivos não podem ser enviados através do POST. Se você quiser permitir que um usuário carregue um arquivo por meio de um formulário, você deve usar esse tipo de encadeamento.

</br>

* __STEP__
> É um número que especifica a granularidade à qual o valor deve aderir ou a palavra-chave. É válido para os inputs numéricos, incluindo os tipos de data, mês, semana, hora, data-hora-local, número e intervalo. </br> O define o intervalo de passo ao clicar nos botões giratórios para cima e para baixo, mover um controle deslizante para a esquerda e para a direita em um intervalo e validar os diferentes tipos de data. Se não for explicitamente incluído, o padrão será 1 para e , e 1 tipo de unidade (minuto, semana, mês, dia) para os tipos de entrada de data/hora. O valor pode ser um número positivo - inteiro ou flutuante - ou o valor especial , o que significa que nenhuma etapa está implícita e qualquer valor é permitido (exceto outras restrições, como min e max).
```html
<!-- Só serão aceitos valores que pulem de cem em cem, ou seja, de centenza em centena.. Exemplo: 
100, 200, 300, 400.. -->
<input typ="number" step="100" />


<!-- Só serão aceitos valores que pulem de 2 em 2.. Exemplo: 
-8, -6, -4, -2, 0, 2, 4..  -->
<input typ="number" step="2" />
```

