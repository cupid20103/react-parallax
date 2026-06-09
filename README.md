# React Parallax

A single page parallax scene built with React, TypeScript and Vite. Seven image
layers move at different speeds to create a sense of depth, and a sticky button
lets you scroll smoothly between the top and bottom of the scene.

## Tech stack

- [React 18](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Vite](https://vitejs.dev/) for development and bundling
- [@react-spring/parallax](https://www.react-spring.dev/docs/components/parallax) for the layered parallax effect
- [Tailwind CSS](https://tailwindcss.com/) for styling

## Prerequisites

- Node.js 18.16.1 or later (the version is pinned in [.nvmrc](.nvmrc))
- [Yarn](https://classic.yarnpkg.com/) as the package manager

If you use [nvm](https://github.com/nvm-sh/nvm), run `nvm use` to select the
correct Node version.

## Getting started

Install the dependencies:

```bash
yarn install
```

Start the development server:

```bash
yarn dev
```

Vite prints a local URL (by default http://localhost:5173). Open it in your
browser to view the app.

## Available scripts

| Script         | Description                                            |
| -------------- | ------------------------------------------------------ |
| `yarn dev`     | Start the Vite development server with hot reloading.  |
| `yarn build`   | Type check with `tsc` and build for production.        |
| `yarn preview` | Serve the production build locally.                    |
| `yarn lint`    | Run ESLint over the `src` folder.                      |

## Project structure

```
react-parallax/
├── public/                 Static assets served as is
├── src/
│   ├── assets/             Parallax layer images (layer-01 to layer-07)
│   ├── App.tsx             Parallax scene and the scroll button
│   ├── main.tsx            React entry point
│   ├── index.css           Tailwind directives and global styles
│   └── vite-env.d.ts       Vite type definitions
├── index.html              HTML entry point
├── tailwind.config.js      Tailwind configuration
├── postcss.config.js       PostCSS configuration
└── vite.config.ts          Vite configuration
```

## How it works

[src/App.tsx](src/App.tsx) renders a `Parallax` container that spans 1.45 pages.
Each `ParallaxLayer` is given a background image along with `offset`, `speed` and
`factor` values, so the layers shift at different rates as the page scrolls.

A final sticky `ParallaxLayer` holds the button. Clicking it calls `scrollTo` on
the parallax ref to move between the start and end of the scene, and the button
label toggles between "Down" and "Up" to reflect the next action.
