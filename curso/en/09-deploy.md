# Deploy: From Local to the World

*Production*

Your software works locally. Now it is time to put it online for real users to access.

## Deploy Options

| Platform | Best For | Cost | Difficulty |
|---|---|---|---|
| **Vercel** | Frontend, Next.js, static sites | Free (hobby, personal use) | Easy |
| **Railway** | Backend, databases, full-stack | $5/month+ | Easy |
| **AWS (EC2/ECS)** | Projects at scale, full control | Variable | Advanced |
| **VPS (Hetzner/DigitalOcean)** | Full control, predictable cost | $4-20/month | Medium |

## Docker Basics

Docker packages your app with all its dependencies, ensuring it works the same anywhere.

```
# Basic Dockerfile for Node.js
FROM node:24-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --omit=dev
COPY . .
EXPOSE 3000
CMD ["node", "dist/index.js"]

# Essential commands:
# docker build -t meu-app .
# docker run -p 3000:3000 meu-app
```

## CI/CD with GitHub Actions

Automate tests and deploy on every push. The code goes to production automatically when the tests pass.

```
# .github/workflows/deploy.yml
name: Deploy
on:
  push:
    branches: [main]

jobs:
  test-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v7
      - uses: actions/setup-node@v7
        with:
          node-version: 24
      - run: npm ci
      - run: npm test
      - run: npm run build
      # Add your platform's deploy step here
```

### Domain + SSL

Register a domain (Namecheap, Cloudflare). Point the DNS to your deploy platform. SSL is automatic on most modern platforms.

### Monitoring

Use **UptimeRobot** (free) for downtime alerts. **Sentry** for error tracking. **Vercel Analytics** or **Plausible** for usage metrics.

> **Tip for Claude Code:** Ask: *"Set up Docker with a multi-stage build, GitHub Actions for CI/CD with tests and automatic deploy to Railway/Vercel, and add a health check endpoint."*
