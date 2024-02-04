# Steps to recreate:
1. `pnpm create vite`
1. `cd <project-directory>`
1. `pnpm install`
1. `pnpm run dev`
1. **(In a new terminal tab)** `git init` (Open in Github Desktop and create a new remote repo)
1. `pnpm add -D eslint-config-airbnb-typescript eslint-config-airbnb@19.0.4 eslint@^8.2.0 eslint-plugin-import@^2.25.3 eslint-plugin-jsx-a11y@^6.5.1 eslint-plugin-react@^7.28.0 eslint-plugin-react-hooks@^4.3.0`
1. Edit `.eslintrc.cjs`:
   - ```
      + 'airbnb',
      + 'airbnb-typescript',
      + 'airbnb/hooks',
      - 'eslint:recommended',
      // ...
      parser: '@typescript-eslint/parser',
      + parserOptions: {
      +   ecmaVersion: 'latest',
      +   sourceType: 'module',
      +   project: './tsconfig.json'
      + },
      // ...
      rules: {
      + 'react/react-in-jsx-scope': 0,
      // ...
      },
1. `pnpm add -D prettier eslint-config-prettier eslint-plugin-prettier`
1. `touch .prettierrc.cjs`
1. `.prettierrc.cjs`:
   - ```
     + module.exports = {
     +  trailingComma: 'es5',
     +  tabWidth: 2,
     +  semi: false,
     +  singleQuote: true,
     + }
