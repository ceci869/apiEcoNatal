# apiEcoNatal

Este repositório contém o **backend do projeto EcoNatal**, uma API desenvolvida para gerenciar usuários, catadores de materiais recicláveis e mensagens de contato.


## Sobre o Projeto

O **EcoNatal** é um projeto voltado para a sustentabilidade e a reciclagem, com o objetivo de conectar pessoas que possuem materiais recicláveis a catadores cadastrados.

Este backend é responsável por:
- Gerenciar o cadastro de usuários
- Gerenciar o registro de catadores
- Armazenar mensagens enviadas pelo sistema de contato


## Tecnologias Utilizadas

- Node.js  
- Express  
- MongoDB  
- Mongoose  
- Bcrypt  
- Cors  

  
## Endpoints da API

A seguir estão descritas as rotas disponíveis na API e a função de cada uma.

### Cadastro de Usuários  
**Rota:** `/api/cadastro_usuarios`  
**Método:** `POST`

Este endpoint é utilizado para cadastrar usuários comuns no sistema.  

**Campos esperados no corpo da requisição (JSON):**
- `nome` (string): nome completo do usuário  
- `data_nascimento` (date): data de nascimento  
- `email` (string): e-mail do usuário  
- `endereco` (string): endereço completo  
- `senha` (string): senha do usuário  

**Exemplo de requisição:**
```json
{
  "nome": "Cecília Aine",
  "data_nascimento": "1998-05-12",
  "email": "cecilia@email.com",
  "endereco": "Rua Jundiaí, 123 - Natal/RN",
  "senha": "1234567"
}
```
### Registro de Catadores  
**Rota:** `/api/cadastro_catadores`  
**Método:** `POST`

Este endpoint permite o cadastro de catadores de materiais recicláveis.  
O campo `coletas` deve ser uma lista com os tipos de materiais que o catador coleta.

**Campos esperados no corpo da requisição (JSON):**
- `nome` (string): nome do catador  
- `telefone` (string): telefone para contato  
- `email` (string): e-mail do catador  
- `endereco` (string): endereço  
- `coletas` (array de string): materiais recicláveis coletados  

**Exemplo de requisição:**
```json
{
  "nome": "João da Silva",
  "telefone": "84999998888",
  "email": "joao@email.com",
  "endereco": "Avenida Itapetinga, 143 - Natal/RN",
  "coletas": ["papel", "vidro", "plástico"]
}
```

### Mensagens de Contato  

A API possui um modelo responsável por armazenar mensagens enviadas por usuários através do formulário de contato.

**Campos do modelo:**
- `nome` (string): nome de quem enviou a mensagem  
- `email` (string): e-mail para contato  
- `assunto` (string): assunto da mensagem  
- `mensagem` (string): conteúdo da mensagem
