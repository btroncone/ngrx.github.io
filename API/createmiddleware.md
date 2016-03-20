# `createMiddleware(useFactory: (...deps: any[]) => Middleware, deps?: any[])`

__@ngrx/store__ exposes a `createMiddleware` helper function in order to quickly create middleware with dependencies.
#### Arguments
1. `useFactory: (...deps: any[]) => Middleware` - Factory function accepting any number of application dependencies (supplied by second parameter). 
2. `deps?: any[]` - An array of dependencies to be injected into factory function.

#### Returns
([*`Provider`*](https://angular.io/docs/ts/latest/api/core/Provider-class.html)): Provider for given middleware.

#### Example
```ts
import {bootstrap} from 'angular2/platform/browser';
import {App} from './myapp';
import {provideStore, usePreMiddleware} from '@ngrx/store';
import {Logger} from './services/logger';
import {counter} from "./counter";

const preLogger = createMiddleware(logger => {
    return action$ => action$
        .do(action => {
            logger.log(action)
        });
}, [Logger]);

bootstrap(App, [
  provideStore({counter}),
  usePreMiddleware(preLogger)
]);
```
