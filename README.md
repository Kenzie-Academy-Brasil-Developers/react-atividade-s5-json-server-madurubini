# techs-api-madurubini

Esse é o repositório contem uma API simples para estudo, contendo um pouco sobre Requests com o JSON-Server-Auth e o estudo de ENDPOINTS.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login. Foram adicionados mais 6 endpoints, totalizando 11. Sendo eles, 1 que pode ser utilizado para obter todos os usuários cadastrados. 3 para adicionar, deletar e exibir Bibliotecas react para o usuário e 2 para o usuário logado, adicionar e exibir suas Tecnologias.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Users

GET /users<br/>

Este endpoint apenas exibe os usuários cadastrados na plataforma para os usuários logados.
É necessario está logado para acessar esse endpoint.

### Libs

GET /libs<br/>

Este endpoint é responsável por exibir a lista de bibliotecas cadastradas para o usuário logado.
Para fazer a requisição é necessário o token para autenticação.
Apenas usuários logados podem visualizar a lista de bibliotecas cadastradas.

POST/libs<br/>
Este endpoint é responsável por adicionar uma nova Lib no array de Libs.
Para cadastrar uma nova lib na lista temos 2 campos obrigatórios, lib: a biblioteca que você indica e type: para que ela serve.
O usuário precisa estar logado para realizar essa ação.

Ex. lib: Material UI , type: Style

DELETE/libs/${id} <br/>
Este endpoint é responsável por deletar uma lib da lista.
Para fazer a resquisição é necessário estar logado na aplicação e passar o id da lib desejada como parametro na url e assim seguir com a remoção.

### Techs

GET/techs <br/>
Este endpoint é responsável por exibir todas as tecnologias cadastradas dos usuários da aplicação.
Qualquer usuário pode fazer essa requisição.

POST/techs<br/>
Este endpoint é responsável por adicionar uma nova tecnologia no usuário selecionado.
Para fazer a requisição o usuário precisa estar logado e preencher 2 campos na requisição, Tech: Tecnologia de interesse e userId: id do usuário no qual será cadastrada nova tecnologia.
O usuário logado só poderá cadastrar uma nova tecnologia em sua conta.
