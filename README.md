# RockWave

**O som não morreu.**

Repositório independente do site RockWave.

## Estrutura

- `index.html` — página principal do site.
- `rockwave-logo.png` — logo original.
- `src/index.js` — Cloudflare Worker que entrega os arquivos do site.
- `wrangler.toml` — configuração do Worker e dos assets.
- `.assetsignore` — impede que arquivos internos de desenvolvimento sejam publicados como assets.

## Publicação no Cloudflare

O workflow em `.github/workflows/deploy-cloudflare.yml` publica o Worker sempre que houver um push para `main`.

Para habilitar a publicação automática, adicione estes dois repositório-secrets em **Settings → Secrets and variables → Actions**:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

Sem esses secrets, o workflow apenas informa que a publicação foi pulada; ele não altera o Worker existente.

## Desenvolvimento local

Com Node.js instalado, execute:

```bash
npx wrangler dev
```

Para publicar manualmente:

```bash
npx wrangler deploy
```
