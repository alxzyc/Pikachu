# EcoDescarte (Pikachu)

Projeto de interface web para incentivar o descarte correto de eletrônicos.

## Melhorias aplicadas

- Tela de login criada e definida como tela principal.
- Tela principal ajustada para abrir diretamente na Home com vídeo educativo.
- Login com visual mais atrativo usando slideshow de imagens de fundo.
- Navegação do app liberada apenas após login e opção de logout no perfil.
- Filtros de pontos de coleta com busca em tempo real.
- Correções de UX/acessibilidade (focus visível, `aria-*`, estados de menu).
- Correções de lógica no perfil:
  - validação de email;
  - persistência segura no `localStorage`;
  - tratamento de dados corrompidos.
- Texto da página de informações expandido, mais claro e educativo.
- Embed de vídeo atualizado (`youtube-nocookie`) com permissões de reprodução para evitar falhas de carregamento.

## Explicação detalhada do código (para apresentação do trabalho)

### 1) Estrutura HTML

- `header`: barra superior com nome do projeto e botão de menu (quando o usuário está logado).
- `aside.sidebar`: menu lateral com navegação entre as páginas internas do app.
- `section#login`: tela inicial principal, com formulário de login e fundo visual com imagens.
- `section#home`: página inicial com vídeo e cartões de indicadores (KPIs).
- `section#locations`: busca de pontos de coleta por texto e categoria.
- `section#shop`: área simples de recompensas/cupons.
- `section#info`: conteúdo educativo com orientações de descarte.
- `section#profile`: edição de perfil e botão de logout.

### 2) Estilos CSS

- Uso de variáveis em `:root` para padronizar cores, sombras e bordas.
- Classe `body.logged-out` controla quais elementos aparecem sem login.
- Layout responsivo com `@media` para melhorar visual no celular.
- A tela de login usa `login-bg-layer` + `@keyframes slideshow` para alternar imagens de fundo.
- Espaçamentos foram ajustados para evitar elementos “colados” (`padding`, `gap`, `margin-bottom`).

### 3) Lógica JavaScript

- **Navegação/Menu**
  - `toggleMenu()` e `closeMenu()` controlam abertura/fechamento do menu lateral.
  - `showPage(id)` troca a página ativa e atualiza visual do botão selecionado.

- **Coleta**
  - `locations`: lista local de pontos de coleta.
  - `searchLocations()`: filtra por texto e categoria.
  - `renderLocationCard()`: cria cards de resultado via DOM.

- **Perfil**
  - `isValidEmail(email)`: valida formato de email.
  - `saveProfile()`: salva dados em `localStorage` na chave `ecodescarte_user`.
  - `loadProfile()`: recupera dados salvos e lida com JSON inválido.
  - `updateKPIs()`: atualiza indicadores da Home com base nos dados locais.

- **Login/Sessão**
  - `login()`: valida formulário e salva sessão local em `ecodescarte_session`.
  - `loadSession()`: restaura sessão ao abrir a página.
  - `logout()`: remove sessão e retorna para a tela de login.
  - `enableApp()` / `disableApp()`: ligam/desligam o modo autenticado.

## Como executar

Abra o arquivo `index.html` no navegador.
