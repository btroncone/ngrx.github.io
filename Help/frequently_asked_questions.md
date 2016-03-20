# Frequently Asked Questions

Commonly asked questions and issues regarding @ngrx/store setup and use.

### How does @ngrx/store compare to Redux?
Check out this [conversation](https://github.com/ngrx/store/issues/16) for a full rundown on the inspiration for store and how it compares to vanilla redux.

### Can I access the current application state in preMiddleware?
At this time there is no clean way to access store in `preMiddleware`. Consider using `postMiddleware` when access to store is required.

### How do I utilize dependencies in middleware?
@ngrx/store provides a [`createMiddleware`](../API/createmiddleware.md) helper function, making it easy to inject application dependencies into your middleware.

### More to come...

## Other issues?

No worries! We have an active gitter channel [![Join the chat at https://gitter.im/ngrx/store](https://badges.gitter.im/ngrx/store.svg)](https://gitter.im/ngrx/store?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) or feel free to [create an issue](https://github.com/ngrx/store/issues).  
