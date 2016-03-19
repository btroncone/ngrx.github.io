# Store

A store holds the whole [state tree](../Glossary.md#state) of your application.  
The only way to change the state inside it is to dispatch an [action](../Glossary.md#action) on it.  

### Store Methods

- [`select<R>(keyOrSelector: ((state: T) => R) | string | number | symbol): Observable<R>`](#select)
- [`getState()`](#getstate)
- [`dispatch(action: Action) : void`](#dispatch)
- [`replaceReducer<V>(reducer: Reducer<V>)`](#replaceReducer)

## Store Methods

### <a id='select'></a>[`select<R>(keyOrSelector: ((state: T) => R) | string | number | symbol): Observable<R>`](#select)

Select's appropriate slice of state based on supplied value, applying the `distinctUntilChanged` operator. `Select` is equivalent to `store.map(state => state[keyOrSelector]).distinctUntilChanged()`. 

#### Returns

*(Observable<R>)*: Observable of the requested state slice.

<hr>

### <a id='getState'></a>[`getState()`](#getstate)

Returns the current state tree of your application. This method should generally be avoided.

#### Returns

*(any)*: The current state tree of your application.

<hr>

### <a id='dispatch'></a>[`dispatch(action)`](#dispatch)

Dispatches an action. 

### <a id='replaceReducer'></a>[`replaceReducer<V>(reducer: Reducer<V>)`](#replaceReducer)

Replaces the reducer currently used by the store to calculate the state. 

#### Arguments

1. `reducer` (*Reducer<V>*) The next reducer for the store to use.

