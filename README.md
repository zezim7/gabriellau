# gabriellau.pages.dev

Site pessoal de Gabriel Lau: infraestrutura, monitoramento e suporte técnico.

O site é um único `index.html`, sem frameworks e sem etapa de build. O topo é uma simulação de fluido em WebGL 2 que imita tinta num tinteiro, e as amostras de tinta dos projetos são desenhadas em canvas.

## Rodar localmente

Abra o `index.html` no navegador.

## Publicar no Cloudflare Pages

```
npx wrangler pages deploy . --project-name gabriellau
```

O arquivo `_headers` define os cabeçalhos de segurança: Content-Security-Policy, HSTS, nosniff, Referrer-Policy e Permissions-Policy. A política de script libera só o script embutido no `index.html`, pelo hash SHA-256 dele. Se esse script mudar, gere o hash de novo e atualize o `_headers`, senão o navegador bloqueia o script.
