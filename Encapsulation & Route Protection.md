# Elysia Core Concepts Guide

This document provides a structured overview of core **Elysia** concepts, including **encapsulation**, **scope**, **guards**, and **cookie handling**.

---

## Encapsulation

Encapsulation is used to validate incoming requests before allowing access to routes.

For example, you can check whether a required query parameter exists and return a **401 Unauthorized** response if it does not.

Encapsulation helps:

* Protect routes
* Enforce request rules
* Centralize validation logic

---

## Scope

Scope defines where plugins, guards, or logic apply within the application hierarchy.

### Types of Scope

* **Local**

  * Affects only the current instance and its children

* **Scoped**

  * Applies upward and downward within the same instance tree

* **Global**

  * Applies everywhere in the application

Scope helps control how far logic and behavior spread across the app.

---

## Guard

A **Guard** is a hook that runs before any route handler.

Common uses:

* Validate query parameters
* Validate request body
* Validate headers
* Authentication and authorization

Guards allow you to protect multiple routes with shared logic.

---

## Cookies

Cookies are available in the **context** of every route.

Each cookie:

* Has a `.value` property
* Can be read or modified
* Automatically reflects changes in the response when updated

---

## Type Annotation / Schema

Cookies can be typed using `t.Object` to ensure:

* Strong type safety
* Validated structure
* Predictable data

This reduces runtime errors and improves developer experience.

---

## Cookie Attributes

Common cookie options include:

* `httpOnly` → Prevents access from browser JavaScript
* `path` → Defines the URL path where the cookie is active
* `secure` → Cookie is sent only over HTTPS
* `sameSite` → Controls cross-site cookie behavior
* `maxAge` → Defines the cookie expiration time

---

## Cookie Management

* Use `.set()` to update multiple cookie attributes at once
* Use `.remove()` to delete a cookie from the browser so it will not be sent in future requests

This provides full control over cookie lifecycle.

---

## Cookie Signature

Cookie signatures protect cookies from tampering.

* A secret can be defined globally
* Or defined per cookie

This ensures cookie integrity and security.

---

## Conclusion

These features enable **Elysia** to provide:

* Secure backend applications
* Scalable architecture
* Strong type safety
* Clean and maintainable structure

Elysia is well-suited for both small services and large production systems.
