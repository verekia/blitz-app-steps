# 02 - Project Setup

- **Generate a new Blitz project in the current folder**: `blitz new .`

Pick `React Final Form (recommended)`.

## PostgreSQL Database via Docker

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

- **Add to `.gitignore`**:

```
/data/
```

- **In `db/schema.prisma`, change the `provider` to `postgres`**:

```
datasource db {
  provider = "postgres"
  url      = env("DATABASE_URL")
}
```

- **Delete the `db/migrations` folder**.

- **Run `docker-compose up`** in a new terminal, or `docker-compose up -d` in the same terminal.

- **Run `blitz prisma migrate dev --preview-feature`**

- **Run `npm test` to test the testing database** ([not `blitz test`](https://github.com/blitz-js/blitz/issues/2006))

Previous: [01 - System Setup](/01-system-setup#readme)
