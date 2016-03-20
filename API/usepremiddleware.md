# `usePreMiddleware(...middleware: Array<Middleware | Provider>)`

#### Arguments
1. `...middleware: Array<Middleware | Provider>`- An indefinite number of middleware arguments, order is guaranteed.

#### Returns
([*`Provider[]`*](store.md)): An array of middleware `Providers`.

#### Example
```ts
const actionLogger = action$ => action$
        .do(action => {
            console.log('DISPATCHED ACTION:', action)
        });

//in application bootstrap
bootstrap(App, [
  provideStore({exampleReducer}),
  usePreMiddleware(actionLogger)
]);
```
