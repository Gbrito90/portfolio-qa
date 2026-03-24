# 📖 Tipos de Teste de Software

> Estudo teórico sobre os principais tipos de teste utilizados em QA, cobrindo desde testes unitários até a pirâmide de testes.

---

## Teste de Unidade

Unidades individuais de código são testadas isoladamente para verificar se funcionam como esperado.

- Testamos o código da aplicação
- Pode ser testado de forma independente

### Objetivos
- Isolamento de funcionalidades
- Identificação de defeitos
- Garantia de qualidade do código
- Facilitar a refatoração

---

## Teste de Integração

Diferentes unidades ou módulos de um sistema são combinados e testados como um grupo.  
Verifica se dois ou mais módulos funcionam em conjunto de maneira adequada.

### Objetivos
- Verificar se diferentes módulos do sistema ou componentes conseguem trabalhar juntos sem conflito ou erros
- Identificar comportamento inesperado
- Avaliar comunicação entre módulos
- Garantir a consistência do sistema

### Desafios
- Identificação de dependências: com quem ele se comunica
- Isolamento de defeitos: onde está a origem do defeito/problema
- Custos e complexidade
- Simulação em ambiente real

### Benefícios
- Garantia de funcionalidade global
- Detecção precoce dos problemas de integração
- Maior confiança na qualidade do sistema
- Facilita a evolução e manutenção do sistema

---

## Teste de Sistema

Verifica se o sistema inteiro atende especificações definidas previamente.

### Objetivos
- Validação de requisitos
- Avaliação de funcionalidade global
- Verificação de usabilidade (UX)
- Teste de desempenho e carga
- Teste de segurança
- Avaliação de conformidade

### Tipos de Teste
| Tipo | Foco |
|---|---|
| Funcionais / Usabilidade | Comportamento e experiência |
| Desempenho / Carga | Velocidade e estabilidade |
| Segurança | Vulnerabilidades |
| Compatibilidade / Conformidade | Padrões e ambientes |

### Benefícios
- Identificação de problemas críticos
- Aumento da satisfação do cliente
- Prevenção de problemas futuros
- Antes do ambiente de produção

---

## Teste de Aceitação

Feito pelo cliente/usuário final para verificar se o sistema atende aos critérios de aceitação.  
Ocorre após os testes de sistema e antes da implantação.

### Objetivos
- Garantir que o sistema está pronto para produção
- Preparação para lançamento

### Benefícios
- Validação do cliente
- Confiança na qualidade
- Redução de riscos na implementação
- Preparação para o ambiente
- Melhoria contínua

---

## Pirâmide de Teste

Representa a distribuição equilibrada de diferentes tipos de testes ao longo do desenvolvimento e a hierarquia de teste.

```
        /‾‾‾‾‾‾‾‾‾‾‾‾‾\
       /  Testes de    \
      /    Sistema      \
     /‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\
    /  Testes de         \
   /    Integração        \
  /‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\
 /     Testes Unitários     \
/‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾\
```

- A **maioria** dos testes devem ser de unidade — mais rápidos e menos propensos a falhas
- Poucos testes de integração de componentes
- Aceitação/automação começa superior com maior custo e margem de erro

---

## Caixa Branca x Caixa Preta

### Caixa Branca
Testes avaliam a partir da **estrutura do código-fonte**.  
Concentra-se na lógica do código com seus caminhos e condições internas.

| Campo | Detalhe |
|---|---|
| **Processo** | Casos de teste com base em análise lógica |
| **Benefícios** | Falhas de lógica, loop, erro de sintaxe e o que não foi testado |
| **Tipos** | Cobertura de código, teste de caminho, teste de decisão e condição |

### Caixa Preta
Avaliação **sem testar/considerar** a estrutura interna do código-fonte ou a lógica subjacente.  
Testamos o sistema/aplicação pelo comportamento externo.

| Campo | Detalhe |
|---|---|
| **Foco** | Entrada e saída dos sistemas |
| **Processo** | QA não tem conhecimento do código interno — apenas funções, requisitos e documentação para criação de casos de teste |
| **Benefícios** | Não precisa de conhecimento de programação para testar, pode intensificar falhas de lógica |
| **Tipos** | Funcionalidades, usabilidades, integração |

---

## Testes Funcionais e Não Funcionais

### Funcionais
Avalia o comportamento de um sistema ou aplicativo em relação às especificações funcionais.

- Funciona conforme os requisitos
- Não requer lógica interna (caixa preta)
- **Entrada e saída:** envolve entrada e saída de dados na tela via interface do usuário
- **Cenários de uso:** simular uma situação de uso real como integração
- **Tipos:** Regressão, integração e regressão
- **Objetivo:** Garantir que o software atenda os requisitos funcionais
- **Benefícios:** Verificação de requisitos, validação da usabilidade e experiência do usuário, identificação de falhas

### Não Funcionais
Avaliam aspectos cruciais para determinar o desempenho, usabilidade e segurança — características mais permanentes que afetam a qualidade.

- **Avaliação:** Desempenho, escalabilidade, usabilidade e segurança
- **Medição:** Avaliar a qualidade global do software
- **Objetivo:** Testes de usabilidade com foco no usuário — podem ser subjetivos
- **Tipos:** Desempenho/carga, usabilidade, segurança, manutenibilidade, confiabilidade e disponibilidade
