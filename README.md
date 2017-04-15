# JavaScript Libraries Baby Steps

Quando eu estava aprendendo a programar eu odiava ter que usar algo que não sabia como foi feito, me sentia como se eu tivesse engessado por não conhecer aquilo a fundo.
Esse é o proposito deste repositório. É preparar e mostrar os padrões das bibliotecas mais conhecidas do mercado.

## Primeiro passo - callbacks

```javascript
  function sum( input, outputTunnel ) {
    outputTunnel( input ); 
  }
  
  sum( 2, function(output) { 
    console.log(output);
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

  $('elementoDom').on('click', onClickCallback)

```




# Future steps

- [ ] Promises
- [ ] Dom Manipulation
- [ ] Http Requests
- [X] Callback

Por favor, contribua para esse projeto =), eu não gosto de ver as pessoas passando pelo que eu passei.
