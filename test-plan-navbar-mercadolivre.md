# 📋 Test Plan — Navbar do Mercado Livre

**Responsável:** Guilherme Brito (QA em formação)  
**Plataforma:** Mercado Livre (Web)  
**URL:** https://www.mercadolivre.com.br  
**Ambiente:** Chrome | Windows | Desktop

---

## 1. Análise do Produto

**Componente testado:** Navbar (barra de navegação) do Mercado Livre

**Objetivo do componente:**  
Permitir que os usuários encontrem produtos e naveguem pelo sistema de forma rápida e eficiente.

**Usuários envolvidos:**
- Compradores
- Usuários não logados
- Vendedores

**Tecnologias:**

| Camada | Tecnologia |
|---|---|
| Front-end | React |
| Back-end | Java |
| Plataforma | Web |

---

## 2. Estratégia de Teste

### Escopo

| ✅ Dentro do escopo | ❌ Fora do escopo |
|---|---|
| Barra de busca | Checkout |
| Navegação por categorias | Login |
| Aplicação de filtros | Página de produto |

### Tipos de Teste

- Teste exploratório
- Teste funcional
- Teste negativo
- Teste de usabilidade

### Riscos Identificados

| Risco | Impacto |
|---|---|
| Falhas na busca | Alto |
| Resultados incorretos | Alto |
| Filtros não funcionando | Médio |
| Interface confusa | Baixo |

---

## 3. Objetivos do Teste

- Validar o funcionamento completo da navbar
- Garantir que a busca retorna resultados eficientes
- Avaliar a experiência do usuário na navegação
- Identificar falhas e documentar bugs encontrados

---

## 4. Critérios de Teste

### Critérios de Suspensão
Os testes devem ser suspensos se:
- Ocorrerem erros críticos na busca
- A navbar parar de funcionar completamente
- O sistema estiver indisponível

### Critérios de Saída
Os testes podem ser encerrados quando:
- Todos os casos de teste planejados forem executados
- Bugs encontrados estiverem documentados
- As funcionalidades principais estiverem validadas

---

## 5. Planejamento de Recursos

**Recursos Humanos:**
- 1 QA responsável pelos testes

**Recursos Técnicos:**

| Recurso | Detalhe |
|---|---|
| Dispositivo | Computador Desktop |
| Navegador | Google Chrome |
| Conexão | Internet |

---

## 6. Ambiente de Teste

| Campo | Detalhe |
|---|---|
| Aplicação | Mercado Livre Web |
| Navegador | Google Chrome |
| Sistema Operacional | Windows |
| Dispositivo | Desktop |

---

## 7. Cronograma

| Etapa | Tempo estimado |
|---|---|
| Análise | 20 min |
| Execução dos testes | 40 min |
| Documentação | 30 min |
| **Total** | **90 min** |

---

## 8. Entregáveis

- [x] Test Plan
- [x] Casos de teste
- [x] Bug Reports
- [x] Evidências dos testes *(prints)*

---

## Considerações Finais

Durante os testes, foi possível identificar oportunidades de melhoria na experiência do usuário, principalmente relacionadas à busca e aplicação de filtros.

A documentação foi criada com foco em simular um ambiente real de trabalho de QA, aplicando conceitos de teste exploratório e análise funcional.
