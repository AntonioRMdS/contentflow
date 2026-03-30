# 📱 Como hospedar o ContentFlow no GitHub Pages

## Guia completo passo a passo (mesmo se você nunca usou GitHub)

---

## PARTE 1 — Preparar o computador (só precisa fazer uma vez)

### Passo 1: Criar conta no GitHub
1. Acesse **https://github.com**
2. Clique em **Sign up**
3. Preencha email, senha e nome de usuário
4. Confirme o email recebido

### Passo 2: Instalar o Git
- **Windows**: Baixe em https://git-scm.com/download/win e instale (Next, Next, Next...)
- **Mac**: Abra o Terminal e digite `git --version` (ele instala sozinho)
- **Linux**: `sudo apt install git`

### Passo 3: Instalar o Node.js
1. Acesse **https://nodejs.org**
2. Baixe a versão **LTS** (botão verde)
3. Instale (Next, Next, Next...)
4. Para conferir, abra o terminal e digite:
   ```
   node --version
   npm --version
   ```
   Se aparecer números tipo `v20.x.x`, está tudo certo.

---

## PARTE 2 — Subir o projeto no GitHub

### Passo 4: Descompactar o projeto
1. Descompacte o arquivo **contentflow-project.zip** em uma pasta no seu computador
2. Você vai ver esta estrutura:
   ```
   contentflow-project/
   ├── .github/workflows/deploy.yml
   ├── public/
   │   ├── manifest.json
   │   ├── icon-192.png
   │   └── icon-512.png
   ├── src/
   │   ├── main.jsx
   │   └── ContentFlow.jsx
   ├── index.html
   ├── package.json
   ├── vite.config.js
   └── .gitignore
   ```

### Passo 5: Criar o repositório no GitHub
1. Acesse **https://github.com/new**
2. Em "Repository name" digite: **contentflow**
3. Marque **Public**
4. **NÃO** marque "Add a README"
5. Clique **Create repository**
6. Vai aparecer uma página com instruções — deixe essa aba aberta

### Passo 6: Subir os arquivos (via terminal)
1. Abra o terminal (CMD, PowerShell, ou Terminal no Mac)
2. Navegue até a pasta do projeto:
   ```bash
   cd caminho/para/contentflow-project
   ```
   Exemplo Windows: `cd C:\Users\SeuNome\Downloads\contentflow-project`
   Exemplo Mac: `cd ~/Downloads/contentflow-project`

3. Execute estes comandos UM POR UM:
   ```bash
   git init
   git add .
   git commit -m "primeiro deploy do ContentFlow"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/contentflow.git
   git push -u origin main
   ```
   ⚠️ Troque **SEU_USUARIO** pelo seu nome de usuário do GitHub!

4. Vai pedir login — use seu usuário e senha do GitHub
   (Se pedir token, veja a PARTE 5 no final)

---

## PARTE 3 — Ativar o GitHub Pages

### Passo 7: Configurar o Pages
1. No GitHub, entre no repositório **contentflow**
2. Clique em **Settings** (aba superior)
3. No menu lateral esquerdo, clique em **Pages**
4. Em **Source**, selecione: **GitHub Actions**
5. Pronto! Não precisa fazer mais nada aqui

### Passo 8: Aguardar o deploy automático
1. Clique na aba **Actions** do repositório
2. Você vai ver o workflow "Deploy to GitHub Pages" rodando
3. Aguarde ficar com ✅ verde (leva 1-3 minutos)
4. Se ficar ❌ vermelho, clique nele para ver o erro

### Passo 9: Acessar o app! 🎉
Seu app estará online em:
```
https://SEU_USUARIO.github.io/contentflow/
```
Abra esse link no celular!

---

## PARTE 4 — Instalar no celular como app

### No Android (Chrome):
1. Abra o link no **Chrome**
2. Toque nos **3 pontinhos** (menu) no canto superior
3. Toque em **"Adicionar à tela inicial"** ou **"Instalar app"**
4. Confirme — um ícone vai aparecer na sua tela inicial
5. Abrindo por esse ícone, o app roda em tela cheia sem barra do navegador!

### No iPhone (Safari):
1. Abra o link no **Safari** (tem que ser Safari, não Chrome)
2. Toque no botão de **compartilhar** (quadrado com seta ↑)
3. Role para baixo e toque em **"Adicionar à Tela de Início"**
4. Toque em **Adicionar**
5. Pronto! O ícone aparece na sua tela inicial

---

## PARTE 5 — Criando Token de acesso (se pedir)

Se na hora do `git push` pedir **token** em vez de senha:

1. No GitHub, clique na sua **foto** (canto superior direito)
2. Vá em **Settings** → **Developer settings** (final da página)
3. Clique em **Personal access tokens** → **Tokens (classic)**
4. Clique em **Generate new token (classic)**
5. Dê um nome (ex: "meu-pc"), marque **repo** e clique **Generate token**
6. **COPIE O TOKEN** (ele aparece só uma vez!)
7. Use esse token como senha na hora do `git push`

---

## Atualizando o app depois

Sempre que quiser alterar algo:
1. Edite os arquivos na pasta do projeto
2. No terminal, na pasta do projeto:
   ```bash
   git add .
   git commit -m "minha atualização"
   git push
   ```
3. O deploy roda automaticamente em 1-3 minutos

---

## Compartilhando com outras pessoas

Basta enviar o link:
```
https://SEU_USUARIO.github.io/contentflow/
```
Qualquer pessoa pode acessar, usar e instalar no celular.
Cada pessoa terá seus próprios dados salvos localmente no navegador.
Use a função de Export CSV/JSON para compartilhar conteúdo entre pessoas!

---

## Dúvidas comuns

**P: Os dados ficam salvos mesmo offline?**
R: Sim! Tudo fica no localStorage do navegador. Funciona offline após o primeiro acesso.

**P: Se eu limpar os dados do navegador, perco tudo?**
R: Sim, por isso use o Export JSON/CSV regularmente como backup.

**P: Funciona em qualquer celular?**
R: Sim, em qualquer navegador moderno (Chrome, Safari, Firefox, Edge).

**P: É de graça?**
R: 100% gratuito. GitHub Pages é gratuito para repositórios públicos.
