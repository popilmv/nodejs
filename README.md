<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

## Description

# E-commerce Backend [Nest](https://github.com/nestjs/nest)

This project is a basic backend application for an e-commerce platform.
Its main goal is to provide a clean and scalable architectural foundation
for further development (Orders, Payments, Notifications, etc.).

The application is built using **NestJS** and follows a **modular monolith**
approach, where the codebase is kept in a single application but logically
split into domain-oriented modules.

---

## Architecture Overview
The project is designed with the following principles in mind:

- **Modular Monolith** — the system is divided into domain modules (Users, later Orders and Payments).
- **Separation of Concerns** — controllers handle HTTP requests, services contain business logic.
- **Dependency Injection** — NestJS manages dependencies between application components.

This approach allows the application to scale and evolve without turning
into a tightly coupled monolithic codebase.

---

## Project Structure
```
src/
main.ts # Application entry point
app.module.ts # Root module, application composition
users/
users.module.ts # Users domain module
users.controller.ts # HTTP endpoints for /users
users.service.ts # Users business logic
```


### AppModule
`AppModule` - the root module of the application
It is responsible for composing the system by importing domain modules and global configuration modules

### UsersModule
`UsersModule` functionality related to the Users domain.
It contains:
- `UsersController` — HTTP layer
- `UsersService` — business logic layer

---

## Environment Configuration
The project uses `@nestjs/config` for environment-based configuration.

- `.env` — local environment variables (ignored by git)
- `.env.example` — example configuration file committed to the repository

Example `.env` file:
```env
NODE_ENV=local
PORT=3030
APP_NAME=ecommerce-backend
```

The application port is read using ConfigService in **main.ts**

## Running the Application

# Install dependencies:

```
npm install
```

# Start the application in development mode:

```
npm run start:dev
```

# Available endpoints:

- GET **/** — basic test endpoint
- GET **/users** — Users module test endpoint

# Future Improvements

- Add OrdersModule and PaymentsModule
- Integrate a database (PostgreSQL)
- Add DTO validation and centralized error handling
- Introduce asynchronous processing (notifications, billing, etc.)
