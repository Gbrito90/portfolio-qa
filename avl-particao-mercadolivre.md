# 🧪 Casos de Teste — Partição de Equivalência e Análise de Valor Limite

**Plataforma:** Mercado Livre (Web)  
**URL:** https://www.mercadolivre.com.br  
**Funcionalidade:** Barra de busca  
**Ambiente:** Chrome | Windows  
**Técnicas aplicadas:** Partição de Equivalência + Análise de Valor Limite (AVL)

---

## Resumo dos Resultados

| ID | Cenário | Técnica | Status |
|---|---|---|---|
| CT-005 | Busca com 1 caractere (limite mínimo) | AVL | ⚠️ Parcial |
| CT-006 | Busca com ~120 caracteres (limite máximo) | AVL | ⚠️ Parcial |
| CT-007 | Busca com termo válido intermediário | AVL + Partição | ✅ Passou |

---

## CT-005 — Busca com 1 caractere (Valor Limite Mínimo)

| Campo | Detalhe |
|---|---|
| **Tipo** | Análise de Valor Limite |
| **Classe** | Limite mínimo de entrada |
| **Prioridade** | Média |
| **Status** | ⚠️ Passou parcialmente |

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Digitar `A`
4. Pressionar `Enter`

**Resultado Esperado:**  
O sistema deveria executar a busca normalmente.

**Resultado Obtido:**  
A busca foi executada, porém o sistema retornou:  
> *"Não encontramos resultados para sua busca."*

**Observação:**  
O sistema aceita 1 caractere como entrada válida, mas não encontra produtos relacionados. Comportamento aceitável — a entrada é processada sem erros.

---

## CT-006 — Busca com texto longo (Valor Limite Máximo)

| Campo | Detalhe |
|---|---|
| **Tipo** | Análise de Valor Limite |
| **Classe** | Limite máximo de entrada (~120 caracteres) |
| **Prioridade** | Média |
| **Status** | ⚠️ Passou parcialmente |

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Inserir texto com aproximadamente 120 caracteres
4. Pressionar `Enter`

**Resultado Esperado:**  
O sistema deveria processar a busca normalmente.

**Resultado Obtido:**  
A busca foi executada, porém o sistema informou que não encontrou resultados relacionados.

**Observação:**  
Testes com valores próximos ao limite (~118 caracteres) também funcionaram normalmente, confirmando que o sistema aceita entradas longas sem travar ou gerar erro.

---

## CT-007 — Busca com termo válido (Valor Intermediário)

| Campo | Detalhe |
|---|---|
| **Tipo** | AVL + Partição de Equivalência |
| **Classe** | Valor intermediário — classe válida |
| **Prioridade** | Alta |
| **Status** | ✅ Passou |

**Passos:**
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Digitar `carro`
4. Pressionar `Enter`

**Resultado Esperado:**  
O sistema deve retornar produtos relacionados à busca.

**Resultado Obtido:**  
A busca foi executada com sucesso e diversos produtos foram apresentados. ✅

---

## Mapa de Classes — Partição de Equivalência (Barra de Busca)

| Classe | Exemplo | Tipo | Comportamento observado |
|---|---|---|---|
| 1 caractere | `A` | Limite mínimo | Aceita, sem resultados |
| Termo curto válido | `tv` | Válida | Retorna produtos ✅ |
| Termo médio válido | `carro` | Válida | Retorna produtos ✅ |
| Texto muito longo | ~120 chars | Limite máximo | Aceita, sem resultados |
| Caracteres especiais | `!@#$` | Inválida | Remove caracteres, retorna aleatórios ⚠️ |
| Sem texto | *(vazio)* | Inválida | Nenhuma ação ⚠️ |

---

## Conclusões

- A aplicação das técnicas de **Partição de Equivalência** e **AVL** permitiu identificar comportamentos importantes da busca com um número reduzido de testes
- O sistema **prioriza retornar resultados aproximados** mesmo quando a busca não é clara — o que pode ser positivo para UX, mas dificulta identificar o limite real de caracteres aceitos
- Os limites mínimo (1 char) e máximo (~120 chars) foram identificados e o sistema os aceita sem gerar erros críticos
