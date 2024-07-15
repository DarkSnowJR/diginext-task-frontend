# front-task

This template should help get you started developing with Vue 3 in Vite.

## Resolved Problem

<span style="color:red">in App.vue: should use `profile.id` for key not index, because index is not unique and when the sorting changes the index changes and the comment assigned to the wrong profile</span>

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
pnpm install
```

### Compile and Hot-Reload for Development

```sh
pnpm dev
```

### Compile and Minify for Production

```sh
pnpm build
```
