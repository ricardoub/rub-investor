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

### LIVEWIRE [Getting Started with TALL stack](https://devdojo.com/thinkverse/getting-started-with-tall-stack)

```bash
composer require laravel/jetstream
php artisan jetstream:install livewire
php artisan migrate
composer require livewire/livewire
```

#### Editar o arquivo [vite.config.js] conforme abaixo

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

### TAILWIND [Getting Started with TALL stack](https://devdojo.com/thinkverse/getting-started-with-tall-stack)

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

#### Editar o arquivo [tailwind.config.js] conforme abaixo

```js
import defaultTheme from 'tailwindcss/defaultTheme';
import forms from '@tailwindcss/forms';
import typography from '@tailwindcss/typography';

/** @type {import('tailwindcss').Config} */
export default {
    content: [
        './vendor/laravel/framework/src/Illuminate/Pagination/resources/views/*.blade.php',
        './vendor/laravel/jetstream/**/*.blade.php',
        './storage/framework/views/*.php',
        './resources/views/**/*.blade.php',
        './resources/views/**/*.js',
    ],

    theme: {
        extend: {
            fontFamily: {
                sans: ['Figtree', ...defaultTheme.fontFamily.sans],
            },
        },
    },

    plugins: [forms, typography],
};
```

#### Editar o arquivo [resources/css/app.css] conforme abaixo

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

[x-cloak] {
    display: none;
}
```

#### Editar o arquivo [resources/views/layout/app.blade.php] conforme abaixo, incluindo no final do arquivo

```php
@vite(['resources/css/app.css', 'resources/js/app.js'])
```

```bash
npm run dev
npm run build

git add .
git commit -m "DEPENDENCIAS: tailwind install"
```

### ALPINE [Getting Started with TALL stack](https://devdojo.com/thinkverse/getting-started-with-tall-stack)

```bash
npm install alpinejs
```

#### Editar o arquivo [resources/js/app.js] e acrescentar as linhas abaixo ao final do arquivo

```javascript
import Alpine from 'alpinejs'
Alpine.start()
window.Alpine = Alpine
```

```bash
npm run dev
npm run build

git add .
git commit -m "DEPENDENCIAS: alpine install"
```
