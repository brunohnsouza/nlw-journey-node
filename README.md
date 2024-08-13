# plann.er

O plann.er oferece acesso a recursos para registro, recuperaração, atualização e exclusão de informações de viagens como atividades, links úteis e participantes.

## Índice

- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Endpoints](#endpoints)
- [Licença](#licença)

## Requisitos

- **Fastify**: Framework web rápido e de baixa sobrecarga para Node.js.
- **@fastify/cors**: Plugin para habilitar CORS (Cross-Origin Resource Sharing) no Fastify.
- **@prisma/client**: Cliente Prisma para interagir com o banco de dados.
- **Day.js**: Biblioteca para manipulação de datas.
- **Fastify-type-provider-zod**: Provedor de tipos para Fastify usando a biblioteca Zod.
- **Nodemailer**: Módulo para enviar e-mails com Node.js.
- **Zod**: Biblioteca para validação de esquemas e tipos.

## Instalação

Siga as etapas abaixo para configurar e instalar a API em seu ambiente local:

1. Clone o repositório e acesse o diretório:

```bash
git clone git@github.com:brunohnsouza/nlw-journey-node.git
cd nlw-journey-node
```

2. Instale as dependências do projeto usando o `Node Package Manager (NPM)`:

```bash
npm install
```

3. Inicie o servidor em modo de desenvolvimento:

```bash
npm run dev
```

A API estará acessível em `http://localhost:3333`.

## Endpoints

Principais endpoints da API, com informações sobre seus métodos HTTP, descrição, parâmetros, exemplos de solicitações e exemplos de respostas.

| Endpoint                              | Método | Descrição                                             | Parâmetros                                                                 | Exemplo de Solicitação                                           | Exemplo de Resposta        |
| ------------------------------------- | ------ | ----------------------------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------- | -------------------------- |
| /trips/{tripId}/confirm               | GET    | Confirma a viagem e envia um e-mail aos participantes | tripId                                                                     | GET /trips/123e4567-e89b-12d3-a456-426614174000/confirm          | Status 204 No Content      |
| /trips                                | POST   | Cria uma nova viagem                                  | destination, starts_at, ends_at, emails_to_invite, owner_name, owner_email | POST /trips                                                      | Status 201 Created         |
| /trips/{tripId}                       | GET    | Obtem detalhes de uma viagem                          | tripId                                                                     | GET /trips/123e4567-e89b-12d3-a456-426614174000                  | Status 200 Ok, [JSON]      |
| /trips/{tripId}                       | PUT    | Atualiza uma viagem                                   | tripId                                                                     | PUT /trips/123e4567-e89b-12d3-a456-426614174000                  | Status 204 No Content      |
| /participants/{participantId}/confirm | PATCH  | Confirma um participante na viagem                    | participantId                                                              | PATCH /participants/123e4567-e89b-12d3-a456-426614174000/confirm | Status 204 No Content      |
| /trips/{tripId}/invites               | POST   | Convida alguém para a viagem                          | tripId                                                                     | POST /trips/123e4567-e89b-12d3-a456-426614174000/invites         | Status 201 Created         |
| /trips/{tripId}/participants          | GET    | Obtem todos os participantes de uma viagem            | tripId                                                                     | POST /trips/123e4567-e89b-12d3-a456-426614174000/participants    | Status 200 Ok, [JSON]      |
| /trips/{tripId}/activities            | POST   | Cria uma atividade de viagem                          | tripId                                                                     | POST /trips/123e4567-e89b-12d3-a456-426614174000/activities      | Status 201 Created, [JSON] |
| /trips/{tripId}/activities            | GET    | Obter as atividades de uma viagem                     | tripId                                                                     | GET /trips/123e4567-e89b-12d3-a456-426614174000/activities       | Status 200 Ok, [JSON]      |
| /trips/{tripId}/links                 | GET    | Obter os links úteis de uma viagem                    | tripId                                                                     | GET /trips/123e4567-e89b-12d3-a456-426614174000/links            | Status 200 Ok, [JSON]      |
| /trips/{tripId}/links                 | POST   | Criar um link útil                                    | tripId                                                                     | POST /trips/123e4567-e89b-12d3-a456-426614174000/links           | Status 201 Created, [JSON] |

## Licença

[MIT](https://choosealicense.com/licenses/mit/)
