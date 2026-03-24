# Épico: Mapa Interativo

O épico **Mapa Interativo** tem como objetivo permitir que visitantes explorem as obras do arquiteto alemão Theodor Wiederspahn localizadas principalmente no **Centro Histórico de Porto Alegre**, através de um mapa digital interativo, com informações culturais, históricas e arquitetônicas acessíveis ao público geral.

A ferramenta deve ser amigável para turistas, estudantes, pesquisadores e moradores da cidade, com suporte multilíngue e foco em educação patrimonial.

---

## US14 - Visualizar mapa das edificações no Centro Histórico

**Como** visitante do site
**Quero** visualizar um mapa interativo de Porto Alegre destacando as edificações de Theodor Wiederspahn no Centro Histórico
**Para** entender onde estão localizadas e explorar a relação delas com a cidade.

**Critérios de Aceitação**

- O sistema deve exibir um mapa interativo centralizado inicialmente no Centro Histórico de Porto Alegre.
- O mapa deve carregar as localizações das edificações cadastradas.
- O carregamento do mapa deve ocorrer em tempo aceitável em redes móveis comuns.
- O mapa deve funcionar tanto em desktop quanto em dispositivos móveis.
- Elementos do mapa devem possuir contraste adequado para facilitar a visualização por usuários com baixa visão.

---

## US15 - Identificar edificações no mapa

**Como** visitante
**Quero** ver marcadores ou ícones no mapa representando cada edifício
**Para** reconhecer facilmente os pontos de interesse arquitetônico.

**Critérios de Aceitação**

- Cada edificação cadastrada deve possuir um marcador visível no mapa.
- Os marcadores devem possuir ícones claros e distinguíveis.
- Ao passar o cursor (desktop) ou tocar (mobile) no marcador, o sistema deve permitir interação com ele.
- Marcadores devem possuir descrição acessível (aria-label ou equivalente) para leitores de tela.

---

## US16 - Navegar livremente pelo mapa

**Como** visitante
**Quero** poder mover o mapa e aplicar zoom
**Para** explorar diferentes regiões da cidade e visualizar melhor as edificações.

**Critérios de Aceitação**

- O usuário deve conseguir mover o mapa arrastando-o.
- O usuário deve conseguir aplicar zoom utilizando controles do mapa ou gestos de pinça no mobile.
- O mapa deve manter desempenho aceitável durante navegação.
- O sistema deve permitir navegação básica por teclado quando possível (ex.: controles de zoom acessíveis).

---

## US17 - Visualizar informações rápidas da edificação

**Como** visitante
**Quero** clicar em um marcador no mapa e visualizar um resumo da edificação (nome, imagem e breve descrição)
**Para** entender rapidamente o que representa aquele prédio.

**Critérios de Aceitação**

- Ao clicar ou tocar em um marcador, deve abrir um popup informativo.
- O popup deve exibir pelo menos:
  - nome da edificação
  - imagem representativa
  - breve descrição
- O popup deve possuir botão ou link para acessar a página detalhada.
- O conteúdo textual deve ser compatível com leitores de tela.

---

## US18 - Acessar página detalhada da edificação

**Como** visitante
**Quero** acessar uma página com informações completas sobre uma edificação selecionada
**Para** conhecer seu histórico, características arquitetônicas e relevância cultural.

**Critérios de Aceitação**

- A partir do popup ou da lista de edificações, o usuário deve conseguir abrir uma página dedicada.
- A página deve apresentar:
  - nome da edificação
  - histórico
  - imagens
  - descrição arquitetônica
- A navegação de retorno ao mapa deve estar disponível.
- As imagens devem possuir texto alternativo (alt text).

---

## US19 - Acessar materiais e modelos tridimensionais das edificações

**Como** visitante interessado em arquitetura ou história
**Quero** acessar conteúdos mais detalhados como plantas, documentos, análises arquitetônicas e visualizar modelos tridimensionais das edificações quando disponíveis
**Para** compreender melhor sua forma, estrutura arquitetônica e aprofundar meu conhecimento sobre a edificação.

**Critérios de Aceitação**

- A página da edificação deve permitir acessar materiais adicionais quando disponíveis.
- Materiais podem incluir:
  - plantas arquitetônicas
  - documentos históricos
  - análises arquitetônicas
  - modelos tridimensionais
- Conteúdos pesados devem carregar sob demanda para preservar desempenho.

---

## US20 - Filtrar edificações no mapa

**Como** visitante
**Quero** aplicar filtros ou camadas no mapa
**Para** visualizar diferentes conjuntos de edificações ou percursos arquitetônicos.

**Critérios de Aceitação**

- O sistema deve permitir aplicar filtros ou camadas no mapa.
- Ao ativar um filtro, apenas os marcadores correspondentes devem permanecer visíveis.
- A interface de filtros deve ser simples e intuitiva.
- Filtros devem ser utilizáveis tanto em desktop quanto em mobile.

---

## US21 - Utilizar o site em múltiplos idiomas

**Como** visitante internacional
**Quero** visualizar o conteúdo do mapa e das edificações em português, alemão e inglês
**Para** compreender as informações no meu idioma.

**Critérios de Aceitação**

- O sistema deve permitir alternar entre os idiomas:
  - Português
  - Alemão
  - Inglês
- O idioma selecionado deve atualizar todo o conteúdo textual disponível.
- O idioma selecionado deve permanecer ativo durante toda a navegação do usuário e ser armazenado para visitas futuras.
- O idioma deve ser detectado automaticamente com base nas preferências do navegador, mas o usuário deve poder alterar manualmente.
- Elementos de interface devem indicar claramente o idioma selecionado.

---

## US22 - Localizar minha posição no mapa

**Como** visitante utilizando o celular
**Quero** visualizar minha localização atual no mapa
**Para** entender quais edificações estão próximas de mim.

**Critérios de Aceitação**

- O sistema deve solicitar permissão de geolocalização ao usuário.
- Caso autorizado, o mapa deve exibir a posição aproximada do usuário.
- A localização deve ser indicada visualmente no mapa.
- Caso a localização não seja permitida, o sistema deve continuar funcionando normalmente.

---

## US23 - Abrir rota para visitar uma edificação

**Como** visitante
**Quero** abrir a localização de uma edificação em um aplicativo de navegação
**Para** poder visitá-la fisicamente.

**Critérios de Aceitação**

- Na página da edificação ou no popup deve existir opção de abrir rota.
- O sistema deve permitir abrir a rota em aplicativo de navegação (ex.: Google Maps).
- O link deve funcionar em dispositivos móveis e desktop.
- A rota deve utilizar as coordenadas da edificação cadastrada.

---

## US24 - Abrir o mapa a partir de um QR Code ?

**Como** visitante em um ponto físico da cidade
**Quero** escanear um QR Code e abrir o mapa já focado na edificação correspondente
**Para** acessar rapidamente informações sobre o prédio que estou visitando.

**Critérios de Aceitação**

- Um QR Code associado a uma edificação deve direcionar o usuário para o site.
- Ao abrir o link, o mapa deve carregar já focado na edificação correspondente.
- Um popup ou destaque visual da edificação deve ser exibido automaticamente.
- O funcionamento deve ser compatível com navegadores móveis comuns.

---

## US34 - Acessar página detalhada de um arquiteto

**Como** visitante interessado em arquitetura
**Quero** acessar uma página com informações sobre o arquiteto responsável pela edificação selecionada
**Para** conhecer melhor o profissional por trás da obra e sua relevância histórica.

**Critérios de Aceitação**

- A página de detalhes do arquiteto deve exibir informações profissionais e biográficas.
- Deve haver uma seção com as obras mais relevantes do arquiteto.
- A página deve ser acessível via link a partir da página de detalhes da edificação.
- O design deve ser responsivo e compatível com dispositivos móveis.

