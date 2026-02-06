# Elysia Framework – Overview

Elysia is a modern web framework known for **high performance**, **fast request handling**, **strong security**, and a **simple, readable syntax**. It is designed to make building APIs and web servers efficient and developer‑friendly.

---

## Routing & Paths

### 1. Static Path

A static path is a fixed route with no changing parts.

**Examples:**

* `/health`
* `/about`

The path is matched exactly as written.

---

### 2. Dynamic Path

A dynamic path contains a variable segment that changes based on user input.

**Example:**

* `/user/:id`

**Notes:**

* Dynamic values are accessed using `params`
* Useful for resources like users, products, posts, etc.

---

### 3. Optional Path Parameters

If you want a dynamic part to be optional, add `?` after it.

**Example:**

* `/user/:id?`

This route works with or without the `id` parameter.

---

### 4. Wildcards

Wildcards are used to match everything that comes after a specific path, regardless of length.

**Example:**

* `/files/*`

This will match any path under `/files`.

---

## Handler

The handler is what responds to the user’s request.

A handler can return:

* Function
* String
* Object
* File

The returned value is automatically sent as the response.

---

## Context

The context is a container that holds all information about the incoming request.

It includes:

* `body` → Data sent in the request (POST / PUT)
* `query` → Data after `?` in the URL
* `params` → Dynamic values from the path
* `headers` → Additional request information

---

## Status Codes

Status codes tell the client what happened with the request.

Common examples:

* `200 OK` → Request succeeded
* `404 Not Found` → Resource not found
* `400 Bad Request` → Invalid request

---

## Redirect

A redirect automatically sends the user to another URL.

Commonly used in:

* Login flows
* Registration flows
* Protected routes

---

## Validation

Validation ensures that incoming data is correct and matches expectations.

You can validate:

* `body` → POST / PUT data
* `query` → URL query parameters
* `params` → Dynamic path values (e.g. `/user/:id`)
* `headers` → Request metadata
* `cookies` → Stored client data
* `response` → Server response structure

---

## Lifecycle

The request lifecycle represents the journey of a request from the moment it reaches the server until a response is sent back.

**Example use cases:**

* Logging requests
* Authentication checks
* Performance monitoring

---

## Hooks

A hook is a function that runs at a specific lifecycle stage.

### Types of Hooks

#### 1. Route-level Hook

* Applied directly to a specific route
* Runs only for that route

#### 2. Interceptor Hook

* Applied globally
* Runs for all routes registered after it

---

## Guard

A guard helps group multiple hooks or schemas together.

**Benefits:**

* Avoid repeating hooks on every route
* Apply shared logic once
* Can also apply schemas to multiple routes

---

## Plugin

A plugin is a reusable server module.

It can include:

* Routes
* Hooks
* Guards

**Features:**

* Can be attached using `.use()`
* Can be dynamic and accept options
* Helps split the server into small, reusable modules

---

## Summary

Elysia provides a clean, fast, and scalable way to build backend services with:

* Powerful routing
* Strong validation
* Clear lifecycle control
* Modular architecture via guards and plugins

This makes it suitable for both small projects and large production systems.
