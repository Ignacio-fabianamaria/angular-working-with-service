# 🅰️ Angular - Working With Service

Este projeto foi desenvolvido com o propósito de auxiliar na compreensão dos conceitos fundamentais service no Angular. Abaixo estão listados os principais comandos utilizados durante a criação do projeto:

- `ng new` - cria um novo projeto Angular
- `ng g c components/card` - cria o component card
- `ng g s services/pokemon` -cria o arquivo de service

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

## Arquivo de Serviço (pokemonService)
Em Angular, os serviços são módulos dedicados à lógica de negócios e à gestão de dados que não estão diretamente ligados à interface do usuário. Eles desempenham um papel essencial na organização do código, seguindo o princípio da separação de responsabilidades.

<details>

<summary>Aqui estão as características dos serviços em Angular</summary>

**Responsabilidades Claras:** Os serviços se concentram em lógica de negócios, gerenciamento de dados e comunicação com servidores, enquanto os componentes lidam com a interface do usuário.

- **Centralização da Lógica:** Os serviços permitem centralizar a lógica de negócios em um único local, evitando duplicações de código em diferentes partes da aplicação.

- **Compartilhamento de Dados:** Serviços são ideais para armazenar e compartilhar dados entre várias partes da aplicação, incluindo dados de requisições a servidores, armazenamento em cache e compartilhamento de estado.

- **Injeção de Dependência:** Serviços podem ser injetados em componentes e outros serviços, tornando a comunicação e integração entre eles mais eficientes.

- **Reutilização:** Os serviços podem ser reutilizados em toda a aplicação, promovendo a modularidade e escalabilidade do código.

</details>

 

## Em Construção 🚧
