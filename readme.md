## Title
Codebits GraphQL

## Description
API for a microblogging platform

## Running the API
It's very simple to get the API up and running. First, create the database (and database user if necessary) and add them to the .env file.

```env
DB_DATABASE=your_db_name
DB_USERNAME=your_db_user
DB_PASSWORD=your_password
```

Then install, migrate, seed, and run the server:

```php
composer install
php artisan key:generate
php artisan migrate
php artisan serve
```

## Testing Environment
Visit http://localhost:8000/graphiql  on your browser to test the API

Alternatively you can use Postman or Insomnia

Use this url: http://localhost:8000/graphql

## Queries and Mutations

### Fetch all bits
```
{
  allBits {
    id
    user {
      name
    }
    snippet
    replies {
      id
      user {
        name
      }
      reply
    }
    likes_count
    created_at
    updated_at
  }
}
```

### Register a user
```
mutation {
    signUp(
        name: "Ryan Wire"
        email: "ryanwire@outlook.com"
        password: "123456"
    )

}
```

### Login a user
```
mutation {
    logIn(
        email: "ryanwire@outlook.com"
        password: "123456"
    )

}
```
