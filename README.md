# ReactRouterComParametrosRota
React Router - Parâmetros de Rota. Projeto com react router e parâmetros de rota, usando react, vite e typescript.  

Vamos criar um projeto com React Router, Vite e TypeScript.  
Aqui está um passo a passo para você começar:  

1. Configurar o projeto.  
Instale o Vite:  
```
npm create vite@latest my-react-app -- --template react-ts
cd my-react-app
```
Instale as dependências necessárias:  
```
> npm install react-router-dom
```
2. Configurar o React Router  
Crie um arquivo routes.tsx na raiz do projeto para definir suas rotas:
```
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Home from './pages/Home';
import About from './pages/About';
import User from './pages/User';
const AppRoutes: React.FC = () => (
  <Router>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
      <Route path="/user/:id" element={<User />} />
    </Routes>
  </Router>
);
export default AppRoutes;
```
Crie os componentes de página (Home.tsx, About.tsx, User.tsx) na pasta pages:  
> Home.tsx:
```
import React from 'react';
const Home: React.FC = () => {
  return <h1>Home Page</h1>;
};
export default Home;
```
> About.tsx:
```
import React from 'react';
const About: React.FC = () => {
  return <h1>About Page</h1>;
};
export default About;
```
> User.tsx:
```
import React from 'react';
import { useParams } from 'react-router-dom';
const User: React.FC = () => {
  const { id } = useParams<{ id: string }>();
  return <h1>User Page: {id}</h1>;
};
export default User;
```
3. Integrar as rotas no aplicativo principal
Modifique o arquivo main.tsx para incluir as rotas:  
```
import React from 'react';
import ReactDOM from 'react-dom';
import AppRoutes from './routes';
import './index.css';
ReactDOM.render(
  <React.StrictMode>
    <AppRoutes />
  </React.StrictMode>,
  document.getElementById('root')
);
```
4. Executar o projeto
Inicie o servidor de desenvolvimento:  
```
npm run dev
```
Para visualizar as rotas no navegador, você pode seguir estes passos:  
Abra o navegador e acesse a URL fornecida pelo Vite, geralmente http://localhost:3000.  
Navegue pelas rotas:  
- Para a página inicial, acesse http://localhost:3000/.
- Para a página "About", acesse http://localhost:3000/about.
- Para a página do usuário com um ID específico, acesse http://localhost:3000/user/1 (substitua 1 pelo ID desejado).

