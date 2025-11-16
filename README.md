# 🚀 Azure SmartCost - Beta Landing Page

Landing page para captação de beta testers do Azure SmartCost.

## 📋 Deploy no GitHub Pages

### Passo 1: Criar repositório no GitHub
1. Acesse: https://github.com/new
2. Nome: `smartcost-beta`
3. Descrição: `Landing page beta - Azure SmartCost`
4. Público ou Privado: **Público** (necessário para GitHub Pages grátis)
5. **NÃO** adicionar README, .gitignore ou licença
6. Clique em **Create repository**

### Passo 2: Fazer push do código
Após criar o repositório, execute no PowerShell:

```powershell
cd C:\DIOazure\Azure-SmartCost\marketing\beta-site

# Adicionar remote (SUBSTITUIR 'seu-usuario' pelo seu username GitHub)
git remote add origin https://github.com/seu-usuario/smartcost-beta.git

# Push
git branch -M main
git push -u origin main
```

### Passo 3: Habilitar GitHub Pages
1. No repositório GitHub, vá em **Settings**
2. Menu lateral: **Pages**
3. Source: **Deploy from a branch**
4. Branch: **main** / **/ (root)**
5. Clique em **Save**

⏱️ Aguarde 1-2 minutos para o deploy

### Passo 4: URL da sua landing page
```
https://seu-usuario.github.io/smartcost-beta/
```

---

## ⚙️ Configuração da API

Após deploy, você precisa ajustar a URL da API no código.

**Editar no GitHub:**
1. Abra o arquivo `index.html`
2. Procure por `fetch('/api/beta/signup'` (linha ~350)
3. Alterar para: `fetch('https://smartcost-api-7016.azurewebsites.net/api/beta/signup'`
4. Commit direto no GitHub

**OU atualizar localmente:**
```powershell
# Editar index.html (linha 350)
# Depois:
git add index.html
git commit -m "Update API URL"
git push
```

---

## 🔄 Atualizar conteúdo

Sempre que modificar a landing page:

```powershell
cd C:\DIOazure\Azure-SmartCost\marketing\beta-site
git add .
git commit -m "Descrição da mudança"
git push
```

Deploy automático em 1-2 minutos!

---

## 📊 Métricas

**Google Analytics (opcional):**
Descomentar linhas 548-556 do `index.html` e adicionar seu GA ID.

**Meta Pixel (opcional):**
Adicionar antes do `</head>`:

```html
<!-- Meta Pixel Code -->
<script>
!function(f,b,e,v,n,t,s)
{if(f.fbq)return;n=f.fbq=function(){n.callMethod?
n.callMethod.apply(n,arguments):n.queue.push(arguments)};
if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
n.queue=[];t=b.createElement(e);t.async=!0;
t.src=v;s=b.getElementsByTagName(e)[0];
s.parentNode.insertBefore(t,s)}(window, document,'script',
'https://connect.facebook.net/en_US/fbevents.js');
fbq('init', 'SEU_PIXEL_ID');
fbq('track', 'PageView');
</script>
```

---

## 🎨 Domínio Customizado (opcional)

Se quiser usar `beta.azuresmartcost.com`:

### No seu provedor de domínio:
Adicionar registro CNAME:
```
beta.azuresmartcost.com → seu-usuario.github.io
```

### No GitHub:
1. Settings → Pages
2. Custom domain: `beta.azuresmartcost.com`
3. Save
4. Aguardar validação DNS (até 24h)

---

## ✅ Checklist Pós-Deploy

- [ ] Landing page acessível na URL GitHub Pages
- [ ] Formulário abre sem erros
- [ ] Countdown mostrando data correta (26/11/2025)
- [ ] Testar submissão do formulário
- [ ] Verificar responsivo (mobile)
- [ ] Adicionar URL nos posts de redes sociais
- [ ] Configurar Google Analytics (opcional)

---

## 📞 Suporte

**Problemas comuns:**

**1. Página 404**
- Aguardar 2-3 minutos após habilitar Pages
- Verificar se branch é `main` e pasta é `/ (root)`

**2. CSS não carrega**
- Verificar se `index.html` está na raiz do repo
- Hard refresh: Ctrl+F5

**3. Formulário não submete**
- CORS precisa estar configurado na API
- Verificar URL da API no código

---

**Status:** ✅ Pronto para deploy  
**Próximo:** Criar repo no GitHub e fazer push
