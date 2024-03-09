# API de Receitas por Ingredientes e Data de Validade

Esta é uma API em PHP que fornece acesso a um sistema de receitas com base nos ingredientes fornecidos e suas datas de validade. A API consulta um banco de dados para encontrar receitas que possam ser preparadas com os ingredientes válidos e as retorna ordenadas pela data de validade dos ingredientes.

## Funcionalidades

- **Consulta de Ingredientes Válidos**: Os ingredientes fornecidos são verificados em relação à sua data de validade. Aqueles cuja data de validade é posterior à data atual são considerados válidos.
- **Consulta de Receitas Compatíveis**: As receitas que podem ser preparadas com os ingredientes válidos são consultadas no banco de dados.
- **Ordenação por Data de Validade**: As receitas são ordenadas com base na data de validade mais próxima dos ingredientes que compõem cada uma.

## Uso da API

### Endpoint

```
GET /api/receitas
```

### Parâmetros de Requisição

- `ingredientes`: Lista de ingredientes e suas datas de validade.

### Exemplo de Requisição

```json
{
  "ingredientes": [
    {"nome": "Tomate", "expiration_date": "10/03/2024", "best_before_date": "08/03/2024"},
    {"nome": "Cebola", "expiration_date": "15/03/2024", "best_before_date": "12/03/2024"}
  ]
}
```

### Exemplo de Resposta

```json
{
  "success": true,
  "recipes": [
    {
      "id": 1,
      "nome": "Salada de Tomate e Cebola",
      "modo_preparo": "Lave e corte os tomates e as cebolas. Misture em uma tigela e tempere a gosto.",
      "tempo": "10 minutos",
      "porcoes": 4
    },
    {
      "id": 2,
      "nome": "Sopa de Legumes",
      "modo_preparo": "Pique os legumes e cozinhe em água fervente até ficarem macios. Tempere a gosto.",
      "tempo": "30 minutos",
      "porcoes": 6
    }
  ]
}
```

## Requisitos

- PHP instalado (compatível com a versão usada no script)
- Servidor web para executar o script PHP
- Banco de dados configurado e acessível para consulta

## Estrutura do Banco de Dados

Este script assume que existem tabelas no banco de dados conforme mencionado nos comandos SQL. Certifique-se de que sua estrutura de banco de dados esteja em conformidade para garantir o funcionamento correto da API.

## Notas Adicionais

- Este script pode ser integrado a uma aplicação web ou móvel para fornecer recomendações de receitas com base nos ingredientes disponíveis.
- Certifique-se de que as dependências, como o acesso ao banco de dados, estejam configuradas corretamente no ambiente de execução.

## Autor

Esta API foi desenvolvida por [Matehus Mendes](https://github.com/mm490514).
