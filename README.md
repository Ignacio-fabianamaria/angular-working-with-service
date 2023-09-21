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

## Comunicação com o Arquivo Environment

  O arquivo `environment` em Angular é uma prática comum para armazenar variáveis de ambiente, como URLs de API, chaves de acesso e outros valores que podem variar dependendo do ambiente de execução, como desenvolvimento, teste ou produção.

  <details>
  
 No arquivo environment da aplicação é definida uma variável pokeApi que armazena a URL base da API que será usada na aplicação:

  ```typescript
  // Arquivo environment.ts
  export const environment = {
    production: false,
    pokeApi: 'https://pokeapi.co/api/v2/pokemon/'
  };

  ```

  Neste arquivo service da aplicaçãp (PokemonService)  a variável pokeApi do arquivo environment é usada  para configurar a URL base da API. Isso permite que o serviço acesse facilmente a URL da API, mantendo a configuração separada em um local central e facilitando a mudança dessa configuração para diferentes ambientes (por exemplo, de desenvolvimento para produção) sem a necessidade de alterar o código do serviço.

  </details>

## Observable e Subscribe em Angular

**Observable** e **Subscribe** são conceitos fundamentais em Angular quando se trata de lidar com requisições assíncronas

  - **Observable**: Um **Observable** é uma representação de uma fonte de dados que pode emitir valores ao longo do tempo. No contexto do Angular, ele é frequentemente usado para lidar com operações assíncronas, como requisições HTTP. Você pode pensar em um Observable como uma corrente de eventos ou dados que pode ser observada.

  - **Subscribe**: O método **Subscribe** é usado para observar (ou "escutar") os valores que um Observable emite. Quando você se inscreve em um Observable, está efetivamente declarando que deseja ser notificado quando novos valores são emitidos pela fonte de dados observada. Isso é feito fornecendo funções de callback para lidar com os eventos emitidos pelo Observable, como os eventos de sucesso (`next`) e erro (`error`).

  <details>
  
  <summary>Agora, vejamos como esses conceitos são aplicados na sua estrutura de aplicação:</summary>

 - No serviço `PokemonService`:

    ```typescript
    import { Observable } from 'rxjs';
    import { PokemonData } from '../models/pokemonData';

    // ...

    getPokemon(pokemonName: string): Observable<PokemonData> {
      // Realiza uma requisição HTTP e retorna um Observable que emite os dados do Pokémon.
      this.pokeData = this.http.get<PokemonData>(`${this.baseURL}${pokemonName}`);
      return this.pokeData;
    }
    ```

    O método `getPokemon` retorna um Observable que emite os dados do Pokémon após a conclusão da requisição HTTP.

  - No componente `CardComponent`:

    ```typescript
    import { Component, OnInit } from '@angular/core';
    import { PokemonService } from 'src/app/services/pokemon.service';

    @Component({
      selector: 'app-card',
      templateUrl: './card.component.html',
      styleUrls: ['./card.component.css']
    })
    export class CardComponent implements OnInit {
      name: string = 'CHARMANDER';
      attributesTypes: string[] = ['FIRE', 'ROCK'];

      constructor(private service: PokemonService) {}

      ngOnInit(): void {
        // Ao iniciar o componente,  o serviço é chamado e se inscreve no Observable
        // para receber os dados do Pokémon.
        this.service.getPokemon('charmander').subscribe({
          next: (res) => console.log(res), // Manipula os dados quando estão disponíveis.
          error: (err) => console.log(err)   // Manipula erros, se ocorrerem.
        });
      }
    }
    ```

    No método `ngOnInit` do componente, é chamado o serviço `getPokemon` e se inscreve no Observable resultante para manipular os dados (no caso, usando `console.log` para exibi-los) e para lidar com erros, se ocorrerem.

  Isso permite que a aplicação lide de forma eficiente com operações assíncronas, como a obtenção de dados de Pokémon da API, garantindo que a interface do usuário permaneça responsiva enquanto as operações são executadas em segundo plano.

</details>

  </details>

## Em Construção 🚧
