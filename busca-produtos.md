# 🧪 Casos de Teste — Busca de Produtos

**Plataforma:** Mercado Livre (Web)  
**URL:** https://www.mercadolivre.com.br  
**Funcionalidade:** Barra de busca  
**Ambiente:** Chrome | Windows  
**Tipo de teste:** Funcional, Negativo

---

## Resumo dos Resultados

| ID | Cenário | Tipo | Status |
|---|---|---|---|
| CT-001 | Busca por produto existente | Funcional | ✅ Passou |
| CT-002 | Busca por termo inexistente | Negativo | ⚠️ Comportamento inesperado |
| CT-003 | Busca sem inserir termo | Negativo | ⚠️ Comportamento não ideal |
| CT-004 | Busca com caracteres especiais | Negativo | ⚠️ Comportamento inesperado |

---

## CT-001 — Busca por produto existente

| Campo | Detalhe |
|---|---|
| **Tipo** | Funcional |
| **Prioridade** | Alta |
| **Status** | ✅ Passou |

**Pré-condição:** Estar na página inicial do Mercado Livre

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Digitar `notebook`
4. Pressionar `Enter`
5. Visualizar os resultados apresentados

**Resultado Esperado:**  
O sistema deve exibir uma lista de produtos relacionados a "notebook".

**Resultado Obtido:**  
O sistema exibiu diversos notebooks disponíveis para compra, filtros adicionais e informações detalhadas dos produtos. ✅

---

## CT-002 — Busca por termo inexistente

| Campo | Detalhe |
|---|---|
| **Tipo** | Negativo |
| **Prioridade** | Média |
| **Status** | ⚠️ Comportamento inesperado |

**Pré-condição:** Estar na página inicial do Mercado Livre

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Digitar `121rrr1111`
4. Pressionar `Enter`
5. Visualizar os resultados apresentados

**Resultado Esperado:**  
O sistema deveria exibir uma mensagem indicando que nenhum produto foi encontrado, ou sugerir termos de busca similares.

**Resultado Obtido:**  
O sistema exibiu produtos com números similares ao termo, sem apresentar mensagem clara de busca inválida.

**Observação:**  
Possível melhoria de experiência do usuário — seria ideal exibir "Nenhum resultado encontrado" ou sugestões de busca.

---

## CT-003 — Busca sem inserir termo

| Campo | Detalhe |
|---|---|
| **Tipo** | Negativo |
| **Prioridade** | Baixa |
| **Status** | ⚠️ Comportamento não ideal |

**Pré-condição:** Estar na página inicial do Mercado Livre

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Não inserir nenhum texto
4. Pressionar `Enter`

**Resultado Esperado:**  
O sistema deveria exibir sugestões de busca, produtos em destaque ou uma mensagem orientando o usuário.

**Resultado Obtido:**  
Nenhuma ação ocorreu após pressionar Enter.

**Observação:**  
Uma mensagem como "Digite o que você está procurando" melhoraria a experiência do usuário.

---

## CT-004 — Busca com caracteres especiais

| Campo | Detalhe |
|---|---|
| **Tipo** | Negativo |
| **Prioridade** | Média |
| **Status** | ⚠️ Comportamento inesperado |

**Pré-condição:** Estar na página inicial do Mercado Livre

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Digitar `!@#$`
4. Pressionar `Enter`

**Resultado Esperado:**  
O sistema deveria retornar nenhum resultado ou exibir mensagem informando que a busca é inválida.

**Resultado Obtido:**  
O sistema removeu alguns caracteres especiais da busca e apresentou produtos relacionados aos caracteres restantes.

**Observação:**  
Comportamento de sanitização parcial — ideal seria informar o usuário que a busca contém caracteres inválidos.
