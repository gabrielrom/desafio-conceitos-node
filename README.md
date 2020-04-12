# criação de uma API REST
Essa api faz parte de um desafio do curso GoStack 11, ela tem como objetivo passar os conhecimentos mais básicos de uma API REST,a api nao tem integração com bancos de dados,a api foi feita com o express com as seguintes funcionalidades:
  - **Listar os repositórios**
  - **Criar um novo repositório**
  - **Atualizar um repositório**
  - **Deletar um repositório**
  - **Dar Like em um repositório existente**
# Iniciando a API
Antes de tudo temos que executar alguns comandos basicos:
```
git clone https://github.com/gabrielrom/desafio-conceitos-node.git
```

```
yarn (Comando para baixar todos os pacotes utilizados na API)
yarn dev (Comando que inicia o servidor)
```
Feito isso a api agora está rodando na porta 3333. A url vai ser algo parecido com essa:  
```
http://localhost:3333/
```
# Rotas
  - **/repositories**: Essa rota é do tipo **GET**, ela tem a funcionalidade de retornar um array com todos os repositórios cadastrados.
      ```
      Exemplo de retorno:
      [
        {
          id: '136c5191-998b-48ec-a669-3ead30ad8035',
          title: 'Repositorio NodeJS', 
          url: 'https://github.com/gabrielrom/desafio-conceitos-node', 
          techs: ['React', 'ReactNative', 'ReactJS']
        }
      ]
      ```
  - **/repositories**: Essa rota é do tipo **POST**, ela tem a funcionalidade de criar um novo repositório, a rota recebe no body um **JSON** que recebe os seguintes dados:
      ```
      title (Titulo do repositório, tem que ser uma string)
      url (Uma url do repositório, espera um valor em string)
      techs (As técnologias que esse repositorio estar usando, espera como valor um array de strings) 
      ```
      ```
      Essa rota retorna um array com o repositório criado com as seguintes informações:
      
      {
        id (id do repositório)
        title (titulo do repositório)
        url (url do repositório)
        techs (tecnologias do repositório)
      }
      ```
      
  - **/repositories/:id**: Essa rota é do tipo **PUT**, ela tem como objetivo atualizar um repositório existente, a rota recebe o **ID** do repositório como um **Route param**, e ela recebe também no corpo da requisição um **JSON** que tem os seguintes dados:
     ``` 
     title (titulo do repositório)
     url (url do repositório)
     techs (tecnologias do repositório)
     ```
     
     ```
     Essa rota retorna um array com os dados do repositório atualizado. 
     ```
 - **/repositories/:id**: Essa rota é do tipo **DELETE**, como o proprio metodo sugere ela tem como objetivo deletar um repositório,a rota recebe o **ID** do repositório como um **Route param**. Ela retorna um conteudo vazio.
 
 - **/repositories/:id/like**: Essa rota é do tipo **POST**, ela tem como objetivo dar like em um repositório existente,a rota não recebe um corpo.
 
