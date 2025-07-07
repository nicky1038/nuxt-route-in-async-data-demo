# Nuxt 3 "route in async data" reproduction demo

## What problem does this demo show?

If some navigation is performed within `useAsyncData` callback, route objects created with `useRoute` from `vue-router` and `#imports` differ from each other.

## How is it possible to observe the issue?

This demo is hosted at https://nicky1038.github.io/nuxt-route-in-async-data-demo/.

* Open DevTools console in your browser and go tho the root page.
* Press "Increment param" button.
* In DevTools console notice that within the same `refresh` call `fullPath` property of route objects from `vue-router` and `nuxt` are different, the `nuxt` one is wrong.

## Development Server

It is also possible to run the demo locally.

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
