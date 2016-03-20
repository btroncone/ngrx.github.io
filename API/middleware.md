# `Middleware { (observable: Observable<any>): Observable<any>;}` 

Store middleware provides pre and post reducer entry points for all dispatched actions. Middleware can be used for everything from logging, asynchronous event handling, to action or post action manipulation. 

#####Dispatched action pipeline:
1. Pre-Middleware : `(observable: Observable<Action>): Observable<Action>`
2. Reducer
3. Post-Middleware : `(observable: Observable<State>): Observable<State>`

Middleware can be configured during application bootstrap by utilizing the `usePreMiddleware(...middleware: Middleware[])` and `usePostMiddleware(...middleware: Middleware[])` helper functions. 

####Example
*Warning: Remember to import all utilized RxJS operators.*

```ts
import {bootstrap} from 'angular2/platform/browser';
import {App} from './myapp';
import {provideStore, usePreMiddleware, usePostMiddleware, Middleware} from "@ngrx/store";
import {counter} from "./counter";

const actionLog : Middleware = action => {
    return action.do(val => {
        console.warn('DISPATCHED ACTION: ', val)
    });
};

const stateLog : Middleware = state => {
    return state.do(val => {
        console.info('NEW STATE: ', val)
    });
};

bootstrap(App, [
  provideStore({counter},{counter : 0}),
  usePreMiddleware(actionLog),
  usePostMiddleware(stateLog)
]);
```

####Middleware with Dependencies
For middleware requiring dependencies the `createMiddleware(useFactory: (...deps: any[]) => Middleware, deps?: any[]): Provider` helper function is supplied. This allows you to quickly create middleware that relies on other Angular services, such as the `Dispatcher`.
####Example
- Create middleware provider:
```ts
export const thunk = createMiddleware(function(dispatcher: Dispatcher<Action>) {
  return function(all$: Observable<Action | Thunk>){
    const [thunks$, actions$] = all$.partition(t => typeof t === 'function');

    thunks$.forEach(thunk => thunk(action => dispatcher.dispatch(action));

    return actions$;
  }
}, [Dispatcher]);
```
- Initialize with `usePreMiddleware(...middleware: Middleware[])` or `usePostMiddleware(...middleware: Middleware[])` on application bootstrap:
```typescript
import {bootstrap} from 'angular2/platform/browser';
import {App} from './myapp';
import {provideStore, usePreMiddleware, Middleware} from '@ngrx/store';
import {thunk} from './thunk';
import {exampleReducer} from './exampleReducer';

bootstrap(App, [
  provideStore({exampleReducer}),
  usePreMiddleware(thunk)
]);
```

