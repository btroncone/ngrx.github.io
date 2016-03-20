# `provideStore(reducer: any, initialState?: any)`

#### Arguments

1. `reducer : Reducer | [key:string]: Reducer` - Reducer or map of reducer functions. If multiple reducers are supplied reducers are 
automatically combined to create root reducer. You will rarely need to call `combineReducers` manually.

2. `initialState? : any` : Initial state for given reducer(s). This can be useful if supplying initial state from another service, 
or in the future when using store in universal applications.

#### Returns
([*`Store`*](store.md)): Application store.

#### Example
```ts
import {bootstrap} from 'angular2/platform/browser';
import {App} from './app';
import {provideStore} from "@ngrx/store";
import {counter} from "./reducers/counter";

export function main() {
  return bootstrap(App, [
      provideStore({counter}, {counter : 0}),
  ])
  .catch(err => console.error(err));
}

document.addEventListener('DOMContentLoaded', main);
```
