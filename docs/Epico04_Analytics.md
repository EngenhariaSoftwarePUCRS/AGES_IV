# Épico: Analytics

O épico **Analytics** tem como objetivo coletar e disponibilizar dados de uso do sistema para a análise do comportamento e do engajamento dos visitantes no site.

---

## US25 - Coletar dados de acesso ao site

**Como** administrador
**Quero** que o sistema registre acessos às páginas do site
**Para** acompanhar o volume de visitantes nas páginas do site.

**Critérios de Aceitação**

- O sistema deve registrar visualizações de páginas.
- O registro deve ocorrer automaticamente ao carregar uma página.
- O registro não deve afetar o tempo de carregamento da página.
- Cada registro deve armazenar:
  - data e hora
  - página acessada

---

## US26 - Registrar interação com edificações

**Como** administrador
**Quero** registrar quando usuários interagem com edificações
**Para** identificar quais prédios possuem mais interesse.

**Critérios de Aceitação**

- Os registros devem permitir identificar as edificações mais acessadas.
- O registro deve ocorrer sem impactar negativamente o desempenho do mapa.
- O sistema deve registrar eventos quando:
  - um marcador de edificação é clicado
  - uma página de uma edificação é aberta
- O evento deve armazenar:
  - data e hora
  - identificador da edificação

---

## US27 - Registrar uso das funcionalidades do mapa

**Como** administrador
**Quero** registrar o uso de funcionalidades do mapa
**Para** entender como os visitantes exploram o mapa.

**Critérios de Aceitação**

- O sistema deve registrar eventos quando o usuário:
  - utiliza filtros
  - solicita rota para uma edificação
- Cada evento deve registrar:
  - data e hora
  - tipo de funcionalidade utilizada

---

## US28 - Registrar idioma utilizado pelos visitantes

**Como** administrador
**Quero** registrar qual idioma os visitantes utilizam ao navegar no site
**Para** entender o perfil do público e avaliar o uso multilíngue.

**Critérios de Aceitação**

- O sistema deve registrar o idioma ativo durante a navegação.
- O registro deve ocorrer:
  - ao carregar uma página
  - quando o usuário alterar o idioma

---

## US29 - Identificar origem de acesso ao site

**Como** administrador
**Quero** identificar de onde os usuários acessam o site
**Para** compreender como os visitantes chegam até o site ou mapa.

**Critérios de Aceitação**

- O sistema deve registrar a origem do acesso quando disponível.
- A origem pode incluir:
  - acesso direto
  - link externo
  - QR Code
- Cada registro deve armazenar:
  - data e hora
  - página inicial visitada

---

## US30 - Armazenar histórico de analytics

**Como** administrador
**Quero** manter histórico dos dados analíticos
**Para** analisar a evolução do uso do site ao longo do tempo.

**Critérios de Aceitação**

- Os dados de analytics devem ser armazenados de forma persistente.
- O sistema deve permitir consultas históricas de métricas.
- O sistema deve permitir consultas por intervalo de datas.

---

## US31 - Gerar ranking de edificações mais visualizadas

**Como** administrador
**Quero** visualizar um ranking das edificações mais acessadas
**Para** identificar quais edificações possuem maior interesse dos visitantes.

**Critérios de Aceitação**

- O sistema deve gerar um ranking baseado nos acessos registrados.
- O ranking deve considerar:
  - visualizações da página da edificação
  - interações com marcadores no mapa
- O ranking deve mostrar:
  - nome da edificação
  - número de visualizações
- Deve ser possível visualizar o ranking por período (ex.: 7 dias, 30 dias, total).

---

## US32 - Exportar dados de analytics

**Como** administrador
**Quero** exportar dados de analytics
**Para** utilizá-los em análises externas.

**Critérios de Aceitação**

- O sistema deve permitir exportar dados analíticos.
- A exportação deve incluir métricas como:
  - acessos ao site
  - interações com edificações
  - uso de funcionalidades do mapa
  - registro de idioma utilizado
  - origem de acessos do site e do mapa
- O formato de exportação pode ser:
  - CSV
  - JSON
  - XLS
---

## US33 - Visualizar métricas básicas no CMS

**Como** administrador
**Quero** visualizar métricas de uso do site dentro do CMS
**Para** acompanhar o engajamento de visitantes.

**Critérios de Aceitação**

- O CMS deve possuir uma página de analytics.
- A página deve apresentar:
  - número total de visitas
  - páginas mais acessadas
  - edificações mais acessadas
- As métricas devem poder ser visualizadas por período (ex.: 7, 30 ou total).
