# 🐛 Bug Reports — Mercado Livre

**Plataforma:** Mercado Livre (Web)  
**URL:** https://www.mercadolivre.com.br  
**Ambiente:** Chrome | Windows

---

## Resumo

| ID | Título | Severidade | Status |
|---|---|---|---|
| BUG-001 | Ausência de sugestão para erros ortográficos | Média | 🔴 Aberto |

---

## BUG-001 — Ausência de sugestão de correção para erros ortográficos

| Campo | Detalhe |
|---|---|
| **Severidade** | Média |
| **Prioridade** | Média |
| **Status** | 🔴 Aberto |
| **Tipo** | UX / Funcional |
| **Ambiente** | Chrome, Windows |
| **Data** | 2025 |

### Descrição

Quando o usuário digita um termo com erro ortográfico na barra de busca, o sistema **não apresenta sugestão de correção** ("Você quis dizer...") e retorna produtos que não correspondem ao termo pretendido.

Isso pode gerar confusão e frustração para o usuário durante a navegação.

---

### Passos para Reproduzir

1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de pesquisa
3. Digitar `cachoooro` *(erro ortográfico intencional)*
4. Pressionar `Enter`

---

### Resultados

**Resultado Esperado:**  
O sistema deveria exibir a mensagem:  
> *"Você quis dizer: **cachorro**?"*  
e/ou sugerir a correção do termo pesquisado.

**Resultado Obtido:**  
O sistema apresenta produtos diferentes do esperado, sem qualquer sugestão de correção ortográfica.

---

### Evidência

> 📸 *(Adicionar print da tela aqui — arraste a imagem diretamente no GitHub)*

---

### Impacto

- Usuário não encontra o produto desejado
- Experiência de busca degradada
- Possível perda de conversão para o marketplace

---

### Sugestão de Melhoria

Implementar mecanismo de **"Did you mean?"** (sugestão de correção ortográfica) similar ao utilizado em outros grandes marketplaces e buscadores.
