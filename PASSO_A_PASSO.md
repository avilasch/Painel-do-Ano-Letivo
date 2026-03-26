# Guia de publicação — Totem CBM como PWA
## EEEM Clovis Borges Miguel

---

## Estrutura de arquivos

Certifique-se de que sua pasta tenha estes arquivos antes de começar:

```
totem-pwa/
├── carrossel_totem.html   ← painel principal
├── manifest.json          ← identidade do app (nome, ícone, cor)
├── sw.js                  ← service worker (cache offline)
├── icons/
│   ├── icon-192.png       ← ícone do app (pequeno)
│   └── icon-512.png       ← ícone do app (grande)
└── midia/                 ← sua pasta com vídeos e imagens
    ├── video1.mp4
    ├── informe1.jpg
    └── ...
```

---

## Passo 1 — Criar uma conta no GitHub

1. Acesse **github.com** e clique em **Sign up**
2. Escolha um nome de usuário (ex: `cbm-vitoria`)
3. Confirme o e-mail

> Se já tiver conta, pule para o Passo 2.

---

## Passo 2 — Criar o repositório

1. Clique no botão **"+"** (canto superior direito) → **New repository**
2. Nome do repositório: `totem-cbm` (ou qualquer nome sem espaços)
3. Deixe marcado como **Public**
4. Clique em **Create repository**

---

## Passo 3 — Enviar os arquivos

### Opção A — Pelo navegador (mais simples)

1. Na página do repositório recém-criado, clique em **"uploading an existing file"**
2. Arraste todos os arquivos da pasta `totem-pwa/` para a área indicada
3. Clique em **Commit changes**

> ⚠️ Atenção: a pasta `midia/` com vídeos e imagens grandes pode
> ultrapassar o limite do GitHub (100MB por arquivo).
> Se isso acontecer, use a Opção B abaixo ou hospede as mídias
> separadamente (Google Drive, etc.).

### Opção B — Pelo Git (para arquivos grandes)

```bash
git clone https://github.com/SEU_USUARIO/totem-cbm.git
cp -r totem-pwa/* totem-cbm/
cd totem-cbm
git add .
git commit -m "Publicação inicial do totem"
git push
```

---

## Passo 4 — Ativar o GitHub Pages

1. No repositório, clique em **Settings** (aba no topo)
2. No menu lateral, clique em **Pages**
3. Em **Source**, selecione: `Deploy from a branch`
4. Em **Branch**, selecione: `main` e pasta `/root`
5. Clique em **Save**

Aguarde 1-2 minutos. Sua URL será:
```
https://SEU_USUARIO.github.io/totem-cbm/carrossel_totem.html
```

---

## Passo 5 — Instalar no tablet como app

1. Abra o **Chrome** no tablet
2. Acesse a URL acima
3. Aguarde carregar completamente (primeira vez precisa de internet)
4. Toque nos **três pontinhos** (⋮) no canto superior direito
5. Toque em **"Adicionar à tela inicial"**
6. Confirme o nome **"Totem CBM"** e toque em **Adicionar**

O app aparecerá na tela inicial do tablet com ícone próprio.
A partir daí, abre em tela cheia sem barra do navegador
e funciona completamente offline. ✅

---

## Passo 6 — Atualizar o app no futuro

Sempre que atualizar o carrossel_totem.html ou outros arquivos:

1. Abra o repositório no GitHub
2. Clique no arquivo → ícone de lápis (editar) ou faça upload do novo arquivo
3. Commit as changes
4. No tablet, abra o app **com internet** uma vez — ele baixará automaticamente a nova versão

> Para forçar a atualização, no Chrome do tablet: Menu → Configurações →
> Privacidade → Limpar dados de navegação → Imagens e arquivos em cache.

---

## Perguntas frequentes

**O app some depois de um tempo?**
Mantenha o tablet conectado à tomada. Android pode "matar" apps em segundo plano.
Use o **Fully Kiosk Browser** se quiser garantia de que o app fica sempre na tela.

**Os vídeos e imagens do carrossel funcionam offline?**
Sim, desde que estejam na pasta `midia/` dentro do repositório (ou no dispositivo).
Arquivos muito grandes (>100MB) precisam ser hospedados separadamente.

**Posso personalizar o ícone?**
Sim. Substitua os arquivos `icons/icon-192.png` e `icons/icon-512.png`
por imagens PNG com o logo da escola e faça o upload novamente.

**O app aparece na Play Store?**
Não — PWAs instaladas pelo Chrome não ficam na Play Store.
Para publicar na Play Store, seria necessário o caminho APK/Android Studio.
Para uso interno na escola, a PWA é suficiente e muito mais simples.
