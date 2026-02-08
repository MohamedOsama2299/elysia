    # 1️⃣ Core Idea: What is a Macro?

In **Elysia**, every route can have options like:

- `body` (the shape of the incoming data)  
- `cookie` (required cookies)  
- `beforeHandle` (a function that runs before the route handles the request)  
- Anything else.

If you have multiple routes that need the **same configuration**, you don’t want to write it every time.

This is where **Macros** come in:

A **Macro** is a **reusable** piece of configuration you can apply to multiple routes.

It’s like a function, but for **route options**.

And it’s **type-safe** if you’re using **TypeScript**.
