# Arestro API (JSON Server)

API fictícia de restaurantes para a aplicação Arestro, desenvolvida para a disciplina de Programação Móvel do curso de Sistemas de Informação do IFAL Arapiraca.

## Dados

Recursos disponíveis:

- `restaurants`: lista de restaurantes com os campos:
  - `id` (number)
  - `name` (string)
  - `description` (string)
  - `photo_url` (string - imagem ilustrativa do Unsplash)
  - `address` (string - endereço real em São Paulo)
  - `rating` (number - avaliação simulada de 0 a 5)

### Exemplos de Endpoints

- Todos os restaurantes: `GET /restaurants`
- Um restaurante: `GET /restaurants/3`
- Filtrar por rating >= 4.7: `GET /restaurants?rating_gte=4.7`
- Paginação: `GET /restaurants?_page=1&_limit=5`
- Ordenar por rating (desc): `GET /restaurants?_sort=rating&_order=desc`
- Buscar por nome (contém "Pizza"): `GET /restaurants?name_like=Pizza`

## Créditos das Imagens

Imagens obtidas de fotógrafos no [Unsplash](https://unsplash.com).
