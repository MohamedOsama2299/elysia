# Error Handling in Elysia

## File Name Suggestion

**`error_handling.md`**

---

## Overview

Error handling in Elysia allows you to manage errors gracefully instead of letting the server crash or return unclear responses. By handling errors properly, you can ensure stability, security, and a better developer and user experience.

Elysia provides a built-in lifecycle hook called `onError`, which is automatically triggered whenever an error occurs during request processing.

---

## onError Hook

The `onError` hook is executed immediately when an error is thrown.

It allows you to:

* Catch errors globally
* Inspect the error type and code
* Customize the response sent to the client
* Prevent unexpected server behavior

---

## Custom Errors

A **Custom Error** is an error you define yourself instead of relying on the default `Error` class.

Why use custom errors?

* Provide meaningful error types
* Attach specific error codes
* Control how errors are handled and returned

Custom errors are especially useful when you want predictable error handling across your application.

---

## Handling Custom Errors in onError

When an error is thrown, Elysia can recognize its type.

If the error is a **NicheError**, Elysia understands that it is a known and expected error, not a system failure.

This allows you to:

* Safely handle the error
* Return a controlled response
* Avoid exposing internal server details

---

## Validation Errors

Validation ensures that incoming data from the client is correct before the server processes it.

Elysia uses `t` to automatically validate:

* `body`
* `params`
* `query`
* `headers`

---

## What Happens When Validation Fails?

### Without Custom Error Handling

If no custom error is provided:

* Elysia returns a default error response
* The response is usually long and highly detailed
* It includes a large JSON structure describing the validation failure

This response may be difficult for clients to understand or consume.

---

## Validation Details Explained

Validation details provide a full report describing:

* Where the error occurred
* Which field failed validation
* What value was expected
* What value was actually received

While useful for debugging, this level of detail is often not suitable for client-facing responses.

---

## Error Response Customization

An **Error Response** defines what is returned to the client when an error occurs.

Instead of relying on the default response, you can:

* Customize the HTTP status code
* Return a clear and user-friendly message
* Hide unnecessary internal details

This results in cleaner APIs and a better client experience.

---

## Summary

By using `onError`, custom errors, and validation handling, Elysia enables you to:

* Handle errors safely and predictably
* Improve API clarity
* Protect internal implementation details
* Deliver meaningful error responses to clients

Proper error handling is a core part of building reliable and production-ready Elysia applications.
