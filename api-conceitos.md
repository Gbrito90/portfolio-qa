# 📖 Fundamentos de Testes de API

> Conceitos essenciais para entender e testar APIs REST como QA.

---

## O que é uma API REST?

Uma **API (Application Programming Interface)** é uma interface que permite que dois sistemas se comuniquem. O estilo **REST** define como essa comunicação deve funcionar usando o protocolo HTTP.

---

## Métodos HTTP principais

| Método | O que faz |
|---|---|
| `GET` | Busca dados |
| `POST` | Cria novos dados |
| `PUT` | Atualiza dados existentes |
| `DELETE` | Remove dados |

---

## Status Codes mais importantes para QA

| Código | Nome | Significado |
|---|---|---|
| 200 | OK | Requisição bem-sucedida |
| 201 | Created | Recurso criado com sucesso |
| 400 | Bad Request | Requisição inválida |
| 401 | Unauthorized | Sem autenticação |
| 403 | Forbidden | Sem permissão |
| 404 | Not Found | Recurso não encontrado |
| 500 | Internal Server Error | Erro no servidor |

---

## O que validar em testes de API?

| O que validar | Exemplo |
|---|---|
| **Status code** | Response retorna 200? |
| **Estrutura do JSON** | Campos obrigatórios presentes? |
| **Dados retornados** | Lista não está vazia? |
| **Tempo de resposta** | Response em menos de 2s? |
| **Erros tratados** | Endpoint inválido retorna 404? |

---

## Anatomia de um teste no Postman

```javascript
// Estrutura básica de um teste
pm.test("Nome do teste", function () {
    // asserção aqui
});

// Exemplos práticos
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response is not empty", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData.length).to.be.above(0);
});

pm.test("Campo obrigatório presente", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData[0]).to.have.property("id");
});
```

---

## Testes Positivos vs Negativos em API

| Tipo | Objetivo | Exemplo |
|---|---|---|
| **Positivo** | Validar que o endpoint funciona corretamente | GET /users → 200 + dados |
| **Negativo** | Validar que erros são tratados adequadamente | GET /userrr → 404 |
