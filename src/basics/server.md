# Axum 

[Axum] itself is for developing a server that handles routing, loading and utilizing [Tower](https://crates.io/crates/tower)
middleware, extracting data from requests headers and cookies and sending generated responses to the client.
Axum is built ontop of [Hyper](https://crates.io/crates/hyper) which is an HTTP client and [Tokio](https://crates.io/crates/tokio)
which is a async event handler.

# What Axum Does

[Axum] retrieves and handles all the requests from hyper, routing them via routes to move the requests
through the layering of middleware and into the methods(GET, PUT, ETC..) function handler.
It then handles the request and generates a response which then flows back through the laying of middleware
in reverse of the request. Hyper then returns the response to the end client.

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


[Axum]: https://github.com/tokio-rs/axum
