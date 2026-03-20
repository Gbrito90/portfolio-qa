# 🔌 Testes de API com Postman — Dia 6

**Ferramenta:** Postman  
**API utilizada:** JSONPlaceholder (https://jsonplaceholder.typicode.com)  
**Ambiente:** Chrome | Windows  
**Objetivo:** Validar o funcionamento de endpoints de uma API REST, garantindo que retornem dados corretos e tratem erros adequadamente.

---

## Resumo dos Resultados

| ID | Endpoint | Tipo | Status Code esperado | Resultado |
|---|---|---|---|---|
| API-001 | GET /users | Positivo | 200 OK | ✅ Passou |
| API-002 | GET /userrrr | Negativo | 404 Not Found | ✅ Passou |

---

## API-001 — Listagem de usuários

| Campo | Detalhe |
|---|---|
| **Método** | GET |
| **Endpoint** | `https://jsonplaceholder.typicode.com/users` |
| **Tipo** | Positivo |
| **Status esperado** | 200 OK |
| **Resultado** | ✅ Passou |

### Validações realizadas

| Validação | Resultado |
|---|---|
| Status code 200 | ✅ PASSED |
| Response não está vazia | ✅ PASSED |
| Campos obrigatórios presentes (id, name, email) | ✅ PASSED |

### Scripts de Teste (Postman)

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response is not empty", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.length).to.be.above(0);
});

pm.test("User has required fields", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData[0]).to.have.property("id");
    pm.expect(jsonData[0]).to.have.property("name");
    pm.expect(jsonData[0]).to.have.property("email");
});
```

### Exemplo de Response (JSON)

```json
[
  {
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz",
    "address": {
      "street": "Kulas Light",
      "suite": "Apt. 556",
      "city": "Gwenborough",
      "zipcode": "92998-3874"
    }
  }
]
```

### Evidências

> 📸 Imagem 1 — Response 200 OK com dados JSON retornados
> ![preview](https://github.com/user-attachments/assets/5dfb1b0e-9f9f-4442-970a-b2a4e6077d27)

> 📸 Imagem 2 — Scripts de teste com 3/3 testes passando
> ![preview (1)](https://github.com/user-attachments/assets/6886b8f5-a90e-4f8f-92c8-a00ec3fa2e0c)


---

## API-002 — Endpoint inválido (Teste Negativo)

| Campo | Detalhe |
|---|---|
| **Método** | GET |
| **Endpoint** | `https://jsonplaceholder.typicode.com/userrrr` |
| **Tipo** | Negativo |
| **Status esperado** | 404 Not Found |
| **Resultado** | ✅ Passou |

### Validações realizadas

| Validação | Resultado |
|---|---|
| Status code 404 | ✅ PASSED |

### Script de Teste (Postman)

```javascript
pm.test("Status code is 404", function () {
    pm.response.to.have.status(404);
});
```

### Evidência

> 📸 Imagem 3 — Status 404 Not Found com teste passando

---

## Conclusão

Os testes demonstram que a API responde corretamente tanto em cenários positivos quanto negativos:

- **Cenário positivo:** endpoint `/users` retorna status 200, lista não vazia e campos obrigatórios presentes
- **Cenário negativo:** endpoint inválido `/userrrr` retorna status 404 conforme esperado

Essa prática combina **testes manuais** (observar a response) com **testes automatizados** (scripts no Postman), simulando um fluxo real de QA de API.
