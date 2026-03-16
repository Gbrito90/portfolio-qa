# 📖 Classificação de Bugs: Severity vs Priority

> Conceitos fundamentais para identificar, analisar e documentar bugs de forma estruturada — essencial para ajudar o time de desenvolvimento a priorizar correções.

---

## O que é um Bug?

Um bug é qualquer comportamento do sistema que:
- Causa erro
- Não segue o funcionamento esperado
- Prejudica a experiência do usuário

> Bugs variam desde problemas críticos que impedem o uso do sistema até pequenos erros visuais.

---

## Severity (Severidade)

Representa o **impacto técnico** do bug no funcionamento do sistema.  
Quanto maior a severidade, maior o impacto na aplicação.

| Nível | Classificação | Descrição |
|---|---|---|
| S1 | 🔴 Crítico | Sistema ou funcionalidade principal quebra |
| S2 | 🟠 Alto | Funcionalidade importante afetada |
| S3 | 🟡 Moderado | Problema que afeta parcialmente a funcionalidade |
| S4 | 🔵 Baixo | Pequeno impacto |
| S5 | ⚪ Cosmético | Problema visual sem impacto funcional |

---

## Priority (Prioridade)

Representa a **urgência de correção** do bug para o negócio.  
Define com que rapidez o time precisa agir.

| Prioridade | Descrição |
|---|---|
| 🔴 High | Correção urgente |
| 🟡 Medium | Correção necessária em breve |
| 🟢 Low | Pode ser corrigido futuramente |

---

## Severity vs Priority — Qual a diferença?

| | Severity | Priority |
|---|---|---|
| **Foco** | Impacto técnico no sistema | Urgência para o negócio |
| **Definido por** | QA / time técnico | Product Owner / negócio |
| **Exemplo** | Bug crítico em tela pouco usada | Bug visual em página de pagamento |

### Combinações importantes

| Severidade | Prioridade | Exemplo |
|---|---|---|
| Alta | Alta | Login quebrado — corrige agora |
| Alta | Baixa | Bug crítico em feature descontinuada |
| Baixa | Alta | Erro visual na página de checkout |
| Baixa | Baixa | Espaçamento errado em rodapé |

> 💡 **Resumo:** Severidade mede o *estrago*. Prioridade mede a *urgência*.
