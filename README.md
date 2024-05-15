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
