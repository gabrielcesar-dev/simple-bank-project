# Bank API

## Introduction

Welcome to the Bank API project. This API is implemented in Java using Spring Boot and Gradle and is designed to simulate basic banking functionalities. It includes functionalities for managing users, accounts, features, cards, and news within a banking system. This README will provide an overview of the project's structure, including the schema and endpoints available.

## Authors

- Gabriel Cesar Silvino Xavier

## Schema

### Class Diagram

```mermaid
classDiagram
  class User {
    -String name
    -Account account
    -Feature[] features
    -Card card
    -News[] news
  }

  class Account {
    -String number
    -String agency
    -Number balance
    -Number limit
  }

  class Feature {
    -String icon
    -String description
  }

  class Card {
    -String number
    -Number limit
  }

  class News {
    -String icon
    -String description
  }

  class BaseItem {
    -String icon
    -String description
  }

  User "1" *-- "1" Account
  User "1" *-- "N" Feature
  User "1" *-- "1" Card
  User "1" *-- "N" News
  Feature "1" *-- "1" BaseItem
  News "1" *-- "1" BaseItem
```

## Endpoints

### Retrieve a User

- **GET /users/{id}**

  Retrieves a user by their ID.

### Create a User

- **POST /users**

  Creates a new user.
