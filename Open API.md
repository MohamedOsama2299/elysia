# OpenAPI in Elysia

OpenAPI is like a **manual for your API**.

## Goal

Anyone should be able to understand:

- What the routes are (e.g., `/user`)  
- What data needs to be sent (e.g., `{ age: 25 }`)  
- What the server response will be (e.g., `{ success: true }`)

In **Elysia**, there’s a ready-made plugin that does all of this automatically: `@elysiajs/openapi`.

---

## Adding Details for Each Route

You can add `summary`, `description`, and `tags` for each route to make the documentation **complete and clear**.

---
## Reference Models (Reusable Schemas)

Instead of writing the same schema in every route, you can define it **once** as a model and use it in any route.

---

## Type Gen (Type Generation)

In the context of **Elysia** and **OpenAPI**:

- The idea is to **avoid writing everything manually** in the documentation.  
- Elysia can **infer documentation directly from the code**.  

This means your **TypeScript types** or the result of a **database query** can automatically become an **OpenAPI schema**.

---

## Why is this Useful?

### Without Type Gen:

- You need to manually write for each route:  
  - What data is required (`body`)  
  - What the response will be (`response`)  

This is tedious, especially with large databases.

### With Type Gen:

- Elysia looks at the code (or database query) and knows:  
  - What fields are incoming  
  - Their types (number, string, boolean…)  

It then **generates OpenAPI documentation automatically** without manual effort.
