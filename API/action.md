#` Action { type: string; payload?: any;  }`
Actions are the only method of communication between your application and store. In __@ngrx/store__, actions require a `type` and an optional `payload`, or information carried by the action. Your actions should create a clear history of user interaction within your application.
*Note: Since store itself is a BehaviorSubject you can subscribe it directly to action emitting streams.*

####Example
```ts
//dispatching an action without a payload
this.store.dispatch({ type: 'INCREMENT' });

//dispatching an action with a payload
this.store.dispatch({ type: 'ADD_USER', payload: {name: 'Brian'} });
```

#### Example #2 - Subscribe Store to Action Emitting Stream
```
private actions$: Subject<Action> = new Subject<Action>();
//somewhere later...
this.actions$.subscribe(store)
```


