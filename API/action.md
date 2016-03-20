#` Action { type: string; payload?: any;  }`
Actions are the only method of communication between your application and store. In @ngrx/store, actions require both a `type` and an optional `payload`, or information carried by the action. Your actions should create a clear history of user interaction within your application.

####Example
```ts
//dispatching an action without a payload
this.store.dispatch({ type: 'INCREMENT' });

//dispatching an action with a payload
this.store.dispatch({ type: 'ADD_USER', payload: {name: 'Brian'} }),
```

