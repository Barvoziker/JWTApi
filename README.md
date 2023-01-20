# JWT API

This project is an example of how to create a JSON Web Token (JWT) based API using PHP 8 and the Symfony framework with the API Platform.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- PHP 8
- Composer
- Symfony CLI
- A database (MySQL, PostgreSQL, SQLite, etc.)
- Postman (optional)

### Installation

1. Clone the repository: `git clone https://github.com/Barvoziker/JWTApi.git`
2. Navigate to the project directory: `cd jwt-api`
3. Install the dependencies: `composer install`
4. Create a `.env` file: `cp .env.example .env`
5. Configure the database connection in the `.env` file
6. Create the database: `php bin/console doctrine:database:create`
7. Apply the migrations: `php bin/console doctrine:migrations:migrate`
8. Create a JWT private key: `openssl genpkey -out config/jwt/private.pem -aes256 -algorithm rsa -pkeyopt rsa_keygen_bits:4096`
9. Create a JWT public key: `openssl pkey -in config/jwt/private.pem -out config/jwt/public.pem -pubout`
10. Start the built-in web server: `symfony serve`

### Usage

1. Register a new user by making a POST request to `/api/register` with a JSON body containing the following fields: `email`, `password`, and `name`.
2. Login with the registered user by making a POST request to `/api/login` with a JSON body containing the following fields: `email` and `password`. The response will contain a JWT token that can be used to authenticate future requests.
3. Make authenticated requests by including the JWT token in the `Authorization` header of the request, with a value of `Bearer <token>`.

## Built With

- [Symfony](https://symfony.com/) - The web framework used
- [API Platform](https://api-platform.com/) - The API framework used
- [LexikJWTAuthenticationBundle](https://github.com/lexik/LexikJWTAuthenticationBundle) - JWT authentication bundle for Symfony

## Acknowledgments

- [JWT.io](https://jwt.io/) - For providing a great resource on JSON Web Tokens
- [Auth0](https://auth0.com/) - For their excellent documentation on JWT and API security

## Author

* **[ Barvoziker ]** - *Initial work*
