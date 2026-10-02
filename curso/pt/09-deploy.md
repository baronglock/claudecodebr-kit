# Deploy: Do Local para o Mundo

*Produção*

Seu software funciona local. Agora é hora de colocar no ar para usuários reais acessarem.

## Opções de Deploy

| Plataforma | Melhor Para | Custo | Dificuldade |
|---|---|---|---|
| **Vercel** | Frontend, Next.js, sites estáticos | Grátis (hobby, uso pessoal) | Fácil |
| **Railway** | Backend, bancos de dados, full-stack | $5/mês+ | Fácil |
| **AWS (EC2/ECS)** | Projetos de escala, controle total | Variável | Avançado |
| **VPS (Hetzner/DigitalOcean)** | Controle total, custo previsível | $4-20/mês | Médio |

## Docker Básico

Docker empacota seu app com todas as dependências, garantindo que funcione igual em qualquer lugar.

```
# Dockerfile básico para Node.js
FROM node:24-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --omit=dev
COPY . .
EXPOSE 3000
CMD ["node", "dist/index.js"]

# Comandos essenciais:
# docker build -t meu-app .
# docker run -p 3000:3000 meu-app
```

## CI/CD com GitHub Actions

Automatize testes e deploy a cada push. O código vai para produção automaticamente quando os testes passam.

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
      # Adicione o step de deploy da sua plataforma aqui
```

### Domínio + SSL

Registre um domínio (Namecheap, Cloudflare). Aponte o DNS para sua plataforma de deploy. SSL é automático na maioria das plataformas modernas.

### Monitoramento

Use **UptimeRobot** (grátis) para alertas de downtime. **Sentry** para tracking de erros. **Vercel Analytics** ou **Plausible** para métricas de uso.

> **Dica para o Claude Code:** Peça: *"Configure Docker com multi-stage build, GitHub Actions para CI/CD com testes e deploy automático no Railway/Vercel, e adicione health check endpoint."*
