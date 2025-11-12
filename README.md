# Arestro API (JSON Server)

API fictícia de restaurantes para a aplicação Arestro, desenvolvida para a disciplina de Programação Móvel do curso de Sistemas de Informação do IFAL Arapiraca.

## Dados

Recursos disponíveis:

- `user`: objeto único representando o usuário autenticado (mock) com os campos: 
  - `name` (string) 
  - `email` (string) 
  - `password` (string)

- `restaurants`: lista de restaurantes com os campos:

  - `id` (number)
  - `name` (string)
  - `description` (string)
  - `photo_url` (string - imagem ilustrativa do Unsplash)
  - `address` (string - endereço real em São Paulo)
  - `rating` (number - avaliação simulada de 0 a 5)

- `foods`: lista de comidas (3 por restaurante) com os campos:
  - `id` (number)
  - `name` (string)
  - `description` (string)
  - `photo_url` (string - imagem ilustrativa do Unsplash)
  - `rating` (number)
  - `restaurant_id` (number - referência ao restaurante)
  - `ingredients` (array de strings em Capitalize)

### Exemplos de Endpoints

- Todos os restaurantes: `GET /restaurants`
- Um restaurante: `GET /restaurants/3`
- Filtrar por rating >= 4.7: `GET /restaurants?rating_gte=4.7`
- Paginação: `GET /restaurants?_page=1&_limit=5`
- Ordenar por rating (desc): `GET /restaurants?_sort=rating&_order=desc`
- Buscar por nome (contém "Pizza"): `GET /restaurants?name_like=Pizza`

### Exemplos de Endpoints (Foods)

- Todas as comidas: `GET /foods`
- Comidas de um restaurante (ex: id 5): `GET /foods?restaurant_id=5`
- Buscar por nome (contém "Burger"): `GET /foods?name_like=Burger`
- Buscar por ingrediente (contém "Tomate"): `GET /foods?ingredients_like=Tomate`
- Paginação: `GET /foods?_page=1&_limit=10`
- Ordenar por rating (desc): `GET /foods?_sort=rating&_order=desc`
- Combinar filtros (ex: pizzas com queijo): `GET /foods?name_like=Pizza&ingredients_like=Queijo`

Observação: o JSON Server faz correspondência parcial em `*_like` e busca qualquer item do array `ingredients` que contenha o termo.
