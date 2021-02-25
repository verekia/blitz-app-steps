# 01 - System Setup

## Initialization

- **Run `node -v` and `npm -v`** to check if Node and NPM are installed.

This guide was made with Node `15.3.0` and NPM `7.0.14`

- **Run `blitz -v`** to check if Blitz is installed globally. If not, **run `npm i -g blitz`** or **`yarn global add blitz`**.

This guide was made with Blitz `0.30.4`

- **Position your terminal in your workspace directory** from which we'll create the project in a new subdirectory.

I assume you haven't created any Git repository or folder for your project yet.

- **Run `blitz new your_app_name`** to generate a new Blitz project. Pick `React Final Form (recommended)`.

- **Customize `package.json`** with a `name`, or whatever else you want in there.

## Git

We will use Github in this guide.

- **Create a [new repository](https://github.com/new) on GitHub**. Do not create a `README.md` or `.gitignore`.
- **Copy the GitHub repository URL**
- **Run `git branch -M main`**
- **Run `git remote add origin [YOUR_REPO_URL]`**
- **Run `git push -u origin main`**

Back to the [home page](https://github.com/verekia/blitz-app-steps)
Next: [02 - Project Setup](/02-project-setup#readme)
