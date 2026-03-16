# 🔍 Teste Exploratório — Busca do Mercado Livre

**Plataforma:** Mercado Livre (Web)  
**URL:** https://www.mercadolivre.com.br  
**Ambiente:** Chrome | Windows  
**Tipo:** Exploratório  
**Objetivo:** Explorar comportamentos da barra de busca além dos fluxos esperados

---

## Resumo dos Testes

| # | Entrada | Resultado | Observação |
|---|---|---|---|
| EXP-001 | Emoji 😀 | Nenhum resultado encontrado | Comportamento adequado |
| EXP-002 | Texto em japonês `シャツ` | Produtos corretos retornados | Busca multilíngue funciona ✅ |
| EXP-003 | Produto +18 | Aviso de confirmação de idade | Não exige login ⚠️ |
| EXP-004 | Texto sem sentido `asd123qwe` | Produtos aleatórios | Sem sugestão de correção ⚠️ |
| EXP-005 | Texto muito longo com aspas | Ignora aspas parcialmente | Comportamento inesperado ⚠️ |

---

## EXP-001 — Busca por emoji

**Entrada:** `😀`

**Resultado:**  
O sistema apresentou mensagem informando que nenhum resultado foi encontrado.

**Avaliação:** ✅ Comportamento adequado — mensagem clara para o usuário.

---

## EXP-002 — Busca em outro idioma

**Entrada:** `シャツ` *(japonês para "camisa")*

**Resultado:**  
O sistema retornou produtos relacionados à categoria "camisa" corretamente.

**Avaliação:** ✅ O mecanismo de busca suporta múltiplos idiomas — boa capacidade de internacionalização.

---

## EXP-003 — Busca por produto +18

**Entrada:** termo relacionado a produto adulto

**Resultado:**  
O sistema exibiu um aviso informando que os produtos são destinados apenas para maiores de 18 anos e solicitou confirmação de idade.

**Avaliação:** ⚠️ O sistema apresenta o aviso, porém **não exige login** para visualizar os produtos após a confirmação — o que pode ser um ponto de melhoria do ponto de vista de controle de acesso.

---

## EXP-004 — Busca com texto sem sentido

**Entrada:** `asd123qwe`

**Resultado:**  
O sistema retornou diversos produtos aleatórios sem sugerir possíveis correções ou termos similares.

**Avaliação:** ⚠️ Experiência do usuário prejudicada — ideal seria exibir "Nenhum resultado encontrado" ou sugestões de busca.

---

## EXP-005 — Busca com texto muito longo e aspas

**Entrada:** texto extenso contendo uma palavra entre aspas

**Resultado:**  
O sistema ignorou parcialmente o termo entre aspas e retornou produtos aleatórios.

**Avaliação:** ⚠️ Operadores de busca como aspas (busca exata) não funcionam conforme esperado.

**Observação adicional:** Foi identificado que a barra de busca possui **limite de caracteres**.

---

## Conclusões do Teste Exploratório

### ✅ Pontos positivos
- Suporte a múltiplos idiomas na busca
- Mensagem clara para busca por emojis
- Controle de conteúdo adulto com aviso ao usuário

### ⚠️ Pontos de melhoria
- Ausência de sugestão de correção ortográfica
- Produtos aleatórios para buscas sem sentido
- Operador de aspas (busca exata) não funciona
- Conteúdo +18 acessível sem autenticação
