# 🐛 Bug Reports — Severity & Priority

**Plataforma:** Mercado Livre (Web)  
**URL:** https://www.mercadolivre.com.br  
**Funcionalidade:** Barra de busca e filtros  
**Ambiente:** Chrome | Windows  
**Foco:** Classificação de bugs por Severidade e Prioridade

---

## Resumo

| ID | Título | Severity | Priority | Status |
|---|---|---|---|---|
| BUG-002 | Caractere especial "!" ignorado na busca | S5 — Cosmético | 🟢 Low | 🔴 Aberto |
| BUG-003 | Filtros removidos ao selecionar novos filtros | S4 — Baixo | 🟡 Medium | 🔴 Aberto |

---

## BUG-002 — Caractere especial "!" ignorado na barra de pesquisa

| Campo | Detalhe |
|---|---|
| **Severity** | S5 — Cosmético |
| **Priority** | 🟢 Low |
| **Status** | 🔴 Aberto |
| **Tipo** | Comportamento de entrada de dados |
| **Ambiente** | Chrome, Windows |

### Descrição
Ao inserir o caractere especial `!` na barra de pesquisa, o sistema ignora esse caractere e executa a busca apenas com os demais caracteres digitados, sem informar o usuário sobre essa desconsideração.

### Passos para Reproduzir
1. Acessar https://www.mercadolivre.com.br
2. Clicar na barra de busca
3. Digitar `!carro`
4. Pressionar `Enter`

### Resultados

**Resultado Esperado:**  
O sistema deveria considerar o caractere na busca **ou** informar que caracteres especiais não são aceitos.

**Resultado Obtido:**  
O sistema ignorou o `!` e executou a busca apenas com `carro`, sem nenhum aviso ao usuário.

### Justificativa da Classificação

| | Justificativa |
|---|---|
| **S5 Cosmético** | Não impacta o funcionamento da busca — o usuário ainda encontra o produto |
| **Low Priority** | O problema não impede o uso da funcionalidade e tem baixo impacto no negócio |

### Evidência
> 📸 *(Adicionar print aqui)*

---

## BUG-003 — Filtros removidos ao selecionar novos filtros na busca de carros

| Campo | Detalhe |
|---|---|
| **Severity** | S4 — Baixo impacto |
| **Priority** | 🟡 Medium |
| **Status** | 🔴 Aberto |
| **Tipo** | Comportamento funcional — filtros |
| **Ambiente** | Chrome, Windows |

### Descrição
Ao aplicar filtros na busca de veículos, filtros previamente selecionados são automaticamente desmarcados quando um novo filtro é aplicado. Isso força o usuário a reaplicar filtros manualmente, prejudicando a experiência de navegação.

### Passos para Reproduzir
1. Acessar https://www.mercadolivre.com.br
2. Buscar por `carros` na barra de pesquisa
3. Selecionar um filtro inicial na área lateral (ex: ano)
4. Aplicar um segundo filtro (ex: região)
5. Observar o comportamento dos filtros anteriores

### Resultados

**Resultado Esperado:**  
Os filtros previamente selecionados deveriam permanecer ativos ao aplicar novos filtros.

**Resultado Obtido:**  
Alguns filtros aplicados anteriormente foram automaticamente removidos ao selecionar novos filtros.

### Justificativa da Classificação

| | Justificativa |
|---|---|
| **S4 Baixo** | A funcionalidade continua operando — o usuário consegue filtrar, mas com dificuldade |
| **Medium Priority** | Afeta a experiência de uso e pode frustrar usuários que dependem de múltiplos filtros |

### Evidência
> 📸 *(Adicionar print aqui)*

---

## Conclusão

A classificação de bugs por **Severity** e **Priority** permite que o time de desenvolvimento concentre esforços nos problemas com maior impacto técnico e de negócio, tornando o processo de correção mais eficiente e estratégico.
