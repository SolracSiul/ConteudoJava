# **Introdução ao Spring Boot com VS Code**

## **1. O que é o Spring Boot?**
O **Spring Boot** é um framework Java que facilita a criação de aplicações web e APIs REST. Ele abstrai configurações complexas do **Spring Framework** e permite que você crie um servidor com **pouco código**.

Com o **Spring Boot**, você pode:
- Criar APIs rapidamente.
- Usar **Spring MVC** para manipular requisições HTTP.
- Utilizar **Spring Data** para acesso ao banco de dados.
- Gerenciar dependências automaticamente com **Spring Boot Starter**.

---

## **2. Preparando o Ambiente no VS Code**
### **Instale os seguintes itens:**
1. **Java JDK 17+** (ou versão mais recente)
2. **VS Code**
3. **Extensão Spring Boot Extension Pack** (disponível no marketplace do VS Code)
4. **Maven** (caso não tenha, instale: [Maven Download](https://maven.apache.org/download.cgi))

---

## **3. Criando um Projeto Spring Boot**
Vamos usar o **Spring Initializr** para configurar o projeto. Siga os passos:

1. Acesse **[Spring Initializr](https://start.spring.io/)**.
2. Escolha as seguintes configurações:
   - **Project:** Maven
   - **Language:** Java
   - **Spring Boot Version:** 3.x.x (ou a mais recente)
   - **Group:** com.exemplo.api
   - **Artifact:** produtos-api
   - **Name:** produtos-api
   - **Package Name:** com.exemplo.api
   - **Dependencies:** 
     - **Spring Web** (para criar APIs)
3. Clique em **Generate**, baixe o arquivo ZIP e extraia no VS Code.

---

## **4. Criando o Controller (ProdutoController)**
Agora, substitua o código do `ProdutoController.java` pelo que você passou. No **VS Code**, vá até a pasta `src/main/java/com/exemplo/api/controller/` e crie o arquivo **`ProdutoController.java`**.

Coloque o seguinte código dentro dele:

```java
package com.exemplo.api.controller;

import org.springframework.web.bind.annotation.*;

import java.util.ArrayList;
import java.util.List;

@RestController
@RequestMapping("/produtos")
public class ProdutoController {

    private List<String> produtos = new ArrayList<>();

    @GetMapping
    public List<String> listarProdutos() {
        return produtos;
    }

    @PostMapping
    public String adicionarProduto(@RequestBody String produto) {
        produtos.add(produto);
        return "Produto adicionado: " + produto;
    }

    @DeleteMapping("/{index}")
    public String removerProduto(@PathVariable int index) {
        if (index >= 0 && index < produtos.size()) {
            String removido = produtos.remove(index);
            return "Produto removido: " + removido;
        }
        return "Índice inválido!";
    }
}
```

---

## **5. Executando o Projeto no VS Code**
Agora, vá até o terminal e rode os seguintes comandos:

```sh

cd /caminho/para/produtos-api


./mvnw spring-boot:run  # (Linux)
mvnw.cmd spring-boot:run # (Windows)
```

Se tudo estiver certo, verá algo como:
```
Tomcat started on port(s): 8080
Started ProdutosApiApplication in 2.345 seconds
```

Agora, sua API estará rodando em **http://localhost:8080/produtos** 🚀

---

## **6. Testando a API**
### **Listar Produtos (GET)**
Abra um navegador ou use o Postman para acessar:
```
GET http://localhost:8080/produtos
```

### **Adicionar Produto (POST)**
No **Postman**, envie uma requisição **POST** com um produto no corpo:

- URL: `http://localhost:8080/produtos`
- Body (JSON):  
```json
"Celular"
```

### **Remover Produto (DELETE)**
Para remover um produto do índice **0**, envie:
```
DELETE http://localhost:8080/produtos/0
```

---

Isso já te dá um projeto básico de **Spring Boot** rodando no **VS Code**! Se quiser avançar, podemos integrar com um banco de dados. 🚀
