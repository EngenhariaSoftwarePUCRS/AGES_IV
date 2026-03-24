# Épico: Painel Administrativo

O épico **Painel Administrativo** tem como objetivo fornecer aos administradores uma interface para gerenciar as edificações exibidas no mapa e nas páginas de visualização. A ferramenta deve permitir a criação, edição e remoção de edificações, garantindo que o conteúdo esteja sempre atualizado e relevante.

---

## US01 - Gerenciar edificações

**Como** administrador
**Quero** gerenciar as edificações no CMS
**Para** manter atualizado o conteúdo exibido no mapa e nas páginas de visualização.

**Critérios de Aceitação**

O administrador deve poder:

- Criar uma edificação
- Editar uma edificação existente
- Remover uma edificação

Cada edificação deve permitir:

- título
- descrição (RichText)
- autor
- upload de imagens

## US02 - Listar edificações

**Como** administrador
**Quero** visualizar uma lista de edificações cadastradas
**Para** localizar rapidamente uma edificação para gerenciamento.

**Critérios de Aceitação**

- Deve existir uma listagem de edificações
- A listagem deve mostrar:
    - título
    - autor
    - data de criação (opcional)
- Cada item deve possuir ações:
    - editar
    - excluir

## US03 - Gerenciar imagens de edificações

**Como** administrador
**Quero** adicionar e remover imagens associadas a uma edificação
**Para** compor a galeria exibida no frontend.

**Critérios de Aceitação**

- Deve ser possível fazer upload de imagens
- Deve ser possível remover imagens
- As imagens devem ficar vinculadas à edificação

## US04 - Editar conteúdo da landing page

**Como** administrador
**Quero** editar o conteúdo da landing page
**Para** atualizar as informações exibidas aos visitantes.

**Critérios de Aceitação**

O CMS deve permitir editar:

- título principal
- textos institucionais (RichText)
- imagens associadas (se houver)

## US05 - Gerenciar links institucionais

**Como** administrador
**Quero** gerenciar links externos exibidos na landing page
**Para** direcionar usuários para recursos relevantes.

**Critérios de Aceitação**

O administrador deve poder:

- adicionar links
- editar links
- remover links

Cada link deve possuir:

- título
- URL

## US06 - Gerenciar conteúdo da página Sobre

**Como** administrador
**Quero** editar o conteúdo da página Sobre
**Para** manter atualizadas as informações sobre o projeto e o autor em destaque.

**Critérios de Aceitação**

O CMS deve permitir editar:

- texto da página (RichText)
- nome do autor em destaque
- biografia do autor (RichText)
- imagem do autor

## US07 - Autenticação no CMS

**Como** administrador
**Quero** acessar o CMS através de login
**Para** gerenciar o conteúdo do sistema com segurança.

**Critérios de Aceitação**

- Deve existir tela de login
- Apenas usuários autorizados podem acessar o CMS
- Deve ser possível realizar logout
