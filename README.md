# Site estático — Formulário EPIs (Netlify)

Páginas públicas da extensão Chrome **CBMMG - Formulário EPIs (LOIQ)**:

| Rota | Arquivo |
|------|---------|
| `/` | `public/index.html` |
| `/privacidade` | `public/privacidade/index.html` |

A API e o painel admin continuam em `https://giscad.bombeiros.mg.gov.br`.

## Estrutura

```
netlify/
├── netlify.toml          # publish + headers + redirects
├── README.md
└── public/               # pasta publicada
    ├── index.html
    ├── _redirects
    ├── privacidade/
    │   └── index.html
    └── assets/
        └── icons/        # ícones da extensão
```

## Deploy no Netlify

1. Conecte o repositório Git ao Netlify.
2. Configure o site:
   - **Base directory:** `netlify`
   - **Publish directory:** `public` (já vem no `netlify.toml`)
   - **Build command:** deixe vazio ou use o do `netlify.toml`
3. Publique. A política de privacidade ficará em:
   `https://SEU-DOMINIO.netlify.app/privacidade`
4. (Opcional) Aponte um domínio customizado e use essa URL na Chrome Web Store.

## Pré-visualização local

Qualquer servidor estático na pasta `public`:

```bash
cd netlify/public
python3 -m http.server 5500
```

Abra `http://localhost:5500` e `http://localhost:5500/privacidade/`.

## Após o deploy

Atualize na Chrome Web Store o campo **Privacy policy** com a URL Netlify de `/privacidade`.
