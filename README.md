# dash.acmcsuf.com

## Developing

Install deps with `pnpm i`.  

Start dev server:

```sh
pnpm dev

# or start the server and open the app in a new browser tab
pnpm dev --open
```

## Building and Previewing

To create a production version of your app:

```sh
pnpm build
```

You can now preview the production build:

```sh
pnpm preview
```

> Using the preview after making changes is important because vite uses the NodeJS runtime but the app uses the Workers runtime in production.

