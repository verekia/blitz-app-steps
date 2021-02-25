# 01 - System Setup

- **Check if Node and NPM are installed**: `node -v` and `npm -v`

This guide was made with Node `15.3.0` and NPM `7.0.14`

- **Check if Blitz is installed**: `blitz -v`

If not, install it globally: `npm i -g blitz` or `yarn global add blitz`

This guide was made with Blitz `0.30.4`

- **Create a new folder and Git repository and `cd` into it**.

In this guide we will use PostgreSQL. You need a local database to generate migrations (as opposed to developing using a cloud-hosted dev DB) because Prisma creates a shadow database (see [this issue](https://github.com/prisma/prisma/issues/4571#issuecomment-747496127)).

Here we will use Docker to run a local PostgreSQL database. If you don't want to do that, please tweak the database URL to point to your locally installed database.

- **Launch Docker**

Next: [02 - Project Setup](/02-project-setup#readme)