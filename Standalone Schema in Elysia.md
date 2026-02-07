# Standalone Schema in Elysia

In Elysia, you use **schemas** to validate incoming data (like the request body).

## Guard vs Route

The **Guard** acts like a security guard in front of routes:

- Example:  
  - Guard says: `age` **must exist**  
  - Route says: “No, I want `name` instead”  

Without standalone schema, the route overrides the guard:

```ts
.guard({
  body: t.Object({
    age: t.Number()
  })
})
.post('/user', ({ body }) => body, {
  body: t.Object({
    name: t.String()
  })
})
```

Result: body contains only `name`.

---

## Using Standalone Schema

To make **guard schema** and **route schema** work together:

```ts
.guard({
  body: t.Object({
    age: t.Number()
  }),
  schema: 'standalone'
})
.post('/user', ({ body }) => body, {
  body: t.Object({
    name: t.String()
  })
})
```

- Guard → validates `age`  
- Route → validates `name`  
- If either is missing → **validation error**

---

## Schema Library Interoperability

- Not all schemas need to use the same library.  

Example:

- Guard’s schema → written with **Zod**  
- Route’s schema → written with **Elysia.t**

Both:  
✅ Work together  
✅ No conflicts  
✅ Validation passes  

Elysia is smart and flexible; it won’t force all schemas to use the same library.
