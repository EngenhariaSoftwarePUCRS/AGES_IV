# AGENTS.md

## Contexto do Projeto

- Projeto: Uma Porto Alegre Alemã.
- Objetivo: Website com mapa digital multilíngua para divulgar edificacoes de Theodor Wiederspahn em Porto Alegre.
- Publico-alvo: publico geral (brasileiros e alemaes), incluindo turistas, estudantes, pesquisadores e moradores.
- Escopo funcional principal:
  - Landing page institucional e educativa.
  - Mapa interativo com edificacoes e detalhes.
  - Conteudo detalhado por edificacao e arquiteto.
  - CMS para gestao de conteudo.
  - Analytics de uso.
- Fora de escopo: plataforma de pagamento.
- Diretriz transversal obrigatoria: mobile-first.

## Como o Agente Deve Responder

- Linguagem:
  - US e tarefas de produto em portugues.
  - Detalhes tecnicos podem manter termos de codigo em ingles.
- Estilo:
  - Ser especifico, verificavel e orientado a entrega visivel.
  - Evitar criterios vagos como "melhorar UX" sem medida.
- Ao gerar artefatos:
  - Sempre incluir criterios de aceitacao testaveis.
  - Sempre incluir Depends on em subtasks.
  - Sempre incluir como implementar perto do nivel de arquivo.
  - Sempre incluir como testar.

## Fontes de Verdade no Repositorio

- Regras transversais: docs/Epicos.md.
- Epicos:
  - docs/Epico01_PainelAdministrativo.md
  - docs/Epico02_LandingPage.md
  - docs/Epico03_MapaInterativo.md
  - docs/Epico04_Analytics.md
- Frontend (Next.js + TS): frontend/.

## Template de User Story

Use exatamente este formato:

```md
## USXX - Titulo orientado a ação

**Como** perfil de usuario
**Quero** acao/funcionalidade
**Para** beneficio/valor

**Criterios de Aceitacao**

- Criterio 1, objetivo e testavel.
- Criterio 2, com condicao e resultado esperado.
- Criterio 3, com comportamento em erro/edge case quando aplicavel.
```

Regras obrigatorias:

- Cabecalho: USXX - ... (hifen simples).
- Manter numeracao existente quando editar historias ja criadas.
- Usar verbos como: "deve permitir", "deve exibir", "deve registrar", "deve funcionar".
- Cada criterio deve ser observavel por QA manual e/ou teste automatizado.

## Template de Subtask Frontend

Padrao de ID:

- US14-FE03, US21-FE01, US03-BE02, etc.
- FE = tarefa de frontend.
- BE = tarefa de backend.

Use este formato:

```md
### US14-FE03 - Titulo claro da entrega frontend

**Objetivo**
Descrever a entrega em 1-2 frases.

**Depends on**
- Tasks: IDs de tasks bloqueadoras (ex.: US14-FE01, US14-BE01) ou não incluir item Tasks.
- Pré-requisitos: contratos, endpoints, dados, acessos e decisões técnicas necessárias antes da implementação.

**Criterios de Aceitacao**
- [ ] Criterio funcional 1 com resultado esperado.
- [ ] Criterio funcional 2 com resultado esperado.
- [ ] Criterio mobile-first (viewport pequeno primeiro).
- [ ] Criterio de acessibilidade relevante.
- [ ] Criterio de i18n relevante (pt/de/en), quando houver texto.
- [ ] Criterio de performance relevante, quando houver mapa/3D/lista pesada.

**Como Testar**
1. Escrever/ajustar teste que falha para o comportamento alvo.
2. Implementar o minimo para o teste passar.
3. Refatorar mantendo todos os testes verdes.
4. Validar manualmente no mobile e depois desktop.
5. Registrar evidencias (print, video curto, output de teste).

**Definicao de Pronto**
- Testes da tarefa passam.
- Sem regressao visivel nas rotas impactadas.
- Criterios de aceitacao atendidos e demonstraveis.
```

## Checklist Obrigatório (toda US/tarefa)

- Dependencias (obrigatorio em subtasks):
  - explicitar tasks bloqueadoras por ID;
  - explicitar pre-requisitos tecnicos e/ou de negocio;
  - evitar dependencia vaga como "backend pronto" sem detalhar contrato/endpoint.

- Acessibilidade (A11y):
  - contraste adequado;
  - alternativa textual para imagens/conteudo visual;
  - navegacao por teclado nas funcoes principais;
  - semantica adequada para leitor de tela.
- Internacionalização (i18n):
  - Português, Alemão e Inglês quando houver texto de interface;
  - persistencia de idioma selecionado;
  - indicacao clara do idioma ativo.
- Mobile-first:
  - projetar e validar primeiro em viewport de smartphone;
  - depois expandir para tablet/desktop.
- Performance:
  - evitar bloqueio de renderizacao;
  - lazy-load para conteudo pesado (ex.: mapa, modelos 3D, galerias extensas).
- Analytics:
  - quando houver evento relevante, especificar o que registrar e quando.

## Receitas de Teste por Tipo de Tarefa

UI de secao/pagina:

1. Testar renderizacao do conteudo principal.
2. Testar navegacao por teclado nos elementos interativos.
3. Testar responsividade em largura mobile e desktop.

Navegacao/rotas:

1. Testar caminho feliz (rota valida).
2. Testar caminho invalido (ex.: slug inexistente => fallback adequado).
3. Testar links de ida/volta entre telas relacionadas.

Mapa/interacoes:

1. Testar carregamento inicial e estado de loading.
2. Testar interacao com marcador/popup.
3. Testar filtro/zoom sem degradar usabilidade em mobile.

i18n:

1. Testar troca de idioma e atualizacao de textos.
2. Testar persistencia da escolha ao recarregar.
3. Testar fallback de chave ausente.

Analytics:

1. Testar disparo de evento no gatilho correto.
2. Testar payload minimo esperado.
3. Garantir que falha de analytics nao bloqueia a UX.

## Glossario de Dominio

- Edificação: obra arquitetonica mapeada.
- Centro Histórico: area principal de exploracao do mapa em Porto Alegre.
- Theodor Wiederspahn: arquiteto foco do projeto.
- Popup informativo: resumo rapido da edificacao no mapa.
- Painel administrativo/CMS: gerenciamento de conteudo.

## Regras para Evitar Ambiguidade

Ao escrever US/tarefas, evitar:

- "fazer tela bonita" sem criterios objetivos;
- "otimizar performance" sem meta observavel;
- "melhorar acessibilidade" sem itens concretos.

Preferir:

- comportamento + condicao + resultado esperado;
- referencias de arquivo/rota;
- criterio com validacao manual e/ou automatizada.

## Saidas Esperadas do Agente

Quando solicitado, o agente deve conseguir produzir:

- US completa no formato canonico.
- Quebra de subtasks frontend (ex.: US14-FE03) com:
  - objetivo;
  - depends on;
  - escopo em nivel de arquivo;
  - criterios de aceitacao claros;
  - plano de teste TDD-like;
  - definicao de pronto.
- Plano de implementacao com ordem de entrega mobile-first.
- Trechos de codigo alinhados ao stack atual quando pedido.
