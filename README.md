# 🚀 Conectando APIs: Desenvolvimento Web com React

Este repositório foi criado para auxiliar no **Desenvolvimento Web**, abordando conceitos e práticas essenciais para a integração com APIs RESTful utilizando a extensão **Postman no VSCode**. Aqui, você encontra um guia detalhado para configurar, testar e automatizar chamadas às APIs diretamente no seu editor de código favorito.

---

## 🛠️ Como Configurar a Extensão Postman no VSCode

### **1. Instalar a Extensão Postman**
- **Instale no VSCode**:
  - Acesse o **Marketplace de Extensões** no VSCode.
  - Pesquise por **Postman** e clique em **Install**.
- **Configuração inicial**:
  - Após instalar, abra a extensão e faça login na sua conta Postman ou crie uma.

---

## ⚙️ Configurar o Ambiente
Antes de começar os testes:

- **Crie um ambiente no Postman**:
  - Clique em **Environments** na barra lateral do Postman.
  - Adicione variáveis, como URLs base ou tokens de autenticação:
    ```json
    {
      "base_url": "https://api.example.com",
      "token": "seu_token_aqui"
    }
    ```
  - Essas variáveis podem ser usadas nas requisições, tornando-as dinâmicas.

---

## 📡 Criar e Executar Requisições

### **1. Acessar a extensão**:
   - Na barra lateral, clique no ícone do **Postman**.

### **2. Criar nova requisição**:
   - Clique em **New Request**.
   - Insira detalhes da requisição:
     - **Método**: `GET`, `POST`, etc.
     - **URL**: Substitua variáveis de ambiente se necessário, por exemplo:
       ```
       {{base_url}}/endpoint
       ```
   - **Adicione headers**:
     - Exemplo para autenticação:
       ```json
       {
         "Authorization": "Bearer {{token}}",
         "Content-Type": "application/json"
       }
       ```
   - **Adicione body** (para métodos como `POST` ou `PUT`):
     ```json
     {
       "campo1": "valor1",
       "campo2": "valor2"
     }
     ```

### **3. Executar a requisição**:
   - Clique no botão **Send** para enviar a requisição e veja a resposta no painel.

---

## 🔎 Analisar Respostas
A extensão exibe:

- **Status HTTP**: (ex.: `200 OK`, `404 Not Found`).
- **Headers de resposta**: Mostra metadados, como tipo de conteúdo.
- **Body**: O corpo da resposta em JSON, texto ou outro formato.

---

## ✅ Testar com Scripts

Adicione scripts para validar respostas automaticamente:

- **Script de pré-requisição**: Executado antes do envio.
- **Script de teste**: Validar a resposta.
  ```javascript
  pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
  });

  pm.test("Response time is below 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
  });

  pm.test("Body contains campo1", function () {
    pm.expect(pm.response.json()).to.have.property("campo1");
  });
  ```

---

## 🐞 Depuração
Utilize o painel de **logs** do Postman no VSCode:

- Verifique requisições e respostas detalhadas.
- Depure erros diretamente no ambiente de desenvolvimento.

---

## 🔄 Integração com Projetos

- **Gere código para chamadas API**:
  - Após configurar a requisição, clique em **Generate Code** para obter snippets em várias linguagens (ex.: JavaScript, Python, etc.).
- **Use os snippets no projeto React**, garantindo consistência.

---

## 📚 Automatização e Coleções

- **Coleções**:
  - Agrupe várias requisições para organizar testes.

- **Automatização**:
  - Use o **Runner** no Postman para executar todas as requisições de uma coleção de forma sequencial.

- **Testes em CI/CD**:
  - Exporte coleções do Postman para integração com pipelines.

---

## 🎯 Benefícios do Postman no VSCode

- Centraliza o desenvolvimento e testes de APIs.
- Facilita a colaboração entre equipe com coleções compartilháveis.
- Economiza tempo com a geração de snippets de código.

---

Se precisar de ajuda com um caso específico, contribua com este repositório enviando dúvidas ou sugestões! 😄
