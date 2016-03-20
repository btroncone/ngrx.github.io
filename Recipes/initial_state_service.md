# Providing Initial State Through Service
For times when the intial state of a reducer depends on some value derived from an application dependency, such as a service, @ngrx/store provides an `INITIAL_STATE` token. It is important that you include this provider __after__ `provideStore`.

### Example
```ts
import {provideStore, INITIAL_STATE} from "@ngrx/store";

bootstrap(App, [
      provideStore({counter}),
      provide(INITIAL_STATE, {
        deps: [MyCounterService],
        useFactory(counterService){
          return {counter: service.getCounterValue()};
      }
    ])
});
```