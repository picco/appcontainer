# appcontainer
Simple IoC container intended for splitting up your node app into modules

## Defining the Application Container
```javascript
var AppContainer = require('appcontainer');

var app = new AppContainer(__dirname, [
  'app/module1',
  'app/module2',
]);

console.dir(app.module1method());
console.dir(app.module2method());
```
## Defining a module
```javascript
module.exports = function(app) {
  // app === this, use the one you prefer.
  // you have access to this.cwd which references the directory of the App Container.
  app.module1method = function() {
    return 'beep';
  }
}
```
That's it!
