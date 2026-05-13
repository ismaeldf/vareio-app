# Como publicar o site legal do Vareio

Os 3 arquivos HTML aqui (`index.html`, `privacy.html`, `terms.html`) precisam estar acessíveis numa URL pública HTTPS pra você cadastrar no App Store Connect.

## Opção A — GitHub Pages (gratuito, recomendado)

### 1. Criar repo no GitHub
1. Acesse [github.com/new](https://github.com/new)
2. **Repository name**: `vareio-app`
3. **Description**: `Vareio — Privacy Policy & Terms of Service`
4. **Visibility**: Public (Pages gratuito exige público)
5. NÃO marque "Add README" (já tem)
6. Clique **Create repository**

### 2. Subir arquivos
**Opção 2.1 — Via web (mais fácil)**:
- Na página do repo recém-criado, clique **uploading an existing file**
- Arraste os 4 arquivos desta pasta (`index.html`, `privacy.html`, `terms.html`, `README.md`)
- Commit message: `Initial: legal pages`
- Clique **Commit changes**

**Opção 2.2 — Via terminal**:
```bash
cd /Volumes/Jamal/Projetos/Vareio/legal-site
git init -b main
git add -A
git commit -m "Initial: Vareio legal pages (PT/EN/ES)"
git remote add origin https://github.com/ismaeldf/vareio-app.git
git push -u origin main
```

### 3. Habilitar GitHub Pages
1. No repo, vai em **Settings** → **Pages** (menu lateral)
2. **Source**: Deploy from a branch
3. **Branch**: `main` / `(root)`
4. **Save**
5. Aguarde 1-2 min e a URL fica disponível em:
   - https://ismaeldf.github.io/vareio-app/
   - https://ismaeldf.github.io/vareio-app/privacy.html
   - https://ismaeldf.github.io/vareio-app/terms.html

### 4. Verificar
Abra as URLs no browser. Deve mostrar as páginas com PT/EN/ES.

---

## Opção B — Outro host (Vercel, Netlify, Cloudflare Pages — todos gratuitos)

Funciona igual. Sobe os 3 HTMLs via drag-and-drop. Recebe URL pública. Pula direto pra etapa "Cadastrar URLs" abaixo.

---

## Cadastrar URLs após publicar

### No App Store Connect
1. **My Apps** → Vareio → **App Information**
   - **Privacy Policy URL**: `https://ismaeldf.github.io/vareio-app/privacy.html`
2. **My Apps** → Vareio → **App Privacy** (lateral)
   - Privacy Policy URL: a mesma URL
3. **My Apps** → Vareio → **App Information** → **Localizable Information**
   - **Support URL**: `https://ismaeldf.github.io/vareio-app/` (a home tem email de suporte)
   - **Marketing URL** (opcional): mesma da Support URL ou outra

### No app (Settings → Legal & Sobre)
Me avise a URL final quando estiver no ar — vou adicionar uma nova view `LegalView.swift` no SettingsView com 2 links externos pra Privacy e Terms, além do email de suporte.

---

## Verificação visual

Abre `privacy.html` agora num browser local pra ver o resultado antes de publicar:
```bash
open /Volumes/Jamal/Projetos/Vareio/legal-site/privacy.html
```
