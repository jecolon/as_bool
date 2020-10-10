# as_bool
Provides an expanded notion of what is *true* and what is *false*.

Specifically with the AsBool trait, which an implementing type can
use to express how it should be represented in a boolean context.

This crate also provides implementations of AsBool for Rust's builtin types
and collections from the Standard Library. These implementations provide a
truth table similar to the *Groovy Truth* implemented in the Groovy
programming language. The truth table can be described as follow:

* booleans behave as expected.
* all non-zero numbers are `true`.
* `0` , `0.0` , `f32::NAN`, `f64::NAN`, and `'\0'` are `false`.
* non-empty strings are `true`.
* empty strings are `false`.
* non-empty collections are `true`.
* empty collections are `false`.
* `None` is always `false`.
* `Err` is always `false`.
* `Ok` and `Some` are unwrapped and the contained item is evaluated according
to the preceding rules.

Documentation: https://docs.rs/as_bool

