# vite 設定

```ts:client\vite.config.ts
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react-swc'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000,
    host: true,
    watch: {
      usePolling: true
    }
  }
})
```


docker-compose exec client bash


# Jestの設定とテストの実行手順

## 必要なパッケージのインストール
npm install --save-dev jest @types/jest
npm install --save-dev babel-jest @babel/core @babel/preset-env @babel/preset-typescript

## client\.babelrc
```JSON
{
  "presets": ["@babel/preset-env", "@babel/preset-typescript"]
}
```

## client\jest.config.js
```js
export default {
  transform: {
    "^.+\\.(ts|tsx)$": "babel-jest",
  },
  testEnvironment: "node",
};
```

## client\__tests__\example.test.tsx
```ts
import { describe, it, expect } from "@jest/globals";

describe("Example Component Test", () => {
  it("should be true", () => {
    expect(true).toBe(true);
  });
});
```

## client\package.json
```json
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0 --fix",
    "preview": "vite preview",
    "test": "jest"  追加
  },
```

# React18 以降はこう書く

```jsx:main.jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";
import "./index.css";

const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

# 開発環境構築

```shell
chmod +x init.sh
./init.sh
```

# Laravel

http://localhost:8080/

# phpmyadmin

http://localhost:5000/

or

# Laravel + Next.js 開発環境

# Laravel ダウンロード

```shell
composer create-project laravel/laravel ./api # 最新
or
composer create-project laravel/laravel:^9.0 ./api # バージョン指定
```

# Next.js ダウンロード

```shell
git clone https://github.com/laravel/breeze-next.git ./client # Gitから
or
npx create-next-app@latest ./client # 最新
```

# Docker 起動

```shell
docker-compose up -d
```
