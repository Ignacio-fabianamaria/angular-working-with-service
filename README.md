# 🅰️ Angular - Working With Service

Este projeto foi desenvolvido com o propósito de auxiliar na compreensão dos conceitos fundamentais service no Angular. Abaixo estão listados os principais comandos utilizados durante a criação do projeto:

- `ng new` - cria um novo projeto Angular
- `ng g c components/card` - cria o component card

## Estrutura de Diretórios

O projeto está organizado da seguinte maneira:

- **app/**
  - **components/**: Nesta pasta,encontr-se os componentes reutilizáveis da aplicação.
    - **card/**: Dentro desta pasta, você encontrará o componente de card de Pokémon. Este componente é responsável por representar cards de Pokémon na aplicação. Cada card contém:

      - Um título com o nome do Pokémon.
      - Uma imagem representativa do Pokémon.
      - Atributos do Pokémon, que são exibidos dinamicamente usando a diretiva `ngFor`.

      A diretiva `ngFor` é utilizada para iterar sobre uma lista de atributos do Pokémon, gerando automaticamente elementos `<span>` para cada atributo na lista. Isso torna o componente de card flexível e capaz de lidar com diferentes Pokémon e seus atributos de forma dinâmica.
  - **service/**: A pasta de serviço abriga os arquivos relacionados à lógica de negócios ou ao acesso a APIs externas.

## Em Construção 🚧
