# INSTALL

```bash
composer create-project laravel/laravel rub-investor
```

## FIRST COMMIT

```bash
cd rub-investor
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/ricardoub/rub-investor.git
git push -u origin main
```

## LARAVEL INSTALL

```bash
composer create-project laravel/laravel rub-fii-investor
npm install
npm run dev
npm run build
php artisan migrate
git add .
git commit -m "FIRST COMMIT: laravel install"
```

## DEPENDENCIAS

### [Getting Started with TALL stack](https://devdojo.com/thinkverse/getting-started-with-tall-stack)

```bash
composer require laravel/jetstream
php artisan jetstream:install livewire
php artisan migrate
composer require livewire/livewire
```

### Editar o arquivo [vite.config.js] conforme abaixo

```js
import { defineConfig } from 'vite';
import laravel, { refreshPaths } from 'laravel-vite-plugin';

export default defineConfig({
    plugins: [
        laravel({
            input: [
                'resources/css/app.css',
                'resources/js/app.js',
            ],
            refresh: [
                ...refreshPaths,
                'app/Livewire/**',
            ],
        }),
    ],
});
```

```bash
git add .
git commit -m "DEPENDENCIAS: livewire install"
```
