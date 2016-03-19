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

#### Arguments

1. `keyOrSelector: ((state: T) => R) | string | number | symbol` - Function, string, number, or symbol representing the appropriate slice of state to be returned.

#### Returns

*(Observable<R>)*: Observable of selected state.

<hr>

### <a id='getState'></a>[`getState()`](#getstate)

Returns the current state tree of your application. As a rule of thumb this method should be avoided.

#### Arguments

No arguments

#### Returns

*(any)*: The current state tree of your application.

<hr>

### <a id='dispatch'></a>[`dispatch(action : Action)`](#dispatch)

Dispatches an action. This is equivalent to calling `dispatcher.dispatch`.

#### Arguments

1. `action : Action` - Action to be dispatched.

#### Returns

*(void)*

<hr>

### <a id='replaceReducer'></a>[`replaceReducer<V>(reducer: Reducer<V>)`](#replaceReducer)

Replaces specified reducer. 

#### Arguments

1. `reducer` (*Reducer<V>*) The reducer to replace current reducer.

#### Returns

*(void)*

