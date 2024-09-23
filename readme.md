
# In.Orbit (API)

A API do In.Orbit é responsável por gerenciar a criação, atualização e monitoramento de metas semanais.

## Sumário

1. [Funcionalidades](#funcionalidades)
    - [Criação de Metas](#criação-de-metas)
    - [Atualização de Metas](#atualização-de-metas)
    - [Listagem de Metas](#listagem-de-metas)
    - [Progresso Semanal](#progresso-semanal)
    - [Banco de Dados](#banco-de-dados)

## Funcionalidades
- ### Criação de Metas
    Permite que o usuário crie novas metas semanais, armazenando-as no banco de dados.
---
- ### Atualização de Metas
    Os usuários podem marcar metas como concluídas, atualizando o status no banco de dados.
---
- ### Listagem de Metas
    A API recupera as metas criadas e organiza-as por dia da semana, permitindo que o front-end exiba o progresso semanal.
---
- ### Progresso Semanal
    A API calcula a porcentagem de metas concluídas e as metas pendentes, retornando essa informação ao front-end para que seja exibida aos usuários.
---
- ### Banco de Dados
    Utiliza Docker e Postman para interagir com o banco de dados e gerenciar as informações relacionadas às metas dos usuários.
---

## Instalação e Execução

#### Observações

- Certifique-se de ter o Node.js e o Docker instalados em sua máquina..
- Execute os comandos a seguir na pasta do projeto utilizando o cmd (Windowns), terminal(Linux) e terminal(macOS). Ou utilizando o terminal de sua IDE.

#### Comandos
    
1.  Instale as dependências, inicie o servidor de desenvolvimento e crie o container no docker e as tabelas no banco de dados
    ```bash 
    npm i
    npm run dev
    
    docker-compose up -d
    npx drizzle-kit generate
    npx drizzle-kit migrate
    ```
2.  Caso queira adicionar registro no banco para teste, execute esse comando.
    ```bash 
    npm run dev
    ```

        
## Referência

 - [NLW Pocket  Avançado - Rocketseat](https://app.rocketseat.com.br/classroom/nlw-17-pocket-intermediario)



## Documentação da API

#### Criar Meta

```http
  POST /goals
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `title` | `string` | **Obrigatório**. O título da meta. |
| `desiredWeeklyFrequency` | `number` | **Obrigatório**. Frequência semanal (1 a 7). |
| `api_key` | `string` | **Obrigatório**. Chave da API.. |


---
#### Marcar Meta como Concluída

```http
  POST /completion
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `goalId` | `string` | **Obrigatório**. O ID da meta. |
| `desiredWeeklyFrequency` | `string` | **Obrigatório**. Chave da API. |

---
#### Obter Meta Pendentes da Semana

```http
  GET /pending-goals
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `api_key` | `string` | **Obrigatório**. Chave da API. |

---

#### Obter Resumo da Semana

```http
  GET /pending-goals
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `api_key` | `string` | **Obrigatório**. Chave da API. |

---




## Contribuições
- Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.
