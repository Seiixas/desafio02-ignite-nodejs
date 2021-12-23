# 🚀 Desafio 01 - Bootcamp Ignite (Rocketseat)
![node-js-badge](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white) ![js-badge](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

## 📙 1. Sobre o desafio
Este desafio consiste na criação de middlewares de controle para uma API de TODOs já disponibilizada pelo template da Rocketseat \m/.

## 🏃 2. Como rodar o desafio
Basta dar um git clone neste repositório, carregar as dependências, executar o comando para iniciar o servidor Node e utilizar algum software como Insomnia ou Postman para as requisições
```
git clone https://github.com/Seiixas/desafio02-ignite-nodejs.git
cd desafio01-ignite-nodejs
yarn
yarn dev
```

## ⚙️ 3. Funcionalidades
### 😃 3.1. Criar uma conta para o usuário.
Utilizando a rota `localhost:3333/users` é possível criar um novo usuário passando pelo corpo da requisição os parâmetros: 
```json
{
    "name": "Mateus Silva Seixas",
    "username": "devSeixas"
}
```
Não é possível criar usuários com o mesmo username.

### 📜 3.2. Listar todos os TODOs de um usuário
Utilizando a rota `localhost:3333/todos` no método GET, é possível listar todos os TODOs de um usuário enviando o seu username pelo header da requisição.

### 🆕 3.3. Criar um novo TODO para o usuário
Utilizando a rota `localhost:3333/todos` no método POST, é possível criar um novo TODO para o usuário enviando o seu username pelo header e os seguintes parâmetros pelo corpo da requisição: 
```json
{
    "title": "Buscar o carro do mecânico",
    "deadline": "2021-12-22"
}
```
### 📝 3.4. Editar um TODO existente do usuário
Utilizando a rota `localhost:3333/todos/:id` no método PUT, é possível alterar um novo TODO para o usuário enviando o seu username pelo header, o ID do TODO a ser editado pelos Route Params e os seguintes parâmetros pelo corpo da requisição: 
```json
{
    "title": "Buscar o carro na concessionária",
    "deadline": "2021-12-30"
}
```

### ✔️ 3.5. Marcar um TODO como feito
Utilizando a rota `localhost:3333/todos/:id` no método PATCH, é possível alterar o status de um todo para feito! É necessário enviar o username pelo header e o ID do TODO pelo Route Params.

### ❌ 3.6. Deletar um TODO existente do usuário
Utilizando a rota `localhost:3333/todos/:id` no método DELETE, é possível deletar um TODO específico. É necessário enviar o username pelo header e o ID do TODO pelo Route Params.

### ⭐ 3.7. Adicionar um plano PRO ao usuário
Utilizando a rota `localhost:3333/:id/pro` no método PATCH, enviando um username pelo header da requisição, é possível habilitar o plano Pro ao usuário que permite a criação de N TODOs que, outrora no plano grátis, era limitado a 10.

## 🔀 4. Middlewares

4.1. `checksExistsUserAccount`: Verifica se a conta do usuário existe baseado em um username enviado por header;

4.2. `checksCreateTodosUserAvailability`: Verifica se o usuário pode criar TODOs baseado em seu plano; Onde o plano gratuito possui uma limitação de 10 TODOs a serem criados, enquanto o plano Pro não possui limitações;

4.3. `checksTodoExists`: Verifica se um TODO existe baseado em um ID enviado por route params;

4.4. `findUserById`: Verifica se a conta do usuário existe baseado em um ID enviado por route params;
