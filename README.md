Rotas da aplicação
Com o template já clonado e o arquivo index.js aberto, você deve completar onde não possui código com o código para atingir os objetivos de cada teste.

GET /repositories
A rota deve retornar uma lista contendo todos os repositórios cadastrados.

POST /repositories
A rota deve receber title, url e techs pelo corpo da requisição e retornar um objeto com as informações do repositório criado e um status 201

PUT /repositories/:id
A rota deve receber title, url e techs pelo corpo da requisição e o id do repositório que deve ser atualizado pelo parâmetro da rota. Deve alterar apenas as informações recebidas pelo corpo da requisição e retornar esse repositório atualizado.

DELETE /repositories/:id
A rota deve receber, pelo parâmetro da rota, o `id` do repositório que deve ser excluído e retornar um status `204` após a exclusão.

POST /repositories/:id/like
A rota deve receber, pelo parâmetro da rota, o id do repositório que deve receber o like e retornar o repositório com a quantidade de likes atualizada.


Testes
- Should be able to create a new repository
Para que esse teste passe, você deve permitir que um novo repositório seja cadastrado pela rota POST /repositories. Caso precise confirmar o formato do objeto, você pode olhar aqui.
Também é necessário que você retorne a resposta com o código 201.

- Should be able to list the projects
Para que esse teste passe, é necessário que você conclua o teste anterior. Se tudo ocorreu bem, os repositórios cadastrados deverão aparecerem na listagem da rota GET /repositories e esse teste irá passar

- Should be able to update repository
Para que esse teste passe, você deve permitir que um repositório seja atualizado a partir de seu id pela rota PUT /repositories/:id usando as informações recebidas pelo corpo da requisição. Lembre-se de manter as informações que não foram passadas pelo corpo, por exemplo:
Se o usuário quiser trocar apenas o title, mantenha url e techs que já estavam no repositório

- Should not be able to update a non existing repository
Para que esse teste passe, você deve verificar se o repositório existe antes de atualizar as informações na rota PUT /repositories/:id. Caso não exista, retorne um status 404 (que é o status para Not Found) com uma mensagem de erro no formato { error: "Mensagem do erro" }

- Should not be able to update repository likes manually
Para que esse teste passe, você deve impedir que a quantidade de likes de um repositório seja alterada manualmente através da rota PUT /repositories/:id.

- Should be able to delete the repository
Para que esse teste passe, você deve permitir que um repositório seja excluído através do id passado pela rota DELETE /repositories/:id

- Should not be able to delete a non existing repository
Para que esse teste passe, você deve validar se o repositório existe antes de excluí-lo. Caso o repositório não exista, retorne um status 404 com uma mensagem de erro no formato { error: "Mensagem do erro" }

- Should be able to give a like to the repository
Para que esse teste passe, deve ser possível incrementar a quantidade de likes em 1 a cada chamada na rota POST /repositories/:id/like. Use o id passado por parâmetro na rota para realizar essa ação.

- Should not be able to give a like to a non existing repository
Para que esse teste passe, você deve validar que um repositório existe antes de incrementar a quantidade de likes. Caso não exista, retorne um status 404 com uma mensagem de erro no formato { error: "Mensagem do erro" }