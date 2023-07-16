---
title: vite-react-ts-template-with-tailwind
created_at: 2023. 07. 16
updated_at: 2023. 07. 17
---

# vite-react-ts-template-with-tailwind

> `tailwind css`를 함께 설치하는 `vite-react-ts` 템플릿

## install

```
npm install
```

## Added Packages

```json
"dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.14.1"
},
"devDependencies": {
  "@types/react": "^18.2.14",
  "@types/react-dom": "^18.2.6",
  "@typescript-eslint/eslint-plugin": "^5.61.0",
  "@typescript-eslint/parser": "^5.61.0",
  "@vitejs/plugin-react-swc": "^3.3.2",
  "eslint": "^8.44.0",
  "eslint-plugin-react-hooks": "^4.6.0",
  "eslint-plugin-react-refresh": "^0.4.1",
  "typescript": "^5.0.2",
  "vite": "^4.4.0",
  "prettier": "^2.8.8",
  "eslint-config-prettier": "^8.8.0",
  "eslint-plugin-unused-imports": "^2.0.0",
  "husky": "^8.0.3",
  "lint-staged": "^13.2.3",
  "tailwindcss": "^3.3.2",
  "postcss": "^8.4.25",
  "autoprefixer": "^10.4.14",
  "vite-tsconfig-paths": "^4.2.0"
}
```

## Eslint Settings

### script

```shell
"lint": "eslint --cache --max-warnings=0 ."
```

### .eslintrc.cjs

```js
module.exports = {
  root: true,
  env: { browser: true, es2020: true },
  extends: [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking",
    "plugin:react-hooks/recommended",
  ],
  parser: "@typescript-eslint/parser",
  parserOptions: {
    ecmaVersion: "latest",
    sourceType: "module",
    project: true,
    tsconfigRootDir: __dirname,
  },
  plugins: ["react-refresh", "unused-imports", "@typescript-eslint"],
  rules: {
    "react-refresh/only-export-components": [
      "warn",
      { allowConstantExport: true },
    ],
    "@typescript-eslint/no-non-null-assertion": "off",
    "no-var": "error",
    "no-console": ["warn", { allow: ["warn", "error", "info"] }],
    "no-unused-vars": "off",
    "unused-imports/no-unused-imports": "error",
    "unused-imports/no-unused-vars": "error",
    "@typescript-eslint/no-unused-vars": "off",
  },
  ignorePatterns: ["*.config.js", "*.config.ts", "*.cjs"],
};
```

## Prettier Settings

### script

```
"format": "prettier --write --cache ."
```

### .prettierrc

```json
{
  "semi": true,
  "tabWidth": 2,
  "arrowParens": "always",
  "bracketSpacing": true,
  "singleQuote": false,
  "bracketSameLine": true
}
```

## Lint-Staged Settings

### .lintstagedrc

```json
{
  "*.{js,jsx,ts,tsx}": "npm run format"
}
```

## Husky Settings

### pre-commit

```shell
npm run lint
npm run format
```
