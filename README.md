# NLW Connect Java

## ℹ️ Sobre

Sistema de inscrições em eventos, onde os usuários podem se inscrever, gerar links de indicação e acompanhar um ranking de indicações.

## 🚀 Tecnologias

O projeto foi desenvolvido com as seguintes tecnologias:

- **Java 17**
- **Spring Boot 3.4.2**
- **Maven**

### Dependências utilizadas:

- Spring Web
- Spring Boot DevTools
- Spring Data JPA
- MySQL Driver

## 📂 Estrutura do Projeto

O projeto segue a organização tradicional do Spring Boot, adotando a separação de responsabilidades.

**Padrão em camadas**: Model, Controller, Service, Repository, Padrão DTO.

![Image](https://github.com/user-attachments/assets/405c570a-193a-45ac-be25-93b78e4a3847)

### Diagrama Entidade-Relacionamento:

![Image](https://github.com/user-attachments/assets/a8b8265c-bf10-465a-a984-89a6209dd913)

## ✨ Funcionalidades

- 📌 **Inscrição**: Usuários podem se inscrever em eventos informando nome e e-mail.
- 🔗 **Geração de Link de Indicação**: Cada inscrito pode gerar um link de indicação único.
- 📊 **Ranking de Indicações**: Exibe um ranking baseado no número de indicações bem-sucedidas.
- 👥 **Visualização de Indicações**: Cada usuário pode ver quantas pessoas se inscreveram usando seu link.

## 🌐 Rotas da API

Principais rotas disponíveis na aplicação:

### 🎟️ Eventos

- **Criar um evento**  
  (POST) `/events`  
  ![Image](https://github.com/user-attachments/assets/81401c2b-f950-4c07-af75-f8363d8df169)

- **Listar todos os eventos**  
  (GET) `/events`  
  ![Image](https://github.com/user-attachments/assets/2ce33147-9166-4397-8ea4-30841c9ca7fe)

- **Obter evento por nome formatado**  
  (GET) `/events/{prettyName}`  
  ![Image](https://github.com/user-attachments/assets/138043bb-bfa0-415b-abf6-ab74aa94426b)

### 📝 Inscrição

- **Realizar inscrição no evento**  
  (POST) `/subscription/{prettyName}`  
  ![Image](https://github.com/user-attachments/assets/fac7a30f-d0a7-4db3-8d90-3b251725215d)

- **Cadastrar usuário com id de indicação**  
  (POST) `/subscription/{prettyName}/ranking/{userId}`  
  ![Image](https://github.com/user-attachments/assets/56ef0a4d-1c61-4df3-9d03-7e891e6cab68)

- **Visualizar ranking de indicações de um evento**  
  (GET) `/subscription/{prettyName}/ranking`  
  ![Image](https://github.com/user-attachments/assets/31cacd9e-7737-4ff8-8538-862b81ac6235)

- **Visualizar ranking de indicações de um usuário específico**  
  (GET) `/subscription/{prettyName}/ranking/{userId}`  
  ![Image](https://github.com/user-attachments/assets/7e31b564-63bc-4be2-9a4f-127c2322e4ef)

## ▶️ Como Rodar o Projeto

Para executar o projeto localmente, siga os passos abaixo:

1. Clone o repositório:

    ```bash
    git clone --branch aula3 --single-branch https://github.com/lucaslpdacosta/nlw-connect-java.git
    ```

2. Importe o projeto na sua IDE de escolha (Eclipse, IntelliJ, STS):

    - Selecione **Import > Import Maven Projects**

3. Configure o banco de dados:

    - Edite o arquivo `application.properties` e adapte o valor de `spring.datasource.password` (linha 3) conforme sua configuração local.
    - No MySQL, crie o schema do banco de dados:

      ```sql
      CREATE SCHEMA db_events;
      ```

4. Inicie o servidor:

    - Execute a aplicação dentro da sua IDE ou via terminal com:

      ```bash
      mvn spring-boot:run
      ```
