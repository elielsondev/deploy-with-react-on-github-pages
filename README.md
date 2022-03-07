# Deploy with React.js on GitHub Pages

Seguindo alguns passos simples, conseguimos fazer o deploy de um projeto React.js no github pages.

### 1º Passo - Crie um projeto React.js.
```
npx create-react-app nome-do-projeto
```
* Obs: Você deve substituir o trecho acima `nome-do-projeto` pelo nome do seu projeto.

### 2º Passo - Crie um repositório no GitHub e conecte com seu projeto. 
* Atenção!!! Neste passo suponho que você como pessoa desenvolvedora saiba cria um repositório no github.
* Caso não saiba acesse <a href="https://docs.github.com/pt/get-started/quickstart/create-a-repo" target="_blank">GitHub Docs</a>


##### Após a criação do repositório você deve fazer os passos seguintes no terminal:
`$  cd nome-do-projeto` <br/>
`$  git init` <br/>
`$  git remote add origin git@github.seu-usuario-github/nome-do-projeto.git` <br/>
* Aqui há alguns pontos de atenção:
 - `seu-usuario-github` deve ser o seu nome de usuário cadastrado no GitHub.
 - `nome-do-projeto` é o nome do seu repositório
 - `git@github.seu-usuario-github/nome-do-projeto.git` estamos usando como exemplo uma chave SSH.

### 3º Passo - Instalar o pacote gh-pages, que é o responsável pelo processo de deploy do nosso projeto:
```
npm add -D gh-pages
```

Após a adição do pacote acima, insira o script no arquivo `package.json` do projeto.
Em seguida altere o item de acordo com o `seu-usuario-github` e o `nome-do-projeto`.

```
"homepage": "https://seu-usuario-github.github.io/nome-do-projeto",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build",
},
```

### 4º Passo - Coloque o seu site no "AR", fazendo o deploy:
`npm run deploy`
* Vale lembrar que pra cada atualização ou alteração no site, deve-se rodar esse comando para que o site também seja atualizado.

### 5º Passo - Acesse seu site agora mesmo:
Acesse: https://seu-usuario-github.github.io/nome-do-projeto
Lembre-se de substituir o `seu-usuario-github` e o `nome-do-projeto`.
* Caso acesse o site e não apareça, não se preocupe, pois o deploy demora um pouco mesmo, tente novamente um tempinho depois.

### 6º Passo - Esse passo só é obrigatório para projetos com rotas:
```
npm i react-router-dom
```
O BrowserRouter deverá ter a seguinte sintaxe:
```
<BrowserRouter basename={process.env.PUBLIC_URL}>

</BrowserRouter>
```
Após alteração `npm run deploy` sempre.

[LinkedIn - Elielson Nascimento](https://www.linkedin.com/in/elielsondev/)<br/>
[GitHub - Elielson Nascimento](https://github.com/elielsondev)
