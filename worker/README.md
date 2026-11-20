# Ran Ma Portfolio AI Worker

This Cloudflare Worker is the server-side bridge between the public GitHub Pages
portfolio and the OpenAI Responses API. The browser never receives the API key.

## Required secret

Create a Worker secret named `OPENAI_API_KEY`. Never commit its value to Git.

Cloudflare Dashboard path:

1. Workers & Pages
2. `ran-ma-ai`
3. Settings
4. Variables and Secrets
5. Add a **Secret** named `OPENAI_API_KEY`
6. Deploy

## Optional variables

- `OPENAI_MODEL`: defaults to `gpt-6-luna`
- `ALLOWED_ORIGIN`: defaults to `https://jessica09222.github.io`

## Deploy from the dashboard

Open the Worker's code editor, replace the default Hello World code with
`index.js`, then deploy.

## Endpoints

- `GET /` returns service health and whether a secret is configured.
- `POST /` accepts `{ "question": "..." }` from the portfolio origin.

The Worker fetches the public `llms.txt` file as its verified knowledge source,
limits question length, applies a basic per-IP request limit, and asks OpenAI not
to store responses.

