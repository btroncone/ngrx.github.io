# `usePostMiddleware(...middleware: Array<Middleware | Provider>)`

#### Arguments
1. `...middleware: Array<Middleware | Provider>`: An indefinite number of middleware arguments, order is guaranteed.

#### Returns
([*`Provider[]`*](store.md)): An array of middleware `Providers` .

#### Example
```ts
const stateLogger = state$ => state$
        .do(state => {
            console.log('CURRENT STATE:', state)
        });

//in application bootstrap
bootstrap(App, [
  provideStore({exampleReducer}),
  usePostMiddleware(stateLogger)
]);
```
