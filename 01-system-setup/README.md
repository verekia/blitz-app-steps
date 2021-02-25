# 01 - System Setup

For a smoother experience, some commands in this guide are chained with the `&&` operator. Feel free to split them and run them one by one.

## Installs check

- **Open a terminal** and **`cd` to your workspace directory**.

- **Run `node -v && npm -v`** to check if Node and NPM are installed.

This guide was made with Node `15.3.0` and NPM `7.0.14`

- **Run `blitz -v`** to check if Blitz is installed globally. If not, **run `npm i -g blitz`** or **`yarn global add blitz`**

This guide was made with Blitz `0.30.4`

## Git repository

I assume you haven't created any Git repository or folder for your project yet. We will use Github in this guide.

- **Create a [new repository](https://github.com/new) on GitHub**. Do not create `README.md` or `.gitignore` files.
- **Copy the repository URL** and **run `git clone YOUR_REPO_URL`**

## Blitz project generation

- **`cd` into the created folder**, and **open that folder in your editor**.

- **Run `blitz new .`** to generate a new Blitz project and **Pick `React Final Form (recommended)`**

This command creates an initial Git commit for you.

- **Customize `package.json`** with a `name`, or whatever else you want in there.
  - **Run `git add package.json && git commit -m "Customize package.json"`** if you did that.

- **Run `git push`**

Back to the [home page](https://github.com/verekia/blitz-app-steps)
Next: [02 - Project Setup](/02-project-setup#readme)
