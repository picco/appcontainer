# appcontainer
Simple IoC container intended for splitting up your node app into modules

## Defining the Application Container
```javascript
var AppContainer = require('appcontainer');

var app = new AppContainer(__dirname, [
  // maps to file ./app/module1.js
  'app/module1',
  // maps to file ./app/module2.js  
  'app/module2',
]);

// The app object has now been extended with additonal methods by the modules.
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
