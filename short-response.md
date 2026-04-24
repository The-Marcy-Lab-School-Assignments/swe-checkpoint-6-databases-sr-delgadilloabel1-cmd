# Short Response: Databases Checkpoint

Answer each question below in complete sentences. Aim for 3–5 sentences per answer — enough to show that you understand the concept, not just that you memorized a definition. Use the exact terms and concepts from the lessons, but write in your own words. Specific examples and analogies are encouraged.

---

## Question 1

What is the difference between **authentication** and **authorization**? Give a concrete example of how a user would encounter each in the context of a fullstack web application.

**Your answer:**

Authentication and authorization are two distinct steps in access control within a web application. **Authentication** is the process of verifying a user’s identity, typically through credentials like a username and password. **Authorization**, on the other hand, determines what actions or resources that authenticated user is allowed to access.

For example, Instagram, a user first authenticates by logging in with their credentials. Once authenticated, authorization rules define what they can do, such as: creating, updating, or deleting their own posts, while only being able to view \*not modify\* other users’ content. This separation ensures both secure identity verification and proper access control.

---

## Question 2

Why should passwords **never** be stored as plaintext in a database? Explain what hashing is and its key properties that allow a server to verify a password without ever storing the original?

**Your answer:**

Passwords should never be stored as plaintext in a database because if the database is ever compromised, attackers would immediately have access to every user’s actual password. This is a major security risk, especially since many users reuse passwords across multiple sites.

Hashing is the process of converting a password into a fixed-length string of characters using a one-way cryptographic function. A key property of hashing is that it is **irreversible**, meaning the original password cannot be derived from the hash. Another important property is that the same input always produces the same output, allowing the server to verify a password by hashing the user’s login attempt and comparing it to the stored hash. This way, the server never needs to store the original password.

## Question 3

Explain what it means when we say that "HTTP is stateless"? Explain why cookies are necessary in order to keep users logged-in across multiple sessions and how a server and a client work together to achieve this functionality.

**Your answer:**

When we say that HTTP is **stateless**, it means that each request from a client to a server is independent, and the server does not automatically remember any information about previous requests. In other words, every request is treated as if it is the first time the client is interacting with the server.

Cookies are necessary to maintain login state because they allow the server to store a small piece of identifying data on the client. When a user logs in, the server creates a session and sends a cookie to the client, which is then included in future requests. The server reads this cookie to recognize the user and keep them logged in across multiple requests. This collaboration between client and server allows stateful behavior on top of a stateless protocol.

---

## Question 4

A frontend can hide a "Delete Account" button from users who aren't logged in. Why isn't that enough to protect the `DELETE /api/users/:id` route on the server? What are the two layers of protection that the backend implements to protect against this?

**Your answer:**

Hiding a "Delete Account" button on the frontend is not enough because frontend code can be easily bypassed or manipulated by a user. An attacker could still manually send a request to the `DELETE /api/users/:id` endpoint using tools like Postman or curl.

To properly secure the route, the backend must implement two layers of protection: **authentication** and **authorization**. Authentication ensures the user is logged in and their identity is verified. Authorization ensures that the user has permission to perform the action, such as only allowing a user to delete their own account. Both layers are necessary to fully protect sensitive routes.

## Question 5

What is **SQL injection**? Explain what makes the code below unsafe, then describe how parameterized queries fix the problem.

```js
// Unsafe — never do this!
pool.query(`SELECT * FROM users WHERE username = '${username}'`);
```

**Your answer:**

---

## Question 6

What problem does the **`/api/auth/me`** endpoint pattern solve? When does the frontend call it and what does it return?

**Your answer:**

---
