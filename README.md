# @internxt/css-config

Shared Tailwind CSS configuration for Internxt's frontend projects. It centralizes design tokens (colors, spacing, shadows, transitions, etc.) so that all applications keep a consistent look and feel.

## Installation

```bash
npm install @internxt/css-config
```

## Usage

Import the default configuration in your `tailwind.config.ts` and merge it with your project's own configuration:

```ts
import config from '@internxt/css-config';

export default {
  ...config,
  content: ['./src/**/*.{js,ts,jsx,tsx}'],
};
```

> **Note:** the `content` defined in this package points to `./src/**/*.tsx`, so each consuming project must override this property with its own paths, as shown in the example above.

## What's included

- **Colors**: base palette (`gray`, `purple`, `blue`) and semantic colors (`primary`, `red`, `orange`, `yellow`, `green`, `pink`, `indigo`) defined via CSS variables (`--color-*`) to support dark mode (`darkMode: "class"`).
- **Custom breakpoints** (`screens`): `xs`, `sm`, `md`, `lg`, `xl`.
- **Theme extensions** (`theme.extend`): `dropShadow`, `zIndex`, `opacity`, `rotate`, `transitionDuration`, `transitionProperty`, `width`, `minWidth`, `borderWidth`, `ringOpacity`, `backgroundOpacity`, `ringWidth`, `borderRadius`, `fontSize`, `spacing`, `maxWidth`, `scale`, and `boxShadow`.

See [`src/index.ts`](src/index.ts) for the full list of available values.

## Development

```bash
npm install   # install dependencies
npm run build # compile TypeScript (src/) to JavaScript (dist/)
```

The package is published from the contents of `dist/`, generated from `src/index.ts`.

## Publishing

Publishing to npm happens automatically via GitHub Actions ([`.github/workflows/publish-npm.yml`](.github/workflows/publish-npm.yml)) when a GitHub release is published, or manually via `workflow_dispatch`.
