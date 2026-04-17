# EcoDescarte (Pikachu)

Projeto de interface web para incentivar o descarte correto de eletrônicos.

## Melhorias aplicadas

- Design modernizado com layout responsivo e navegação lateral com backdrop.
- Filtros de pontos de coleta melhorados com busca em tempo real.
- Correções de UX/acessibilidade (focus visível, `aria-*`, estados de menu).
- Correções de lógica no perfil:
  - validação de email;
  - persistência segura no `localStorage`;
  - tratamento de dados corrompidos.
- Renderização de resultados via criação de elementos DOM (evita injeção por `innerHTML`).

## Como executar

Abra o arquivo `index.html` no navegador.
