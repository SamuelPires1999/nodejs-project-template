# Node.js Project Template

A minimal, ready-to-go TypeScript starter for Node.js projects. Includes hot-reload development, production builds, and code formatting out of the box.

## Features

- **TypeScript** with strict mode enabled
- **tsx** for fast, watch-mode development (`start:dev`) with no build step
- **tsc** for type-checked production builds that emit to `dist/`
- **Prettier** for automatic code formatting
- ESM (`"type": "module"`) modules throughout

## Requirements

- [Node.js](https://nodejs.org/) 18 or newer (tsx requires v18+)
- npm (bundled with Node.js)

## Getting Started

### 1. Clone and install dependencies

```bash
git clone <your-repo-url> my-project
cd my-project
npm install
```

To use this template to start a fresh project on GitHub, click **"Use this template"** at the top of the repo page, or use the [GitHub CLI](https://cli.github.com/):

```bash
gh repo create my-project --template nodejs-project-template --clone
```

### 2. Run in development mode

```bash
npm run start:dev
```

This runs `src/index.ts` with `tsx` in watch mode — the server restarts automatically whenever you save a file. You should see:

```
hello world
```

> Tip: edit `src/index.ts` and save — the process reloads instantly.

### 3. Build for production

```bash
npm run build
```

Compiles the TypeScript sources to plain JavaScript in `dist/`, using the settings in `tsconfig.json`.

### 4. Format your code

```bash
npm run format
```

Runs Prettier across the whole project to keep the code style consistent (see `.prettierrc`).

## Project Structure

```
├── src/
│   └── index.ts          # Entry point — replace with your own code
├── .gitignore            # Ignores node_modules/, dist/, .env
├── .prettierrc           # Prettier config (no semicolons)
├── package.json          # Scripts and dependencies
├── tsconfig.json         # TypeScript compiler options
└── README.md
```

## Scripts

| Command             | Description                        |
| ------------------- | ---------------------------------- |
| `npm run start:dev` | Run `src/index.ts` with hot reload |
| `npm run build`     | Compile TypeScript to `dist/`      |
| `npm run format`    | Format all files with Prettier     |

## Customization Checklist

- [ ] Update `name` and `version` in `package.json`
- [ ] Remove existing `git remote` and add your own: `git remote add origin <your-repo-url>`
- [ ] Replace the placeholder `console.log("hello world")` in `src/index.ts` with your app entry point
- [ ] Add a `description` and appropriate `license` in `package.json`
- [ ] Add `.env` files (already gitignored) and a `.env.example` if you use environment variables

## Configuration

### tsconfig.json

Defaults that matter:

| Option   | Value      | Purpose                                 |
| -------- | ---------- | --------------------------------------- |
| `target` | `ESNext`   | Compile to the latest JavaScript syntax |
| `strict` | `true`     | Enables all strict type checks          |
| `outDir` | `./dist`   | Where builds are emitted                |
| `module` | `commonjs` | Module system used in compiled output   |

> Note: `module` is set to `commonjs` in the template even though the package uses ESM. If you use `import`/`export` syntax and hit issues with the build output, you can switch `module` to `ESNext` or `node16` and have `tsc` emit native ESM.

## License

ISC
