# API Reference

Complete API reference for @ngrx/store.

### Types
* [Store](store.md)
* [Reducer](reducer.md)
* [Action](action.md)
* [Middleware](middleware.md)

### Top-Level Exports

* [provideStore(reducer: any, initialState?: any)](providestore.md)
* [usePreMiddleware(...middleware: Array<Middleware | Provider>)](usepremiddleware.md)
* [usePostMiddleware(...middleware: Array<Middleware | Provider>)](usepostmiddleware.md)
* [createMiddleware(useFactory: (...deps: any[]) => Middleware, deps?: any[]](createmiddleware.md)

### Store API

* [Store](store.md)
  * [select<R>(keyOrSelector: ((state: T) => R) | string | number | symbol)](store.md#select)
  * [getState()](store.md#getstate)
  * [dispatch(action : Action)](store.md#dispatch)
  * [replaceReducer<V>(reducer: Reducer<V>)](store.md#replaceReducer)
