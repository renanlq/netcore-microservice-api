# Microservices API conventions (pt-br)

## Objetivo
Estrutura de desenvolvimento em .NET para microsseviços

## Estrutura
Padrão do projeto para cada microsserviço:
1.	**[NomeServico].API**: reponsável pela camada de *disponibilização* dos recursos do serviço;
2.	**[NomeServico].Domain**: domíno da aplicação, responsábilidade de manter as *regras de negócio* de cada microsservico;
3.	**[NomeServico].Infra**: camada mais baixa, para acesso a *dados*, *infraestrutura* e consumo de *serviços externos*; e
4.	**[NomeServico].CrossCutting**: camada vertical para disponibilização de recursos para as camadas de *Domain* e *Infra*.

Para as pastas seguir o seguinte esquema:
* src
  + microsservico1
    + Microsservico1.API
    + Microsservico1.CrossCutting
    + Microsservico1.Domain
    + Microsservico1.Infra
    + test
      + Microsservico1.Api.Test
      + Microsservico1.Domain.Test
      + Microsservico1.Infra.Test
  + microsservico2
    + Microsservico2.API
    + Microsservico2.CrossCutting
    + Microsservico2.Domain
    + Microsservico2.Infra
      + test
        + ...
    ...
  + NomeSolucaoProjeto.sln

## Build and Test
Teste será adicionado em pasta referente à cada microsserviço.

## Depenências iniciais (NuGet)
Para projeto service.API:
1. <a href="https://www.nuget.org/packages/automapper/">AutoMapper</a>;
2. <a href="https://www.nuget.org/packages/newtonsoft.json/">Newtonsoft.Json</a>; e
3. <a href="https://www.nuget.org/packages/swashbuckle.aspnetcore/">Swashbuckle.AspNetCore</a>.
