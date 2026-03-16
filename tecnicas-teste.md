# 📖 Técnicas de Teste: Partição de Equivalência e Análise de Valor Limite

> Técnicas fundamentais para criar casos de teste mais eficientes, reduzindo a quantidade de testes sem perder cobertura.

---

## Tipos de Teste

### Teste Positivo
Verifica se o sistema funciona corretamente quando o usuário executa **ações válidas**.

**Exemplo:** Buscar um produto existente na barra de busca.  
**Resultado esperado:** O sistema retorna produtos relacionados.

### Teste Negativo
Verifica como o sistema se comporta quando o usuário realiza **ações inválidas ou inesperadas**.

**Exemplo:** Buscar utilizando caracteres inválidos ou sem sentido.  
**Resultado esperado:** O sistema trata o erro ou informa que não há resultados.

### Teste de Caixa Preta
Metodologia em que o testador avalia o sistema **sem acessar o código interno**.

O foco está em:
- Entradas do sistema
- Comportamento da interface
- Saídas geradas

> 💡 Muito utilizado em QA funcional — é exatamente o que praticamos nos testes do Mercado Livre.

---

## Partição de Equivalência

Consiste em dividir os dados de entrada em **grupos (classes)** que devem se comportar da mesma forma no sistema.

Em vez de testar todos os valores possíveis, testamos apenas **um representante de cada grupo**.

### Exemplo prático

Campo que aceita valores de **1 a 10**:

| Classe | Tipo |
|---|---|
| 1 a 10 | ✅ Classe válida |
| Menor que 1 | ❌ Classe inválida |
| Maior que 10 | ❌ Classe inválida |

> Não é necessário testar todos os números de 1 a 10 — basta um de cada classe.

---

## Análise de Valor Limite (AVL)

Foca em testar os **extremos de entrada**, pois a maioria dos erros ocorre nesses pontos.

### Exemplo prático

Campo que aceita valores de **1 a 100**:

| Valor | Tipo |
|---|---|
| 0 | ❌ Inválido (abaixo do limite) |
| 1 | ✅ Limite mínimo |
| 2 | ✅ Próximo ao limite mínimo |
| 99 | ✅ Próximo ao limite máximo |
| 100 | ✅ Limite máximo |
| 101 | ❌ Inválido (acima do limite) |

---

## Quando usar cada técnica?

| Situação | Técnica recomendada |
|---|---|
| Campo com muitos valores possíveis | Partição de Equivalência |
| Campo com limites definidos (min/max) | Análise de Valor Limite |
| Ambos os casos | Combinar as duas ✅ |
