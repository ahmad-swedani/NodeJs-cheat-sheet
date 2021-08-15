# middleware

## Write your own middleware to use in Express applications 🧐

> what is `middleware` ??

middleware functions are the function that have access to the `request object (req)`, `response object (res)` and `next() function` on the application req-res cycle.

> what is `next() function` ??

The next function is a function in the Express router which, when invoked, executes the middleware succeeding the current middleware.

## Middleware functions can perform the following tasks:

- Execute any code.
- Make changes to the request and the response objects.
- End the request-response cycle.
- Call the next middleware in the stack.

> Example to Write own middleware:

```js
var express = require("express");
var app = express();

function MyMiddleware(req, res, next) {
  req.requestTime = new Date().toISOString();
  next();
}
app.use(MyMiddleware);
```

this middleware will change the request object by adding a method called `requestTime`.

you can use `requestTime method` on any route you create after it

---

if you are cerise about the built-in method for [request method](https://expressjs.com/en/4x/api.html#req) and [response method](https://expressjs.com/en/4x/api.html#res) and you want to check them just click 😎
