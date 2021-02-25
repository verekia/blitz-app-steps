# 02 - Database Setup

## PostgreSQL databases setup via Docker

In this guide we will use PostgreSQL. You need a local database to generate migrations (as opposed to developing using a cloud-hosted dev DB) because Prisma creates a shadow database (see [this issue](https://github.com/prisma/prisma/issues/4571#issuecomment-747496127)).

Here we will use Docker to run a local PostgreSQL database. If you don't want to do that, please tweak the database URL to point to your locally installed database.

- **Launch Docker**

- **Create a [`docker-compose.yml`](/02-project-setup/docker-compose.yml) file containing**:

```yaml
version: '3.8'
services:
  db:
    image: postgres:13.2
    volumes:
      - ./data:/var/lib/postgresql/data
    environment:
      POSTGRES_PASSWORD: password
    ports:
      - '5432:5432'
  db-testing:
    image: postgres:13.2
    environment:
      POSTGRES_PASSWORD: password
    ports:
      - '5433:5432'
```

If you ever want to reset the database, just delete the `data` folder.

Note that the dev database will be on port `5432` of your machine, and the testing database on port `5433`.

- **Add to `.gitignore`**:

```
/data/
```

- **Run `docker-compose up`** in a new terminal, or `docker-compose up -d` in the same terminal, to start the databases.

## Prisma setup and first migration

- In `db/schema.prisma`, **change the `provider` to `postgres`**:

```
datasource db {
  provider = "postgres"
  url      = env("DATABASE_URL")
}
```

- **Delete the `db/migrations` folder**.

- **Run `blitz prisma migrate dev --preview-feature`** to generate the first migration for Blitz's provided User model.

- **Run `npm test`** to test the testing database ([not `blitz test`](https://github.com/blitz-js/blitz/issues/2006))

Back to the [home page](https://github.com/verekia/blitz-app-steps)
Previous: [01 - System Setup](/01-system-setup#readme)
