 # 🖥️ Trabalhando com Middlewares - Ignite - Rocketseat

Esse é o Desafio 02 da trilha de NodeJS do Ignite da Rocketseat. 

Esse desafio consiste na aplicação de middlewares para o [Desafio 1](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs)

https://www.notion.so/Desafio-02-Trabalhando-com-middlewares-4f89bf538c2e4ee291382b92bdc36790

## 🧑‍💻 Tecnologias utilizadas

- [NodeJS](https://nodejs.org/en/)
- [Express](https://expressjs.com/pt-br/)
- [Insomnia](https://insomnia.rest/)

## 📌 Index

- [Instalando as ferramentas](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#-instalando-as-ferramentas)
  - [Instalando o NodeJS](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#instalando-o-nodejs)
  - [Instalando o Yarn](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#instalando-o-yarn)
  - [Instalando o Insomnia](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#instalando-o-insomnia)
- [Executando o Projeto](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#-executando-o-projeto)
- [Inicializando o Projeto](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#-inicializando-o-projeto)
- [Middlewares](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#middlewares)
- [Requisitos da Aplicação](https://github.com/GabrielFerreira98/ignite-trabalhando-com-middlewares#requisitos-da-aplica%C3%A7%C3%A3o)
  

## 🧰 Instalando as Ferramentas 

Os passos desse tópico foram realizados no sistema operacional do Windows.

### Instalando o NodeJS

É possível fazer o download pelo [Site oficial do NodeJS](https://nodejs.org/en/download/)

Após o download, abra o Windos PowerShell no modo administrador e digite a seguinte linha de código para ver se o Node foi instalado corretamente:

```
node -v
```

### Instalando o Yarn

O Yarn é o gerenciador de pacotes que será utilizado para baixar todas as dependências e executar o projeto. Caso você deseje fazer com o NPM, pode pular esta etapa.
Há duas possibilidades de baixar o Yarn

1. Pelo site oficial do [Yarn](https://yarnpkg.com/)
2. Rodar o seguinte comando no terminal:
```
npm install -g yarn
```

### Instalando o Insomnia

Pode ser baixado pelo próprio site do [Insomnia](https://insomnia.rest/download)

## 🚀 Executando o projeto

Faça o clone do projeto no Powershell 

```
#faça o clone do projeto
git clone 

#entre na pasta baixada
cd ignite-trabalhando-com-middlewares
```

### Abrindo o projeto

Abra o projeto utilizando alguma IDE. Esse projeto foi feito utilizando o [VSCode](https://code.visualstudio.com/)

### Instalando as dependências

Instale as dependências do projeto utilizando a seguinte linha de comando:

```
yarn install
```

## 🏃 Inicializando o projeto

Rode a linha de comando

```
yarn run dev
```

Mantenha o terminal rodando para utilizar o projeto

## ☄️ Middlewares

#### checksExistsUserAccount

Esse middleware é responsável por receber o username do usuário pelo header e validar se existe ou não um usuário com o username passado. Caso exista, o usuário deve ser repassado para o request e a função next deve ser chamada.

#### checksCreateTodosUserAvailability

Esse middleware deve receber o usuário já dentro do request e chamar a função next apenas se esse usuário ainda estiver no plano grátis e ainda não possuir 10 todos cadastrados ou se ele já estiver com o plano Pro ativado. 

#### checksTodoExists

Esse middleware deve receber o **username** de dentro do header e o **id** de um *todo* de dentro de `request.params`. Você deve validar o usuário, validar que o `id` seja um uuid e também validar que esse `id` pertence a um *todo* do usuário informado.
Com todas as validações passando, o *todo* encontrado deve ser passado para o `request` assim como o usuário encontrado também e a função next deve ser chamada.

#### findUserById

Esse middleware possui um funcionamento semelhante ao middleware checksExistsUserAccount mas a busca pelo usuário deve ser feita através do id de um usuário passado por parâmetro na rota. Caso o usuário tenha sido encontrado, o mesmo deve ser repassado para dentro do request.user e a função next deve ser chamada.

## ✔️ Requisitos da Aplicação

1. Deve ser possível encontrar o user através do username no request headers e passá-lo para o request.user
2. Não deve ser possível achar um user não existente a partir de um username no request headers
3. Deve ser possível deixar o user criar um novo to-do quando ele possui o plano free e tem menos de 10 to-do's
4. Não deve ser possível deixar o usuário criar um novo to-do quando ele não tem o plano pro e já possui 10 to-do's
5. Deve ser possível deixar o usuário criar infinitos to-do's quando ele possui o plano pro
6. Deve ser possível atualizar o user e o todo quando ambos existirem
7. Não deve ser possível atualizar o user e o todo quando o user não existe
8. Não deve ser possível atualizar o user e o todo quando o todo.id não é um uuid
9. Não deve ser possível atualizar o user e o todo quando o to-do não existe
10. Deve ser possível achar o usuário pelo route params - id - e passá-lo para o request.user
11. Não deve ser possível passar o user para o request.user quando o user não existe
