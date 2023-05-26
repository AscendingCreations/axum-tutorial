# Hello World Example

In the following example we will show the basics of how to set up a very basic 
axum server example using a GET request function handler to return a Hello World 
response. This example will not use any extensions or extractors and is the most basic
example for axum.

```rust
use axum::{routing::get, Router};

#[tokio::main]
async fn main() {
    // We add our function handler for our GET method which returns the response Hello, world!
    // when the root route is called. Example http://127.0.0.1
    let app = Router::new().route("/", get(|| async { "Hello, world!" }));

    // We will then load and bind axums server to 0.0.0.0:3000 which means it handles any requests
    // to port 3000. If you just want localhost then set this to 127.0.0.1
    axum::Server::bind(&"0.0.0.0:3000".parse().unwrap())
    // We then bind our routes to axum so it can handle them.
        .serve(app.into_make_service())
    // We finally establish the service within Tokio's handlers.
        .await
        .unwrap();
}
```


# [Next](routing.md)
