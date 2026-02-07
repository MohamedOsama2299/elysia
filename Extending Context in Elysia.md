# Context in Elysia 

## What is Context?

Context is like a **container**.

For every request that reaches the server:

- Elysia creates a Context
- It puts some ready data inside it
- You can add your own data
- The handler can use all of this data

---

## Ways to Extend the Context

There are **four ways** to add data to the Context:

- Decorate
- State
- Derive
- Resolve

Each one is used in a different situation.

---

## 1. Decorate

Decorate is a **fixed value** added to the server.

### What does that mean?

- Created **once**
- Used by **all requests**
- **Cannot change**
- Same value for everyone

### When to use it?

- Helper functions
- Shared tools
- Constants

---

## 2. State

State is a **shared variable**.

### What does that mean?

- Value **can change**
- All requests can see it
- If one request changes it, everyone is affected

### When to use it?

- Counters
- Shared values
- Global data (use carefully)

---

## 3. Derive

Derive creates data **from the request**.

### What does that mean?

For every request:

- It reads data from:
  - Headers
  - Query
  - Body
- Runs **before validation**
- Data is **not guaranteed**

### When to use it?

- Preparing data
- Extracting values
- Simple request setup

---

## 4. Resolve

Resolve is like Derive, but **safer**.

### What is the difference?

- Resolve runs **after validation**
- Data is **guaranteed to be correct**

### Simple rule

- Not sure about the data? → **Resolve**
- Just preparing data? → **Derive**

---

## Summary

- Decorate → fixed value
- State → shared changing value
- Derive → before validation
- Resolve → after validation
