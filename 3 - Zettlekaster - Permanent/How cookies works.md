Date: 2025-08-02
Tags: [[security]]

Cookies for authentication basically are random strings that identifies an user in the backend.

Code example:
```ts
import express, { Request, Response } from 'express';

import cookieParser from 'cookie-parser';

  

const app = express();

const PORT = 3000;

  

// Middleware para interpretar JSON e cookies

app.use(express.json());

app.use(cookieParser());

  

// Um "banco de dados" de sessões em memória para simplificar o exemplo

const SESSIONS: Record<string, { userId: string; username: string }> = {};

  

// Rota de Login

app.post('/login', (req: Request, res: Response) => {

  const { username, password } = req.body;

  

  // Em uma aplicação real, você validaria o usuário contra um banco de dados

  if (username === 'admin' && password === 'password') {

    // Crie um ID de sessão único e seguro

    const sessionId = Math.random().toString(36).substring(2);

  

    // Armazene a informação da sessão no servidor

    SESSIONS[sessionId] = { userId: '1', username: 'admin' };

  

    // Defina o cookie no navegador do cliente com flags de segurança

    res.cookie('sessionId', sessionId, {

      // httpOnly: true -> O cookie não pode ser acessado por JavaScript no cliente.

      // Essencial para mitigar ataques de XSS (Cross-Site Scripting).

      httpOnly: true,

  

      // secure: true -> O cookie só será enviado em requisições HTTPS.

      // Previne ataques Man-in-the-Middle (MITM). Use 'false' em desenvolvimento local (HTTP).

      secure: process.env.NODE_ENV === 'production',

  

      // sameSite: 'strict' -> O cookie não será enviado em requisições de sites de terceiros.

      // A proteção mais forte contra ataques de CSRF (Cross-Site Request Forgery).

      // 'lax' é uma alternativa menos restritiva.

      sameSite: 'strict',

  

      // maxAge: Define o tempo de vida do cookie em milissegundos.

      // Ex: 15 minutos. Após isso, o cookie expira.

      maxAge: 15 * 60 * 1000,

    });

  

    return res.status(200).json({ message: 'Login bem-sucedido!' });

  }

  

  return res.status(401).json({ message: 'Credenciais inválidas.' });

});

  

// Rota Protegida

app.get('/perfil', (req: Request, res: Response) => {

  const { sessionId } = req.cookies;

  

  if (!sessionId) {

    return res.status(401).json({ message: 'Acesso não autorizado. Faça o login.' });

  }

  

  const userSession = SESSIONS[sessionId];

  

  if (!userSession) {

    // O cookie existe, mas a sessão não é válida no servidor (expirou ou foi invalidada)

    res.clearCookie('sessionId');

    return res.status(401).json({ message: 'Sessão inválida ou expirada.' });

  }

  

  // Sessão válida, retorne os dados do perfil

  return res.status(200).json({

    message: `Bem-vindo, ${userSession.username}!`,

    user: userSession,

  });

});

  

// Rota de Logout

app.post('/logout', (req: Request, res: Response) => {

  const { sessionId } = req.cookies;

  

  if (sessionId && SESSIONS[sessionId]) {

    // Remove a sessão do nosso "banco de dados"

    delete SESSIONS[sessionId];

  }

  // Instruí o navegador a apagar o cookie

  res.clearCookie('sessionId');

  return res.status(200).json({ message: 'Logout realizado com sucesso.' });

});

  
  

app.listen(PORT, () => {

  console.log(`Servidor rodando em http://localhost:${PORT}`);

  console.log('Ambiente:', process.env.NODE_ENV || 'development');

});
```