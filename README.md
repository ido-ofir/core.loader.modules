# core.loader.modules

load modules from plugin definition

related to <a href="https://github.com/ido-ofir/core.type.module">core.type.module</a>

```js
let core = new require('core.constructor')();
 
core.plugin(
    require('core.type.module'),
    require('core.loader.module')
);

// plugins can now declare modules on the plugin definition object:
core.plugin({
    name: 'test',
    modules: [
        {
            name: 'someModule',
            get(){
                return { a: 5 };
            }
        }
    ]
});

// require this new module
core.require(['test.someModule'], someModule => { ... })

// exists on core.modules
core.modules['test.someModule'];

// exists on plugin modules
core.plugins.test.modules.someModule;
```
