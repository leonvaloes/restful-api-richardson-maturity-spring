# restful-api-richardson-maturity-spring
Implementação de uma API RESTful usando Spring Boot, aderindo ao modelo de maturidade de Richardson para boas práticas de design de APIs. Inclui configuração Docker para o banco de dados PostgreSQL.

# Configuração do Banco de Dados PostgreSQL para a API de Produtos

Este repositório contém uma API RESTful desenvolvida com Spring Boot, e para facilitar a configuração do ambiente, recomendamos o uso do Docker para criar um banco de dados PostgreSQL.

## Pré-requisitos
- Docker instalado no seu sistema ([Instruções de instalação do Docker](https://docs.docker.com/get-docker/))

## Criando um Banco de Dados PostgreSQL via Docker

1. Abra o terminal no seu sistema.

2. Execute o seguinte comando para baixar e iniciar uma instância do PostgreSQL em um contêiner Docker:

    ```bash
    docker run --name postgres-products-api -e POSTGRES_PASSWORD=suaSenhaAqui -p 5432:5432 -d postgres
    ```

   Certifique-se de substituir "suaSenhaAqui" pela senha desejada para o usuário padrão "postgres". Esse comando cria um contêiner chamado "postgres-products-api" e expõe a porta 5432 do PostgreSQL.

3. Aguarde até que o contêiner seja iniciado. Você pode verificar o status do contêiner com o comando:

    ```bash
    docker ps
    ```

   Certifique-se de ver o contêiner "postgres-products-api" na lista.

4. Crie um banco de dados chamado "products-api". Execute o seguinte comando:

    ```bash
    docker exec -it postgres-products-api psql -U postgres -c "CREATE DATABASE products_api;"
    ```

   Isso cria o banco de dados necessário para a API de Produtos.

## Finalizando

Agora você configurou com sucesso um banco de dados PostgreSQL para a API de Produtos. Certifique-se de configurar suas propriedades de conexão no projeto Spring Boot de acordo com as credenciais fornecidas durante a criação do contêiner.

Lembre-se de que essas são instruções básicas, e você pode precisar ajustar conforme necessário para atender aos requisitos específicos do seu projeto.
