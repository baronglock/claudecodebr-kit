# Security: Protecting Your Software

*Protection*

Security is not optional. Every piece of software that goes to production needs to consider these fundamentals from the start.

### Authentication

Use **JWT** (JSON Web Tokens) for stateless APIs, **OAuth 2.0** for social login (Google, GitHub), and **bcrypt** for password hashing. Never store passwords in plain text.

### HTTPS / SSL

All traffic must be encrypted. Use **Let's Encrypt** for free certificates. Platforms such as Vercel and Railway already include automatic SSL.

### Environment Variables (.env)

API keys, secrets and credentials go in `.env`, NEVER in the code. Add `.env` to `.gitignore`. Use `.env.example` as a template.

### Rate Limiting

Limit requests per IP/user to prevent abuse. Use `express-rate-limit` (Node) or equivalent middleware. Protect authentication endpoints in particular.

### Input Validation

Sanitize ALL user input. Prevent **XSS** (Cross-Site Scripting) with HTML escaping, and **SQL Injection** with parameterized queries or ORMs such as Prisma/Drizzle.

### LGPD / Compliance

If you collect data from Brazilian users (LGPD is Brazil's data protection law): have a privacy policy, allow data deletion, obtain explicit consent. Use cookies only with opt-in.

> **Tip for Claude Code:** When starting a project, ask: *"Implement JWT authentication with bcrypt, environment variables via .env, rate limiting on public endpoints and input validation with zod/joi."* The agent will configure everything automatically.

```
Analyze the current project and implement the following security measures:

1. JWT authentication with refresh tokens
2. Password hashing with bcrypt (salt rounds: 12)
3. Rate limiting middleware (100 req/15min per IP)
4. Input validation with Zod on all routes
5. HTML sanitization to prevent XSS
6. Parameterized queries (never concatenate SQL)
7. Helmet.js for HTTP security headers
8. CORS configured only for allowed domains
9. .env.example file with all the required variables
10. Logging middleware for auditing

Explain each measure implemented.
```

> **Never deploy without:** active HTTPS, hashed passwords, .env out of the repository, input validation on all routes, and rate limiting on public endpoints.
