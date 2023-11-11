
# Wer wird Millionär
## Install the tauri app
First download the app from src-tauri/target/release/msi/millionaer_0.1.0_x64_en-US.msi
Then install it on your computer.


# Nuxt 3 Minimal Starter (for the web-application)

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Setup

Make sure to install the dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev

# pnpm
pnpm run dev

# yarn
yarn dev

# bun
bun run dev
```

## Production

Build the application for production:

```bash
# npm (recommended)
npm npx nuxi generate

# pnpm
pnpm npx nuxi generate

# yarn
yarn npx nuxi generate
```

Locally preview production build:

```bash
# 
npx serve .output/public 

```
Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.

## Add a question
>In **app.vue** fügt man an die Liste question_container ein Question-Objekt hinzu.
>Die App muss neu gebildet werden:
>```bash
># tauri app
>cargo tauri build
># die Installationsdatei ist in /src-tauri/target/release/bundle/msi/
>```
