# Parte 01: Hello Word

### Menu
 -  [Inicio](https://github.com/eptaccio/aula-angularjs)
 -  01 - Hello Word
 -  [02 - Forms](https://github.com/eptaccio/aula-angularjs/tree/master/parte02)
 -  [03 - Services](https://github.com/eptaccio/aula-angularjs/tree/master/parte03)
 -  [04 - Diretivas](https://github.com/eptaccio/aula-angularjs/tree/master/parte04)
 -  [05 - SPA](https://github.com/eptaccio/aula-angularjs/tree/master/parte05)

Ao iniciarmos nosso primeiro app, criaremos um index.hml como de costume e então usaremos o atributo `ng-app` para declararmos nosso primeiro e principal modulo da aplicação. O atributo ng-app pode ser utlizado em qualquer elemento da pagina, nesse exemplo usaremos na tag `<html>`.
**Two way data binding **
Two way data binding cria uma ligação direta bidirecional entre o model e controller (que?), resumindo as alterações feitas no model pela view são vistas pelo controller e vise versa, isso ficará mais claro no nosso primeiro exemplo.

```html
<html lang="pt-br" data-ng-app="app"> <!-- declaração do modulo -->
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>ui-router-example</title>
  </head>
  <body data-ng-controller="IndexController"> <!-- declaração do controller -->

    <h1>{{helloWord}}</h1> <!-- exibindo valor de um (model use {{}}) -->
    <input type="text" data-ng-model="helloWord">

  </body>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.6/angular.min.js"></script>
  <script>
    angular
    .module('app', [])
    .controller('IndexController', IndexController);

    IndexController.$inject = ['$scope']; 
    function IndexController($scope){
      $scope.helloWord = 'Escola de ti 2017';
    };
  </script>
</html>
```
No nosso primeiro exemplo podemos notar a criação do modulo usando a sintaxe `angular.module('nomeString', [])` e em seguida por meio de encadeamendo o controller `.controller('nomeDoControllerString', funcaoQueRepresentaOcontroller)`.
Na função que representa o controller podemos ver o `$scope` sendo usado por meio de injeção de dependencias, `$scope` é objeto que contem o valor do model. Uma instancia desse objeto é disponibilizado para a view, cada contoller ou diretiva (chegaremos nisso) possui seu `$scope`.

# live-demo

Live-demo disponível em:
[https://eptaccio.github.io/aula-angularjs/parte01/index.html](https://eptaccio.github.io/aula-angularjs/parte01/index.html)

