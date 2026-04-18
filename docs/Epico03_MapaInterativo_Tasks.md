# Tasks do Épico 03 - Mapa Interativo

Este documento detalha subtasks frontend para todas as US do Épico 03, com foco mobile-first, critérios testáveis e escopo de implementação em nível de arquivo.

## US14 - Visualizar mapa das edificações no Centro Histórico

### US14-FE01 - Estruturar página base do mapa com foco no Centro Histórico

**Objetivo**
Criar a página principal do mapa com layout responsivo e estado inicial centralizado no Centro Histórico de Porto Alegre.

**Critérios de Aceitação**
- [ ] A rota /mapa deve renderizar o mapa com centro inicial no Centro Histórico.
- [ ] O layout deve priorizar viewport mobile e expandir corretamente para tablet/desktop.
- [ ] O mapa deve exibir estado de carregamento visível antes da inicialização completa.
- [ ] O contraste entre fundo, controles e textos do mapa deve ser legível em condições normais de uso.
- [ ] Textos de interface da página devem estar preparados para i18n (pt/de/en) via chaves de tradução.
- [ ] A renderização inicial não deve bloquear a interação básica da página.

**Como Testar**
1. Escrever teste de renderização da rota /mapa verificando container e estado de loading.
2. Implementar centro inicial e zoom mínimo para o mapa.
3. Refatorar componente para separar configuração de mapa e layout.
4. Validar manualmente em viewport mobile (390x844) e depois desktop.
5. Registrar evidências com print da centralização e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US14-FE02 - Carregar edificações cadastradas no mapa

**Objetivo**
Integrar dados de edificações para plotar pontos no mapa assim que os dados estiverem disponíveis.

**Critérios de Aceitação**
- [ ] Cada edificação com coordenada válida deve aparecer no mapa.
- [ ] Caso não haja coordenadas, o sistema deve manter o mapa funcional e exibir feedback de dados indisponíveis.
- [ ] O carregamento dos dados não deve travar a navegação da página.
- [ ] A leitura visual dos pontos deve manter contraste adequado em mobile.
- [ ] Labels ou textos auxiliares devem estar preparados para i18n.
- [ ] A renderização de pontos deve manter desempenho aceitável em redes móveis comuns.

**Como Testar**
1. Escrever teste para validar quantidade de pontos renderizados conforme dados mockados.
2. Implementar mapeamento de edifícios para camada de pontos.
3. Refatorar para isolar transformação de dados em função utilitária.
4. Validar manualmente cenários com dados completos e sem coordenadas em mobile.
5. Registrar evidências com print do mapa populado e resultado de teste.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US15 - Identificar edificações no mapa

### US15-FE01 - Renderizar marcadores acessíveis para cada edificação

**Objetivo**
Exibir marcadores claros e distinguíveis para todas as edificações georreferenciadas.

**Critérios de Aceitação**
- [ ] Cada edificação com coordenada deve possuir um marcador visível.
- [ ] Marcadores devem possuir ícones distinguíveis em fundo claro e escuro.
- [ ] Cada marcador deve ter nome acessível via aria-label equivalente.
- [ ] O tamanho do marcador deve ser adequado para toque em mobile.
- [ ] Elementos textuais de apoio devem suportar i18n.
- [ ] A renderização de marcadores não deve degradar o uso em lote moderado de pontos.

**Como Testar**
1. Escrever teste para validar aria-label e quantidade de marcadores.
2. Implementar componente map-markers com props tipadas.
3. Refatorar para separar lógica de ícone por categoria/tipo.
4. Validar manualmente interação por toque e mouse.
5. Registrar evidências com print e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US15-FE02 - Habilitar interação desktop/mobile sobre marcadores

**Objetivo**
Garantir que hover/click no desktop e toque no mobile permitam interação consistente com cada marcador.

**Critérios de Aceitação**
- [ ] No desktop, o marcador deve responder a hover e click.
- [ ] No mobile, o marcador deve responder a toque sem exigir double-tap.
- [ ] O estado ativo deve ser perceptível visualmente e por leitor de tela quando aplicável.
- [ ] A ordem de foco por teclado deve incluir marcadores interativos principais.
- [ ] Mensagens de feedback devem estar preparadas para i18n.
- [ ] A interação não deve introduzir latência perceptível no uso normal.

**Como Testar**
1. Escrever testes de eventos para click e touch no marcador.
2. Implementar estado de marcador ativo e handlers.
3. Refatorar para remover duplicação de comportamento entre desktop e mobile.
4. Validar manualmente em device touch e navegador desktop.
5. Registrar evidências com vídeo curto da interação.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US16 - Navegar livremente pelo mapa

### US16-FE01 - Habilitar pan, zoom e controles mobile

**Objetivo**
Permitir navegação fluida no mapa por arraste, controles de zoom e gesto de pinça no mobile.

**Critérios de Aceitação**
- [ ] O usuário deve conseguir mover o mapa por arraste.
- [ ] O usuário deve aplicar zoom via controles e gesto de pinça no mobile.
- [ ] Os controles de zoom devem ter alvo de toque adequado para mobile.
- [ ] Controles devem ser navegáveis por teclado e rotulados para leitor de tela.
- [ ] Rótulos dos controles devem suportar i18n.
- [ ] A navegação deve manter desempenho aceitável durante pan/zoom contínuo.

**Como Testar**
1. Escrever teste para renderização e acionamento dos controles de zoom.
2. Implementar pan/zoom e limites de escala.
3. Refatorar para encapsular controles em componente próprio.
4. Validar manualmente gesto de pinça em dispositivo móvel.
5. Registrar evidências com print dos níveis de zoom e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US16-FE02 - Assegurar navegação acessível e estável durante uso prolongado

**Objetivo**
Garantir consistência de navegação, incluindo usabilidade por teclado e estabilidade visual durante interações repetidas.

**Critérios de Aceitação**
- [ ] O foco por teclado deve acessar controles principais de navegação do mapa.
- [ ] O uso prolongado de pan/zoom não deve quebrar layout em mobile.
- [ ] O mapa deve preservar fluidez em cenários comuns de navegação.
- [ ] Deve haver alternativa textual para controles iconográficos.
- [ ] Textos de instruções e labels devem suportar i18n.
- [ ] Monitoramento local de eventos não deve impactar a UX.

**Como Testar**
1. Escrever teste de navegação por teclado nos controles do mapa.
2. Implementar melhorias de acessibilidade e otimização de rerender.
3. Refatorar handlers para memorizar callbacks críticos.
4. Validar manualmente com ciclos repetidos de pan/zoom em mobile.
5. Registrar evidências com checklist de a11y e resultado de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US17 - Visualizar informações rápidas da edificação

### US17-FE01 - Implementar popup informativo com dados essenciais

**Objetivo**
Exibir popup ao interagir com marcador contendo nome, imagem e descrição breve da edificação.

**Critérios de Aceitação**
- [ ] Ao clicar/tocar no marcador, um popup deve abrir com nome, imagem e breve descrição.
- [ ] O popup deve exibir fallback quando imagem estiver indisponível.
- [ ] Conteúdo do popup deve ser legível em viewport mobile sem cortar informação crítica.
- [ ] Conteúdo textual do popup deve ser compatível com leitor de tela.
- [ ] Textos e labels do popup devem suportar i18n.
- [ ] O carregamento de imagem no popup não deve bloquear a interação do mapa.

**Como Testar**
1. Escrever teste para abertura do popup e validação dos campos obrigatórios.
2. Implementar componente building-popup e integração com marcador ativo.
3. Refatorar para isolar fallback de imagem e texto.
4. Validar manualmente popup em mobile e desktop.
5. Registrar evidências com print do popup e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US17-FE02 - Incluir CTA para página detalhada dentro do popup

**Objetivo**
Adicionar ação clara no popup para abrir a página detalhada da edificação sem fricção.

**Critérios de Aceitação**
- [ ] O popup deve possuir CTA claro para abrir detalhes da edificação.
- [ ] O link deve navegar corretamente para a rota de detalhe correspondente.
- [ ] O CTA deve ser navegável por teclado e possuir nome acessível.
- [ ] Em mobile, o CTA deve manter área de toque adequada.
- [ ] Rótulo do CTA deve suportar i18n.
- [ ] A navegação via CTA não deve gerar bloqueio perceptível.

**Como Testar**
1. Escrever teste para verificar href correto do CTA por slug.
2. Implementar CTA no popup com Link do Next.js.
3. Refatorar para extrair função de construção de rota.
4. Validar manualmente ida/volta entre mapa e detalhe em mobile.
5. Registrar evidências com vídeo curto do fluxo.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US18 - Acessar página detalhada da edificação

### US18-FE01 - Completar painel de detalhe com dados históricos e arquitetônicos

**Objetivo**
Expandir página de detalhe para exibir nome, histórico, imagens e descrição arquitetônica da edificação.

**Critérios de Aceitação**
- [ ] A página de detalhe deve exibir campos completos da edificação selecionada.
- [ ] Em slug inválido, o sistema deve aplicar fallback adequado.
- [ ] As imagens da página devem conter texto alternativo.
- [ ] A leitura dos blocos de conteúdo deve ser confortável em mobile.
- [ ] Títulos e rótulos devem suportar i18n.
- [ ] O carregamento da página não deve degradar perceptivelmente com conteúdo médio.

**Como Testar**
1. Escrever teste para caminho feliz (slug válido) e inválido (fallback).
2. Implementar seções faltantes no building-detail-panel.
3. Refatorar mapeamento de dados para reduzir condições espalhadas.
4. Validar manualmente leitura e rolagem em mobile.
5. Registrar evidências com print da página e testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US18-FE02 - Incluir navegação de retorno para o mapa

**Objetivo**
Permitir retorno fácil para o mapa a partir da página de detalhe sem perda de contexto principal.

**Critérios de Aceitação**
- [ ] A página de detalhe deve exibir ação de retorno ao mapa.
- [ ] O retorno deve funcionar em mobile e desktop.
- [ ] O elemento de retorno deve ter label acessível e foco visível.
- [ ] O texto do retorno deve suportar i18n.
- [ ] O fluxo ida/volta não deve quebrar navegação principal.
- [ ] O retorno não deve provocar recarga desnecessária de recursos pesados.

**Como Testar**
1. Escrever teste de navegação para ida via popup e volta para /mapa.
2. Implementar botão/link de retorno com roteamento consistente.
3. Refatorar utilitário de query params de navegação.
4. Validar manualmente fluxo completo em viewport mobile.
5. Registrar evidências com vídeo curto e logs de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US19 - Acessar materiais e modelos tridimensionais das edificações

### US19-FE01 - Criar seção de materiais adicionais na página da edificação

**Objetivo**
Disponibilizar seção organizada para plantas, documentos e análises quando o conteúdo existir.

**Critérios de Aceitação**
- [ ] A página da edificação deve exibir seção de materiais quando houver conteúdo.
- [ ] Tipos de material (planta, documento, análise) devem ser identificados visualmente e textualmente.
- [ ] Em ausência de material, o sistema deve exibir estado vazio claro sem quebrar layout.
- [ ] Elementos da seção devem ser acessíveis por teclado.
- [ ] Rótulos e mensagens da seção devem suportar i18n.
- [ ] A presença da seção não deve impactar o carregamento inicial da página.

**Como Testar**
1. Escrever teste para cenário com materiais e sem materiais.
2. Implementar componente de materiais e integração no painel de detalhe.
3. Refatorar para reutilizar renderer por tipo de item.
4. Validar manualmente renderização em mobile e desktop.
5. Registrar evidências com print dos dois cenários e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US19-FE02 - Habilitar carregamento sob demanda para modelos 3D e conteúdo pesado

**Objetivo**
Implementar estratégia de lazy-load para modelos tridimensionais e outros conteúdos de alto custo.

**Critérios de Aceitação**
- [ ] Conteúdos 3D devem carregar somente sob ação explícita do usuário.
- [ ] Enquanto carrega, deve existir feedback visual de progresso.
- [ ] Em falha de carregamento, deve haver mensagem amigável e fluxo alternativo.
- [ ] Controles do viewer devem possuir rótulos acessíveis.
- [ ] Textos do viewer e mensagens de erro devem suportar i18n.
- [ ] O lazy-load deve reduzir impacto no tempo inicial de carregamento da rota.

**Como Testar**
1. Escrever teste para garantir que viewer não renderiza antes da ação do usuário.
2. Implementar dynamic import e estado de loading/erro.
3. Refatorar fallback para componente reutilizável.
4. Validar manualmente em rede simulada lenta no mobile.
5. Registrar evidências com vídeo curto e comparação de carga inicial.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US20 - Filtrar edificações no mapa

### US20-FE01 - Implementar UI de filtros no mapa

**Objetivo**
Criar painel de filtros simples e intuitivo para controlar visibilidade de conjuntos de edificações.

**Critérios de Aceitação**
- [ ] O usuário deve conseguir ativar e desativar filtros no mapa.
- [ ] A interface de filtro deve ser compreensível em mobile sem poluição visual.
- [ ] O estado ativo de filtros deve estar claramente indicado.
- [ ] O painel deve ser navegável por teclado e possuir labels acessíveis.
- [ ] Textos de filtro devem suportar i18n.
- [ ] A abertura/fechamento do painel não deve comprometer desempenho.

**Como Testar**
1. Escrever teste para alternância de filtros e atualização de estado.
2. Implementar componente map-filters e conectar ao mapa.
3. Refatorar para separar estado de filtro em hook dedicado.
4. Validar manualmente usabilidade do painel em mobile.
5. Registrar evidências com print do painel e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US20-FE02 - Aplicar filtros na camada de marcadores

**Objetivo**
Fazer com que os filtros impactem diretamente a exibição dos marcadores no mapa.

**Critérios de Aceitação**
- [ ] Ao ativar filtro, apenas marcadores correspondentes devem permanecer visíveis.
- [ ] Ao remover filtro, o conjunto completo deve voltar a aparecer.
- [ ] O comportamento de filtro deve funcionar em mobile e desktop.
- [ ] Deve haver feedback textual de quantidade de resultados para acessibilidade.
- [ ] Mensagens de resultado devem suportar i18n.
- [ ] A aplicação de filtros deve manter tempo de resposta adequado.

**Como Testar**
1. Escrever teste para validar filtragem por categoria e reset.
2. Implementar hook de filtros com memoização.
3. Refatorar para reutilizar predicados de filtro em testes.
4. Validar manualmente cenários de filtro combinado em mobile.
5. Registrar evidências com print antes/depois e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US21 - Utilizar o site em múltiplos idiomas

### US21-FE01 - Estruturar provider de idioma global

**Objetivo**
Criar base de internacionalização para suportar português, alemão e inglês no fluxo de mapa e edificações.

**Critérios de Aceitação**
- [ ] O sistema deve permitir alternar idioma entre pt/de/en.
- [ ] A mudança de idioma deve atualizar textos renderizados sem recarregar página.
- [ ] O provider deve ser compatível com navegação mobile-first.
- [ ] O seletor de idioma deve ter rótulos acessíveis e foco visível.
- [ ] O idioma ativo deve estar claramente indicado na interface.
- [ ] A adição do provider não deve degradar a performance global do app.

**Como Testar**
1. Escrever teste para troca de idioma e re-render de texto.
2. Implementar provider e integrar no layout global.
3. Refatorar interface de mensagens para tipagem segura.
4. Validar manualmente troca de idioma em mobile e desktop.
5. Registrar evidências com vídeo curto e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US21-FE02 - Persistir idioma e detectar preferência do navegador

**Objetivo**
Manter idioma selecionado entre sessões e aplicar detecção automática quando o usuário ainda não escolheu manualmente.

**Critérios de Aceitação**
- [ ] O idioma selecionado deve persistir após recarregar a página.
- [ ] Na primeira visita sem preferência salva, o idioma deve seguir preferência do navegador com fallback.
- [ ] O usuário deve conseguir sobrescrever o idioma detectado automaticamente.
- [ ] O comportamento deve funcionar em mobile e desktop.
- [ ] O fluxo de persistência deve ser acessível e transparente ao usuário.
- [ ] A leitura/escrita de preferência não deve bloquear renderização inicial.

**Como Testar**
1. Escrever teste para inicialização com idioma salvo e sem idioma salvo.
2. Implementar hook de persistência e detecção.
3. Refatorar funções de fallback para cobertura de idiomas não suportados.
4. Validar manualmente recarga de página e manutenção do idioma.
5. Registrar evidências com prints de cenários e resultado dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US21-FE03 - Internacionalizar textos de mapa e detalhe de edificação

**Objetivo**
Aplicar i18n em todos os textos de interface das rotas e componentes impactados por Epico03.

**Critérios de Aceitação**
- [ ] Conteúdo textual da experiência de mapa e detalhe deve alternar corretamente entre pt/de/en.
- [ ] Chaves ausentes devem usar fallback controlado sem quebrar UI.
- [ ] O idioma ativo deve refletir imediatamente em popup e página de detalhe.
- [ ] A navegação por teclado e leitores de tela deve continuar funcional após internacionalização.
- [ ] O idioma ativo deve permanecer consistente durante toda a navegação.
- [ ] A internacionalização não deve introduzir regressão perceptível de desempenho.

**Como Testar**
1. Escrever testes para renderização por idioma e fallback de chave ausente.
2. Implementar substituição de strings por dicionários de i18n.
3. Refatorar para consolidar chaves por domínio (mapa, detalhe, filtros).
4. Validar manualmente troca de idioma em fluxo completo.
5. Registrar evidências com prints em 3 idiomas e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US22 - Localizar minha posição no mapa

### US22-FE01 - Implementar geolocalização com permissão e fallback seguro

**Objetivo**
Adicionar recurso de localização atual do usuário com tratamento de permissão negada sem quebrar o mapa.

**Critérios de Aceitação**
- [ ] O sistema deve solicitar permissão de geolocalização ao usuário.
- [ ] Se autorizado, o mapa deve exibir indicador visual da localização aproximada.
- [ ] Se negado, o mapa deve continuar funcional sem erro bloqueante.
- [ ] Mensagens de estado devem ser acessíveis e legíveis em mobile.
- [ ] Mensagens de geolocalização devem suportar i18n.
- [ ] A consulta de geolocalização não deve comprometer desempenho geral da rota.

**Como Testar**
1. Escrever testes com mock de geolocation para sucesso e negação.
2. Implementar hook e indicador visual no mapa.
3. Refatorar estados de erro/sucesso para componente dedicado.
4. Validar manualmente permissão concedida e negada em mobile.
5. Registrar evidências com prints dos dois cenários e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US23 - Abrir rota para visitar uma edificação

### US23-FE01 - Adicionar ação de abrir rota externa por coordenadas

**Objetivo**
Permitir abertura de rota para uma edificação em aplicativo de navegação externo, a partir do popup e/ou detalhe.

**Critérios de Aceitação**
- [ ] Deve existir opção de abrir rota no popup e/ou detalhe da edificação.
- [ ] O link de rota deve usar coordenadas corretas da edificação.
- [ ] O comportamento deve funcionar em dispositivos móveis e desktop.
- [ ] O botão/link deve possuir nome acessível para leitor de tela.
- [ ] Rótulos da ação devem suportar i18n.
- [ ] A abertura da rota não deve bloquear a interação restante da página.

**Como Testar**
1. Escrever teste para validar URL de navegação gerada por coordenadas.
2. Implementar botões de rota em popup e detalhe.
3. Refatorar geração de URL em utilitário único.
4. Validar manualmente abertura do link em mobile e desktop.
5. Registrar evidências com prints e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US24 - Abrir o mapa a partir de um QR Code ?

### US24-FE01 - Suportar deep link para foco em edificação via parâmetro

**Objetivo**
Permitir que links de QR Code abram /mapa com foco automático na edificação correspondente.

**Critérios de Aceitação**
- [ ] Link com parâmetro de edificação deve abrir mapa focado no alvo correspondente.
- [ ] Em parâmetro inválido, o mapa deve abrir normalmente sem quebra da experiência.
- [ ] O comportamento deve funcionar em navegadores móveis comuns.
- [ ] Deve haver feedback acessível quando deep link não encontrar edificação.
- [ ] Mensagens de feedback devem suportar i18n.
- [ ] O processamento do parâmetro não deve impactar perceptivelmente o carregamento inicial.

**Como Testar**
1. Escrever testes para parâmetro válido, inválido e ausente.
2. Implementar leitura de query param e foco no marcador.
3. Refatorar função de resolução de slug para utilitário testável.
4. Validar manualmente abertura via URL em celular.
5. Registrar evidências com vídeo curto e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US24-FE02 - Exibir popup/destaque automático após abertura por QR Code

**Objetivo**
Ao abrir via deep link, destacar visualmente a edificação e apresentar popup informativo automaticamente.

**Critérios de Aceitação**
- [ ] Ao abrir por QR Code válido, a edificação deve ser destacada automaticamente.
- [ ] O popup informativo deve abrir sem interação manual adicional.
- [ ] O destaque deve ser perceptível em mobile e desktop.
- [ ] A leitura do popup automático deve manter compatibilidade com leitor de tela.
- [ ] Mensagens e CTA do popup devem suportar i18n.
- [ ] A automação não deve provocar travamentos no carregamento do mapa.

**Como Testar**
1. Escrever teste para abertura automática de popup via parâmetro.
2. Implementar destaque e ação automática no estado de interação.
3. Refatorar para evitar acionar abertura automática mais de uma vez.
4. Validar manualmente com links de QR em mobile e desktop.
5. Registrar evidências com vídeo curto e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

## US34 - Acessar página detalhada de um arquiteto

### US34-FE01 - Criar rota e página de detalhe do arquiteto

**Objetivo**
Implementar página dedicada de arquiteto com informações profissionais e biográficas, com layout responsivo.

**Critérios de Aceitação**
- [ ] A página de arquiteto deve exibir informações biográficas e profissionais.
- [ ] O layout deve ser responsivo e priorizar mobile-first.
- [ ] A página deve possuir semântica adequada de headings e landmarks.
- [ ] Imagens do arquiteto e conteúdos visuais devem possuir alt text.
- [ ] Textos da página devem suportar i18n (pt/de/en).
- [ ] A rota não deve introduzir regressão de desempenho perceptível.

**Como Testar**
1. Escrever teste para rota válida e fallback para slug inválido.
2. Implementar página dinâmica e painel de detalhe.
3. Refatorar dados do arquiteto para tipagem consistente.
4. Validar manualmente leitura da página em mobile e desktop.
5. Registrar evidências com print da página e output de testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.

### US34-FE02 - Integrar link para arquiteto a partir da página da edificação

**Objetivo**
Conectar página de detalhe da edificação com página de detalhe do arquiteto e listar obras relevantes.

**Critérios de Aceitação**
- [ ] Deve existir link para página do arquiteto na página de detalhe da edificação.
- [ ] A página do arquiteto deve listar obras relevantes com navegação funcional.
- [ ] O fluxo edificação -> arquiteto deve funcionar em mobile e desktop.
- [ ] Links e títulos devem ser acessíveis por teclado e leitor de tela.
- [ ] Rótulos e seções devem suportar i18n.
- [ ] A integração não deve causar regressão em rotas de edificação.

**Como Testar**
1. Escrever teste para renderização do link de arquiteto e navegação entre rotas.
2. Implementar relação entre building e architect slug.
3. Refatorar componentes para evitar duplicação de cards de obras.
4. Validar manualmente fluxo de navegação completo em mobile.
5. Registrar evidências com vídeo curto e output dos testes.

**Definição de Pronto**
- Testes da tarefa passam.
- Não afeta rotas já existentes.
- Critérios de aceitação atendidos e demonstráveis.
