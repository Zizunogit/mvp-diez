# Diez.bet · protótipo navegável (v4)

Protótipo do site da **Diez.bet** — apostas esportivas e cassino para a Argentina (es-AR, voseo) — construído pelo squad (Design, UX, UI, UX Writer e Dev) e aprovado rodada a rodada na Mesa de Decisões. Versão **v4**, exportada em 26/10/2026.

Site estático: HTML, CSS e JavaScript puros, sem dependências, sem build e sem chamadas externas. Esta é a versão **compacta para o GitHub**: 98 arquivos no total, com o mesmo visual e o mesmo comportamento do protótipo publicado.

## Estrutura

```
index.html      casca da página e ícones (sprite SVG)
css/site.css    todos os estilos numa folha só (com a fonte Tektur embutida)
js/site.js      todo o JavaScript num arquivo só (estado, rotas, telas, login; logos de provedores embutidos)
img/            só as imagens que o site usa · c/ personagens · cm/ personagens em versão leve para celular
                · g/ capas de jogos · s/ cenas 1280 px · t/ cenas 640 px
```

As telas usam rotas com `#` (`#inicio`, `#casino`, `#deportes`, `#evento:e1`, `#deposito`, `#retiro`, `#billetera`, `#perfil`, `#limites`…), então funcionam em qualquer servidor estático, inclusive numa subpasta, sem configuração extra.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub, abra *Add file › Upload files* e arraste **o conteúdo desta pasta** (o `index.html`, o `README.md` e as pastas `css`, `js` e `img`) para a raiz. São 98 arquivos, dentro do limite de 100 por envio do site. Confirme com *Commit changes*.
   - O `.nojekyll` começa com ponto e pode ficar oculto no seu computador; ele não é obrigatório para este site.
   - Pelo git também funciona: `git init -b main`, `git add .`, `git commit -m "Diez.bet v4"`, `git remote add origin https://github.com/<usuário-ou-organização>/<repositório>.git`, `git push -u origin main`.
2. No repositório: *Settings › Pages › Build and deployment › Source: Deploy from a branch*, branch `main`, pasta `/ (root)`, *Save*.
3. Em alguns minutos o site fica em `https://<usuário-ou-organização>.github.io/<repositório>/`.

A página tem `noindex` para não aparecer em buscadores.

## Rodar no computador

```bash
python3 -m http.server 8080
# abra http://localhost:8080
```

**Entrar na demo:** no painel de login, qualquer correo válido + qualquer contraseña entra (a contraseña `incorrecta` simula erro). No cadastro, `existe@correo.com` simula conta já existente e o código `000000` simula código errado.

## Antes de tornar público

- O site do GitHub Pages pode ficar aberto para qualquer pessoa com o link, dependendo do plano e da visibilidade do repositório. Confira isso antes de publicar um protótipo de cliente.
- É um protótipo: saldos, apostas, cuotas, prêmios e movimentos são de exemplo e nada é enviado a servidor algum (o estado fica no `sessionStorage`/`localStorage` do navegador).
- Dados legais e de negócio ainda indefinidos aparecem como `[… — por confirmar]` (razão social, licença, organismo provincial, linha de ajuda, prazos).
- Os logos de provedores (embutidos em `js/site.js`) são marcas de terceiros; o uso em produção depende de autorização.
