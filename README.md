# JavaScript Libraries Baby Steps
Quando eu estava aprendendo a programar eu odiava ter que usar algo que não sabia como foi feito, me sentia como se eu tivesse engessado por não conhecer aquilo a fundo.
Onde eu não estava errado. Pois existem padrões que se você os conhecesse, não de maneira aplicada mas sim superficial, já ajudaria a ampliar absurdamente o seu "range" de possibilidades de aprendizado. Pois pelo menos as bibliotecas padrões de mercado seguem esses padrões, onde por conta disso lhe desintegraria de um ecossistema engessado.
Esse é o proposito deste repositório. É preparar e mostrar os padrões das bibliotecas mais conhecidas do mercado.


## Primeiro passo - callbacks

```javascript
  function aoQuadrado( numero, outputTunnel ) {
    outputTunnel( numero * numero ); 
  }
  
  aoQuadrado( 2, function(output) { 
    console.log(output); // retorno: 4
  }) 
```

#### Eu poderia usar o return?
Sim, nesse caso o return seria o ideal, mas se nos depararmos com um caso diferente como o de um click ou alguma ação que é assíncrona, seria o mais correto a se fazer. Pois ao criar um callback, você desprende o código de uma execução síncrona, deixando assim, a possibilidade de chamar o seu callback apenas quando a sua operação estiver pronta.
##### Como por exemplo:
```javascript
  function showAlertTextWithDelay(text, seconds, onAlertShow){
    setTimeout( function(){
      onAlertShow()
      alert(text)
    }, seconds * 1000);
  } 
  
  function onAlertCall(){
    console.log("Alert is up")
  }
  
  showAlertTextWithDelay( 'Hello World', 3, onAlertCall)
```

### Onde vou utilizar isso?

#### Jquery
```javascript

  var onClickCallback = function(event){
    // Aqui voce terá acesso aos dados do evento
  }

  $('elementoDom').click(onClickCallback)

```
#### Angular
```javascript

  angular.module('MyApp',[])
  angular.module('MyApp').controller('MyController', function ($scope){
    // Acesso ao scope do controller
  })
```
> Dica. Não use uma variável para guardar a instancia de seu modulo, como é muito encontrado nos "step-by-step" por ai. Fazendo isso você pode dar um acesso global para sua aplicação, dando a liberdade de uma possível invasão.

## Segundo passo - Manipulação DOM
Já vi pessoas utilizando jQuery apenas pelo seletor de elementos dom. Sim, é bom, é garantido. Mas dependendo de sua aplicação, essa lib pode ser um peso dispensável devido as novas features implementas pelos navegadores.

#### Vanilla
```javascript
  document.querySelector('#idDoMeuElemento.classeDoMeuElemento') // Unico elemento
  document.querySelectorAll('#idDosMeusElementos.classeDosMeusElementos') // Array resultando na seleção
```
#### jQuery
```javascript
  $('#idDoMeuElemento.classeDoMeuElemento')
  $('#idDosMeusElementos.classeDosMeusElementos')
```

Obs. Não são todos os navegadores que suportam o `querySelector`.
[Link para a tabela de compatibilidade](https://caniuse.com/#search=querySelector)

## Terceiro passo - Promises
Quando me deparei com uma requisição ajax que nao seguia o padrão de callbacks fiquei assustado. Pois não sabia como funcionava o `$http` do Angular

#### Angular
```javascript
$http.get("http://google.com")
  .then( function(response){
    console.log(response.data)
  })
  .catch( function(error){
    console.log(error)
  })
```
#### Vanilla
```javascript
function myGet (url){
  return new Promise(function(resolve, reject){
    if(url == "google.com"){
      resolve("<h1>Google</h1>")
    } else {
      reject("Url not found")
    }
  })
}
myGet("google.com").then(console.log).catch(console.log)
```

# Future steps

- [X] Promises
- [X] Dom Selection
- [ ] Http Requests
- [X] Callback
- [ ] Uso do this, e bind
- [ ] Filters
- [ ] ES6 things

Por favor, contribua para esse projeto =), eu não gosto de ver as pessoas passando pelo que eu passei.
