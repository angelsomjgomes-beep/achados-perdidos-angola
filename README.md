# 🌍 Achados & Perdidos Angola

Plataforma web moderna para ajudar pessoas em Angola a reencontrar objetos perdidos ou encontrados.
Desenvolvida com **HTML + TailwindCSS + Firebase + Cloudinary + SweetAlert2**, com suporte a **login Google e telefone**.

---

## 🚀 Funcionalidades

* 🧾 Publicar itens perdidos/encontrados com foto
* 📰 Feed dinâmico e filtrável
* 🔐 Login com **Google** e **telefone (SMS)**
* 🧊 Design navy moderno e responsivo
* ☁️ Upload de imagens via **Cloudinary**
* 💬 Alertas visuais via **SweetAlert2**

---

## 📁 Estrutura do Projeto

```
/ (raiz)
├── index.html           # Página inicial
├── feed.html            # Listagem de itens (Feed)
├── publicar.html        # Publicação de novos itens
├── login.html           # Página de login
├── firebase-config.js   # Configuração Firebase (coloca o teu)
├── README.md            # Este guia completo
```

---

## 🧠 1. Configurar Firebase

### 🔹 Criar o projeto

1. Vai a [Firebase Console](https://console.firebase.google.com/)
2. Clica **“Adicionar projeto”** → dá um nome (ex: *achados-perdidos-angola*)
3. Após criar, entra no painel.

---

### 🔹 Ativar Firestore

1. No menu esquerdo, clica **Build → Firestore Database**
2. Cria uma base de dados em modo **Start in test mode**
3. Cria uma **coleção** chamada:

   ```
   items
   ```
4. Campos recomendados (criam-se automaticamente no `publicar.html`):

   * `titulo` (string)
   * `descricao` (string)
   * `categoria` (string)
   * `tipo` (string)
   * `contacto` (string)
   * `fotoURL` (string)
   * `created_at` (timestamp)

---

### 🔹 Ativar Authentication

1. Vai em **Build → Authentication → Sign-in Method**
2. Ativa:

   * ✅ **Google**
   * ✅ **Telefone (SMS)**

> ⚠️ Para Telefone, podes usar **número de teste** (sem precisar de VISA):
>
> * Número: `+244911111111`
> * Código: `123456`

---

### 🔹 Adicionar domínios autorizados

Para evitar erro `auth/unauthorized-domain`:

1. Vai em **Authentication → Settings (⚙️ ícone)**
2. Em **Authorized domains**, adiciona:

   ```
   localhost
   vercel.app
   teu-nome.vercel.app
   ```
3. Clica **Save**

---

### 🔹 Criar o ficheiro `firebase-config.js`

Na mesma pasta dos HTMLs, cria o ficheiro:

```js
export const firebaseConfig = {
  apiKey: "TUA_API_KEY",
  authDomain: "TEU_PROJETO.firebaseapp.com",
  projectId: "TEU_PROJETO",
  storageBucket: "TEU_PROJETO.appspot.com",
  messagingSenderId: "1234567890",
  appId: "1:1234567890:web:abc123xyz"
};
```

> ⚠️ **Importante:** Não uses `const firebaseConfig = {}` sem `export`.
> O `export` é necessário para os `import` funcionarem nos scripts.

---

## ☁️ 2. Configurar Cloudinary (Upload de Imagens)

### 🔹 Criar conta gratuita

1. Acede a [Cloudinary](https://cloudinary.com/)
2. Cria uma conta gratuita.
3. No dashboard, verás o teu:

   * **Cloud name**
   * **API Key**
   * **API Secret**

### 🔹 Criar um “upload preset”

1. No painel Cloudinary, vai a **Settings → Upload → Upload presets**
2. Clica em **Add upload preset**
3. Define:

   * **Nome:** `ml_default`
   * **Signing Mode:** *Unsigned*
   * **Upload folder (opcional):** `achados-perdidos`
4. Guarda as alterações.

### 🔹 Atualizar o `publicar.html`

Verifica no script que tens:

```js
const cloudName = 'dyylw9hjm';
const uploadPreset = 'ml_default';
```

Substitui pelo teu `cloudName` e `uploadPreset`.

---

## 🔑 3. Testar o Login Localmente

1. Abre `login.html` no navegador
2. Testa **Google Login**:

   * Se aparecer popup e autenticar → ✅ Sucesso
3. Testa **Telefone Login**:

   * Usa número e código de teste (`+244911111111` / `123456`)

---

## 🌍 4. Publicar no Vercel

1. Cria conta em [Vercel](https://vercel.com/)
2. Liga ao teu repositório GitHub
3. Clica em **Deploy**
4. Depois, adiciona o domínio Vercel em **Firebase → Authentication → Authorized domains**

---

## 💬 5. Mensagens e comportamento

* Após login → redireciona automaticamente para `feed.html`.
* Se já estiver logado → mostra alerta *“Sessão ativa”*.
* Se `firebase-config.js` estiver errado → alerta no ecrã inicial.
* Se o utilizador tentar publicar sem login → popup pedindo login.

---

## ✅ 6. Resultado Final Esperado

| Função                      | Estado       |
| --------------------------- | ------------ |
| Login Google                | ✅ Funciona   |
| Login Telefone (teste)      | ✅ Funciona   |
| Upload Cloudinary           | ✅ Funciona   |
| Firestore (guardar itens)   | ✅ Funciona   |
| Feed com filtros e pesquisa | ✅ Funciona   |
| Vercel Deploy               | ✅ Automático |

---

## 💡 Sugestões Futuras

* 🔔 Notificações push para novos itens
* 🧭 Localização aproximada de onde foi encontrado o item
* 🧑‍💻 Painel administrativo (gestão e denúncias)
* 📱 Versão PWA (instalável no telemóvel)
* 💾 Cache offline para acesso sem internet

---

Feito com ❤️ por **R Wizard & [teu nome]** — Angola, 2025.
🌐 [Desenvolvido com Firebase + Cloudinary + Vercel]
