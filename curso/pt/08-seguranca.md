# Segurança: Protegendo Seu Software

*Proteção*

Segurança não é opcional. Todo software que vai para produção precisa considerar esses fundamentos desde o início.

### Autenticação

Use **JWT** (JSON Web Tokens) para APIs stateless, **OAuth 2.0** para login social (Google, GitHub), e **bcrypt** para hash de senhas. Nunca armazene senhas em texto puro.

### HTTPS / SSL

Todo tráfego deve ser criptografado. Use **Let's Encrypt** para certificados gratuitos. Plataformas como Vercel e Railway já incluem SSL automático.

### Variáveis de Ambiente (.env)

Chaves de API, secrets e credenciais vão no `.env`, NUNCA no código. Adicione `.env` ao `.gitignore`. Use `.env.example` como template.

### Rate Limiting

Limite requisições por IP/usuário para evitar abuso. Use `express-rate-limit` (Node) ou middlewares equivalentes. Proteja especialmente endpoints de autenticação.

### Validação de Input

Sanitize TODA entrada do usuário. Previna **XSS** (Cross-Site Scripting) com escape de HTML, e **SQL Injection** com queries parametrizadas ou ORMs como Prisma/Drizzle.

### LGPD / Compliance

Se coleta dados de usuários brasileiros: tenha política de privacidade, permita exclusão de dados, obtenha consentimento explícito. Use cookies apenas com opt-in.

> **Dica para o Claude Code:** Ao iniciar um projeto, peça: *"Implemente autenticação JWT com bcrypt, variáveis de ambiente via .env, rate limiting nos endpoints públicos e validação de input com zod/joi."* O agente configurará tudo automaticamente.

```
Analise o projeto atual e implemente as seguintes medidas de segurança:

1. Autenticação JWT com refresh tokens
2. Hash de senhas com bcrypt (salt rounds: 12)
3. Middleware de rate limiting (100 req/15min por IP)
4. Validação de input com Zod em todas as rotas
5. Sanitização de HTML para prevenir XSS
6. Queries parametrizadas (nunca concatenar SQL)
7. Helmet.js para headers de segurança HTTP
8. CORS configurado apenas para domínios permitidos
9. Arquivo .env.example com todas as variáveis necessárias
10. Middleware de logging para auditoria

Explique cada medida implementada.
```

> **Nunca faça deploy sem:** HTTPS ativo, senhas hasheadas, .env fora do repositório, validação de input em todas as rotas, e rate limiting nos endpoints públicos.
