# Configurar o login e a sincronização (Firebase, grátis)

Leva uns 10 minutos. Você só faz isso uma vez.

## 1. Criar o projeto
1. Acesse https://console.firebase.google.com e entre com sua conta Google.
2. **Criar um projeto** → nome `showtime` → pode desligar o Google Analytics → **Criar**.

## 2. Ligar o login
1. Menu **Build → Authentication → Vamos começar**.
2. Aba **Sign-in method** e ative:
   - **Google** (escolha seu e-mail de suporte e salve);
   - **E-mail/senha** (opcional).

## 3. Criar o banco de dados
1. Menu **Build → Firestore Database → Criar banco de dados**.
2. Escolha o local `southamerica-east1` (São Paulo) e **modo de produção**.
3. Aba **Regras**, apague tudo e cole isto (cada pessoa só lê e grava os próprios dados):

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid} {
      allow read, write: if request.auth != null && request.auth.uid == uid;
    }
  }
}
```
Clique em **Publicar**.

## 4. Pegar a configuração
1. Na tela inicial do projeto, clique no ícone **</>** (Web) → nome `showtime` → **Registrar app**.
2. Copie o bloco `firebaseConfig` que aparece.
3. Abra o arquivo `firebase-config.js` e troque `window.FIREBASE_CONFIG = null;` por:

```js
window.FIREBASE_CONFIG = {
  apiKey: "...",
  authDomain: "...",
  projectId: "...",
  appId: "..."
};
```
Essa configuração não é segredo: quem protege seus dados são as regras do passo 3.

## 5. Autorizar o endereço do app
Em **Authentication → Settings → Domínios autorizados**, adicione o endereço onde o app roda, por exemplo `seu-usuario.github.io`. O `localhost` já vem autorizado.

## 6. Usar
Abra o app → **Perfil → Conta e sincronização** → entre. Faça o mesmo no celular, com a mesma conta, e a lista será a mesma nos dois.

Na primeira vez que você entra, o app junta o que já existe no aparelho com o que está na nuvem, sem apagar nada.
