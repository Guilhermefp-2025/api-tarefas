API de Gerenciamento de Tarefas
Projeto de desenvolvimento back-end de uma API RESTful para gerenciamento de tarefas. Esta API foi desenvolvida como parte dos requisitos acadêmicos (Trabalho de Desenvolvimento Web Back-end).

A API permite o cadastro, consulta, atualização e remoção de tarefas, seguindo os padrões REST.


Autor: Guilherme Faria de Paula

RU: 368377

Tecnologias Utilizadas
Linguagem: Java 17

Framework: Spring Boot 3

Persistência: Spring Data JPA (Hibernate)

Banco de Dados: MySQL

Build: Maven

Funcionalidades
A API implementa as seguintes operações CRUD (Create, Read, Update, Delete):

[x] Criar uma nova tarefa.

[x] Criar múltiplas tarefas em uma única requisição (em lote).

[x] Listar todas as tarefas cadastradas.

[x] Buscar uma tarefa específica pelo seu ID.

[x] Atualizar os dados de uma tarefa existente.

[x] Remover uma tarefa.

Pré-requisitos para Execução
JDK 17 (ou superior)

Maven 3.x

MySQL Server (rodando na porta padrão 3306)

Postman (ou similar) para testes.

Como Executar o Projeto
Clone o repositório:

git clone https://github.com/SeuUsuario/api-tarefas.git
cd api-tarefas

Crie o Banco de Dados: Conecte-se ao seu MySQL (Workbench, DBeaver, etc.) e execute o comando:
CREATE DATABASE tarefas_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

Configure o application.properties: O arquivo application.properties não é enviado ao repositório por razões de segurança. Você deve criá-lo manualmente:

Vá para a pasta src/main/resources/.

Crie um arquivo chamado application.properties.

Cole o conteúdo abaixo, substituindo [sua_senha] pela senha que você usa no seu MySQL (geralmente root ou a senha que você definiu).
-----------------------------------------------------------------
# Configuração do Banco de Dados MySQL
spring.datasource.url=jdbc:mysql://localhost:3306/tarefas_db
spring.datasource.username=root
spring.datasource.password=[sua_senha]
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# Configurações do Hibernate (JPA)
# 'update': atualiza o schema se necessário, mas mantém os dados.
# (use 'create' para limpar o banco a cada reinicialização)
spring.jpa.hibernate.ddl-auto=update

# Exibe o SQL gerado no console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
-----------------------------------------------------------------------
Execute a Aplicação: Abra um terminal na raiz do projeto (onde está o pom.xml) e execute:
mvn spring-boot:run

Aqui está um README.md completo e profissional para o seu projeto. Você pode copiar e colar este conteúdo em um novo arquivo chamado README.md na pasta raiz do seu projeto (a mesma pasta onde está o pom.xml).

API de Gerenciamento de Tarefas
Projeto de desenvolvimento back-end de uma API RESTful para gerenciamento de tarefas. Esta API foi desenvolvida como parte dos requisitos acadêmicos (Trabalho de Desenvolvimento Web Back-end).

A API permite o cadastro, consulta, atualização e remoção de tarefas, seguindo os padrões REST.

Autor
Autor: Guilherme Faria de Paula

RU: 368377

Tecnologias Utilizadas
Linguagem: Java 17

Framework: Spring Boot 3

Persistência: Spring Data JPA (Hibernate)

Banco de Dados: MySQL

Build: Maven

Funcionalidades
A API implementa as seguintes operações CRUD (Create, Read, Update, Delete):

[x] Criar uma nova tarefa.

[x] Criar múltiplas tarefas em uma única requisição (em lote).

[x] Listar todas as tarefas cadastradas.

[x] Buscar uma tarefa específica pelo seu ID.

[x] Atualizar os dados de uma tarefa existente.

[x] Remover uma tarefa.

Pré-requisitos para Execução
JDK 17 (ou superior)

Maven 3.x

MySQL Server (rodando na porta padrão 3306)

Postman (ou similar) para testes

Como Executar o Projeto
Clone o repositório:

Bash

git clone https://github.com/SeuUsuario/api-tarefas.git
cd api-tarefas
Crie o Banco de Dados: Conecte-se ao seu MySQL (Workbench, DBeaver, etc.) e execute o comando:

SQL

CREATE DATABASE tarefas_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
Configure o application.properties: O arquivo application.properties não é enviado ao repositório por razões de segurança. Você deve criá-lo manualmente:

Vá para a pasta src/main/resources/.

Crie um arquivo chamado application.properties.

Cole o conteúdo abaixo, substituindo [sua_senha] pela senha que você usa no seu MySQL (geralmente root ou a senha que você definiu).

Properties

# Configuração do Banco de Dados MySQL
spring.datasource.url=jdbc:mysql://localhost:3306/tarefas_db
spring.datasource.username=root
spring.datasource.password=[sua_senha]
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# Configurações do Hibernate (JPA)
# 'update': atualiza o schema se necessário, mas mantém os dados.
# (use 'create' para limpar o banco a cada reinicialização)
spring.jpa.hibernate.ddl-auto=update

# Exibe o SQL gerado no console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
Execute a Aplicação: Abra um terminal na raiz do projeto (onde está o pom.xml) e execute:
mvn spring-boot:run

A API estará disponível para testes em http://localhost:8080.

Documentação dos Endpoints (API)
A base da URL para todos os endpoints é: http://localhost:8080/api/tarefas
Método	URL	Descrição	Exemplo de Body (JSON)
POST	/	Cria uma nova tarefa.	{ "nome": "Nova Tarefa", "dataEntrega": "2025-12-01", "responsavel": "Usuário" }
POST	/lote	Cria várias tarefas em lote.	[ { "nome": "Tarefa A" }, { "nome": "Tarefa B" } ]
GET	/	Lista todas as tarefas.	N/A
GET	/{id}	Busca uma tarefa por ID. (Ex: /1)	N/A
PUT	/{id}	Atualiza uma tarefa por ID.	{ "nome": "Tarefa Atualizada", "dataEntrega": "2025-12-02", "responsavel": "Novo Resp." }
DELETE	/{id}	Remove uma tarefa por ID.	N/A

