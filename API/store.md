# Store

A store holds the entire state tree for your application. There will be one store instance per application.  

### Store Methods

- [`select<R>(keyOrSelector: ((state: T) => R) | string | number | symbol): Observable<R>`](#select)
- [`getState()`](#getstate)
- [`dispatch(action: Action) : void`](#dispatch)
- [`replaceReducer<V>(reducer: Reducer<V>)`](#replaceReducer)

## Store Methods

### <a id='select'></a>[`select<R>(keyOrSelector: ((state: T) => R) | string | number | symbol): Observable<R>`](#select)

Select slice of state based on supplied value. The `select(keyOrSelector)` method is equivalent to `store.map(state => state[keyOrSelector]).distinctUntilChanged()`. 

#### Returns

*(Observable<R>)*: Observable of selected state.

<hr>

### <a id='getState'></a>[`getState()`](#getstate)

Returns the current state tree of your application. As a rule of thumb this method should be avoided.

#### Returns

*(any)*: The current state tree of your application.

<hr>

### <a id='dispatch'></a>[`dispatch(action)`](#dispatch)

Dispatches an action. This is equivalent to calling `dispatcher.dispatch`.

### <a id='replaceReducer'></a>[`replaceReducer<V>(reducer: Reducer<V>)`](#replaceReducer)

Replaces specified reducer. 

#### Arguments

1. `reducer` (*Reducer<V>*) The next reducer for the store to use.

