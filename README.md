# JavaScript Libraries Baby Steps

Quando eu estava aprendendo a programar eu odiava ter que usar algo que não sabia como foi feito, me sentia como se eu tivesse engessado por não conhecer aquilo a fundo.
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

#### Por que não usar o return?
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


# Future steps

- [ ] Promises
- [X] Dom Selection
- [ ] Http Requests
- [X] Callback

Por favor, contribua para esse projeto =), eu não gosto de ver as pessoas passando pelo que eu passei.
