# Plano de Testes — Site MTP Global
> **Projeto:** Site institucional mtp.com.br  
> **Versão:** 1.0  
> **Data:** 24/04/2026  
> **Responsável:** QA Sênior  
> **Metodologia:** BDD (Behavior Driven Development)

---

## Sumário

| # | Módulo | Casos |
|---|--------|-------|
| 1 | [Home](#home) | 2 |
| 2 | [Navegação](#navegação) | 7 |
| 3 | [Formulário de Contato](#formulário-de-contato) | 9 |
| 4 | [Carreiras](#carreiras) | 2 |
| 5 | [Liderança](#liderança) | 1 |
| 6 | [Contato](#contato) | 2 |
| 7 | [Rodapé](#rodapé) | 3 |
| 8 | [Responsividade](#responsividade) | 2 |
| 9 | [Compatibilidade](#compatibilidade) | 3 |
| 10 | [Performance](#performance) | 2 |
| 11 | [Segurança](#segurança) | 2 |
| 12 | [Cookies](#cookies) | 2 |
| 13 | [Acessibilidade](#acessibilidade) | 2 |
| 14 | [Pesquisa](#pesquisa) | 1 |
| | **Total** | **40** |

---

## Legenda

| Símbolo | Significado |
|---------|-------------|
| ✅ | Tipo: Funcional |
| ⚙️ | Tipo: Não Funcional |
| 🔴 | Prioridade Alta |
| 🟡 | Prioridade Média |
| 🟢 | Prioridade Baixa |

---

## Home

### TC-001 — Carregamento da Home

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa mtp.com.br em um navegador moderno
Quando  a página carrega completamente
Então   o banner principal é exibido
Então   o menu de navegação está visível
Então   o tempo de carregamento é inferior a 3 segundos
```

### TC-002 — Exibição dos 5 serviços na Home

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está na página inicial
Quando  rola a página até a seção de serviços
Então   os 5 cards de serviço são exibidos: Quality Assurance, Automation, Development Experience, Business Experience e Data Intelligence
```

---

## Navegação

### TC-003 — Navegação via menu — Serviços

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está em qualquer página do site
Quando  passa o mouse sobre o menu 'Serviços'
E       clica em 'Quality Assurance'
Então   o submenu exibe os 5 itens
Então   o usuário é redirecionado para a página correta do serviço
```

### TC-004 — Navegação via menu — Sobre a MTP

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está em qualquer página do site
Quando  passa o mouse sobre 'Sobre a MTP'
E       clica em 'Liderança'
Então   o submenu exibe 'Liderança' e 'Empoderando a mudança'
Então   o usuário é redirecionado para /about-mtp/leadership/
```

### TC-005 — Navegação via menu — Modelos de Entrega

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está em qualquer página do site
Quando  passa o mouse sobre 'Modelos de Entrega'
Então   o submenu exibe: Nossas Soluções, Serviço Profissional Dedicado, Squad Fechado e Modelos Customizados
```

### TC-006 — Link 'Carreiras' no menu

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está em qualquer página do site
Quando  clica em 'Carreiras' no menu principal
Então   o usuário é redirecionado para /career/careers/
```

### TC-007 — Link 'Contato' no menu

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está em qualquer página do site
Quando  clica em 'Contato' no menu principal
Então   o usuário é redirecionado para /contact/
```

### TC-023 — Logo MTP redireciona para Home

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está em qualquer página interna do site
Quando  clica na logo MTP no header
Então   o usuário é redirecionado para mtp.com.br
```

### TC-040 — Página de erro 404

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário acessa uma URL inexistente em mtp.com.br
Quando  digita uma URL inválida (ex: mtp.com.br/pagina-inexistente)
Então   uma página de erro 404 amigável é exibida
Então   o menu de navegação permanece funcional
```

---

## Formulário de Contato

### TC-008 — Envio com campos válidos

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está na página de Contato
Quando  preenche todos os campos obrigatórios com dados válidos
E       marca o checkbox de consentimento e clica em 'Enviar'
Então   mensagem de confirmação de envio bem-sucedido é exibida
```

### TC-009 — Envio sem campos obrigatórios

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está na página de Contato
Quando  deixa todos os campos obrigatórios em branco e clica em 'Enviar'
Então   mensagens de erro são exibidas em cada campo obrigatório
Então   o formulário não é enviado
```

### TC-010 — Validação de e-mail inválido

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está na página de Contato
Quando  insere um e-mail inválido (ex: emailsemarroba)
E       clica em 'Enviar'
Então   mensagem de erro de formato inválido é exibida
Então   o formulário não é submetido
```

### TC-011 — Envio sem consentimento

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário preencheu todos os campos obrigatórios
Quando  não marca o checkbox de consentimento
E       clica em 'Enviar'
Então   o formulário não é enviado
Então   mensagem de erro referente ao consentimento é exibida
```

### TC-012 — Seleção do campo país

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página de Contato
Quando  clica no campo 'Selecionar país'
E       seleciona 'Espanha'
Então   as opções Brasil, Espanha e México estão disponíveis
Então   o valor 'Espanha' permanece selecionado
```

### TC-013 — Seleção do campo assunto

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página de Contato
Quando  clica no campo 'Selecionar assunto'
Então   as opções incluem: Solicitação de Proposta Comercial, Informações, Parcerias, Comentários e Sugestões, Outros assuntos
```

### TC-014 — Seleção de como conheceu a MTP

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟢 **Prioridade:** Baixa

```gherkin
Dado que o usuário está na página de Contato
Quando  clica no campo 'Como conheceu a MTP'
Então   as opções incluem: Indicação, Evento, Google, LinkedIn, Instagram, Facebook
```

### TC-015 — Formulário presente na Home e Liderança

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página Home ou Liderança
Quando  rola até a seção 'Fale Conosco'
Então   o formulário é exibido com os mesmos campos do formulário de /contact/
```

### TC-022 — Link da Política de Privacidade no formulário

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está em qualquer formulário do site
Quando  clica no link 'política de privacidade' no texto de consentimento
Então   o usuário é redirecionado para /privacy-policy/ e a página carrega corretamente
```

---

## Carreiras

### TC-016 — Botão 'Confira nossas vagas' redireciona para Gupy

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está na página /career/careers/
Quando  clica no botão 'Confira nossas vagas'
Então   o usuário é redirecionado para mtpbrasil.gupy.io em nova aba
```

### TC-017 — Exibição dos 5 valores institucionais

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página /career/careers/
Quando  rola a página
Então   os 5 valores são visíveis: Excelência, Transparência, Transformação, Performance e Inovação
```

---

## Liderança

### TC-018 — Exibição das certificações

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página /about-mtp/leadership/
Quando  rola até a seção 'Nossas Certificações'
Então   as certificações são exibidas: GPTW, ISO 9001, ISO 27001, TMMi Level 5, entre outras
```

---

## Contato

### TC-019 — Exibição dos endereços internacionais

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página /contact/
Quando  rola a página
Então   escritórios de Espanha (Madrid, Sevilla, Almería, Alicante) e México (CDMX e Querétaro) são listados corretamente
```

### TC-039 — Links externos (mtp.es e mtpinternational.mx)

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está na página /contact/
Quando  clica nos links mtp.es ou mtpinternational.mx
Então   os sites internacionais abrem corretamente em nova aba
```

---

## Rodapé

### TC-020 — Links de redes sociais

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário está em qualquer página do site
Quando  visualiza o rodapé
E       clica em qualquer ícone de rede social
Então   ícones de LinkedIn, Instagram, Facebook, X e YouTube são visíveis
Então   links abrem em nova aba para o perfil correto
```

### TC-021 — Links institucionais no rodapé

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está no rodapé de qualquer página
Quando  localiza os links institucionais
Então   estão presentes e funcionais: Canal de Ética, Acessibilidade, Fornecedores, Termos de Uso, Política Corporativa, de Segurança, de Cookies e de Privacidade
```

### TC-038 — Links de serviços no rodapé

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está no rodapé de qualquer página
Quando  clica em qualquer link de serviço listado
Então   o usuário é redirecionado para a página correta do serviço sem erro 404
```

---

## Responsividade

### TC-024 — Responsividade — dispositivo móvel (375px)

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa mtp.com.br em dispositivo móvel com viewport de 375px
Quando  navega pelas páginas principais e utiliza o formulário
Então   menu colapsa para hamburguer
Então   conteúdos legíveis sem scroll horizontal
Então   formulários utilizáveis em tela touch
```

### TC-025 — Responsividade — tablet (768px)

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário acessa mtp.com.br em tablet com viewport de 768px
Quando  navega pelas páginas principais
Então   layout se adapta sem quebras visuais
Então   cards de serviço se reorganizam adequadamente
```

---

## Compatibilidade

### TC-026 — Compatibilidade com Google Chrome

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa o site pelo Google Chrome versão atual
Quando  navega pelas páginas e utiliza o formulário
Então   todas as funcionalidades operam corretamente sem erros no console
```

### TC-027 — Compatibilidade com Mozilla Firefox

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário acessa o site pelo Mozilla Firefox versão atual
Quando  navega pelas páginas e utiliza o formulário
Então   todas as funcionalidades operam corretamente sem erros visuais ou funcionais
```

### TC-028 — Compatibilidade com Safari

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário acessa o site pelo Safari em macOS ou iOS
Quando  navega pelas páginas e testa o formulário
Então   layout e funcionalidades se comportam da mesma forma que nos outros navegadores
```

---

## Performance

### TC-029 — LCP — Largest Contentful Paint

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa mtp.com.br em conexão padrão
Quando  a página é carregada
Então   o LCP é inferior a 2,5 segundos (Core Web Vitals)
```

### TC-030 — CLS — Cumulative Layout Shift

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário acessa e rola a página inicial
Quando  os elementos são carregados progressivamente
Então   o CLS é inferior a 0.1 garantindo estabilidade visual
```

---

## Segurança

### TC-031 — HTTPS e certificado SSL

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa http://mtp.com.br (sem HTTPS)
Quando  a requisição é enviada
Então   o usuário é redirecionado para https://
Então   o certificado SSL é válido sem alertas no navegador
```

### TC-032 — Proteção contra submissão automatizada

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que um agente automatizado tenta submeter o formulário via script
Quando  múltiplas submissões são realizadas em sequência sem interação humana
Então   o sistema bloqueia ou dificulta o envio automatizado (CAPTCHA ou rate limiting)
```

---

## Cookies

### TC-033 — Exibição do banner de cookies — 1ª visita

✅ **Tipo:** Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa mtp.com.br pela primeira vez sem cookies salvos
Quando  a página carrega
Então   um banner/modal de consentimento de cookies é exibido
Então   usuário pode aceitar ou recusar cookies não essenciais
```

### TC-034 — Persistência da preferência de cookies

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário aceitou ou recusou os cookies
Quando  fecha e reabre o navegador e retorna para mtp.com.br
Então   o banner não é exibido novamente
Então   a preferência do usuário foi armazenada
```

---

## Acessibilidade

### TC-035 — Navegação por teclado

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🔴 **Prioridade:** Alta

```gherkin
Dado que o usuário acessa o site sem usar mouse
Quando  navega usando apenas Tab e Enter
Então   todos os elementos interativos são acessíveis via teclado
Então   foco visível é claramente indicado
```

### TC-036 — Atributos alt em imagens

⚙️ **Tipo:** Não Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário acessa o site utilizando um leitor de tela
Quando  o leitor percorre as imagens da página
Então   imagens informativas possuem atributo alt descritivo
Então   imagens decorativas possuem alt vazio
```

---

## Pesquisa

### TC-037 — Funcionalidade de busca interna

✅ **Tipo:** Funcional &nbsp;&nbsp; 🟡 **Prioridade:** Média

```gherkin
Dado que o usuário está em qualquer página do site
Quando  clica no campo de pesquisa e digita 'Quality Assurance'
E       pressiona Enter
Então   a página de resultados exibe conteúdos relevantes
Então   resultados sem correspondência exibem mensagem adequada
```

---

