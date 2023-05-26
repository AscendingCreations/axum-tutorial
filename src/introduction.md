# Introduction

In this tutorial, we aim to teach how to build web applications using [axum] web
framework. However, If you are just getting started with rust we do recommend that you start 
with the [Rust Programming book](https://doc.rust-lang.org/stable/book/) or
if you prefer a PDF book you can take a look at [The Rust Programming Language book](https://edu.anarcho-copy.org/Programming%20Languages/Rust/rust-programming-language-steve-klabnik.pdf) .

## What is axum?

[axum] is a web framework developed by [David Pedersen].

[axum] provides utilities to create tower services which can be served using a
compatible HTTP web server. This process will be explained later in tutorial.

## Why use axum?

With [axum] you can conveniently create fast, flexible and modular web
applications.

- Fast: Allows you to write really fast applications. See [this
  benchmark](https://github.com/programatik29/rust-web-benchmarks/blob/master/result/hello-world.md)
  comparing [axum] with other rust frameworks.
- Flexible: Provides bunch of ways you can change your applications behavior.
- Modular: You can use/reuse custom and existing utilities.
- Minimal: Doesn't aim to solve every single possible problem, instead by using
  [tower] as an interface, allows you to easily customize and implement
  features you want. This might be really important if you need a feature that
  isn't available in the ecosystem.

### Development - Todo List

> - [X] Create tutorial structure.
> - [ ] Fill empty sections.
> - [ ] Support with examples.
> - [ ] Rearrange contents if needed.
> - [ ] Ask feedback from new users.

[axum]: https://github.com/tokio-rs/axum
[tower]: https://github.com/tower-rs/tower
[David Pedersen]: https://github.com/davidpdrsn
[tokio team]: https://github.com/tokio-rs
