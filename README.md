# Achados & Perdidos Angola

Um site simples para registar e procurar objetos perdidos/encontrados em Angola.

## 🚀 Como usar
1. Cria um projeto no [Firebase Console](https://console.firebase.google.com).
2. Ativa:
   - Firestore Database
   - Storage
3. Vai em *Configurações do projeto → SDK Web* e copia as credenciais.
4. Cola no ficheiro `firebase-config.js`.

## 📦 Deploy no Vercel
1. Cria um repositório no GitHub com os ficheiros deste projeto.
2. Vai em [Vercel](https://vercel.com), cria conta e importa o repositório.
3. O site ficará online com domínio gratuito `https://teu-projeto.vercel.app`.

## 🔒 Segurança
- Inicialmente podes usar regras abertas (`allow read, write: if true`).
- Depois, restringe escrita a utilizadores autenticados ou adiciona moderação.
