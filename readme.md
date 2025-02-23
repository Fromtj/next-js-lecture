# Next.js for Beginners

## 1. Что такое Next.js?

Next.js — это современный фреймворк для создания веб-приложений, разработанный Vercel. Он построен на React.js и решает основные проблемы React, связанные с серверным рендерингом (SSR). Это позволяет:

- Ускоряет загрузку страниц.
- Улучшает SEO (оптимизация для поисковых систем).

Next.js предоставляет удобные инструменты для навигации между страницами на основе файловой структуры, что упрощает маршрутизацию. Приложения могут работать как на сервере, так и в браузере.

---

## 2. Что такое Turbopack?

Turbopack — это новый модульный сборщик, который заменяет Webpack и Vite. Он:

- До 100 раз быстрее Webpack.
- До 10 раз быстрее Vite.

Turbopack помогает быстро собирать и просматривать приложения.

---

## 3. Типы приложений и их использование

Next.js подходит для создания:

- Многопользовательских веб-сайтов.
- E-commerce платформ.
- Веб-порталов.

---

## 4. Основные преимущества Next.js

- **Рендеринг**: поддержка гибридных приложений (части кода рендерятся как на сервере, так и на клиенте).
- **Маршрутизация**: маршруты на основе файловой системы.
- **Оптимизация**: встроенные инструменты для оптимизации шрифтов, скриптов и SEO.

---

## 5. Виды рендеринга

### 1. SSR (Server-Side Rendering)

Рендеринг на стороне сервера. Примеры фреймворков:

- React + Next.js
- Vue + Nuxt.js

### 2. CSR (Client-Side Rendering)

Рендеринг на стороне клиента. Примеры:

- React
- Vue
- Angular

### 3. SSG (Static Site Generation)

Предварительная генерация статических страниц. Примеры:

- React + Next.js
- Vue + Nuxt.js

### 4. SR (Static Rendering)

Использование чистого HTML и CSS.

---

## 6. Установка Next.js

1. Введите в консоль: `npx create-next-app@latest`.
2. Следуйте инструкциям: введите `y` и задайте имя проекта.
3. Для запуска с Turbopack используйте: `npm run dev --turbo`.

Ваш проект по умолчанию будет доступен на `localhost:3000`.

---

## 7. Основные папки и файлы в проекте

- **node_modules**: зависимости проекта.
- **public**: статические файлы, доступные из корня сайта.
- **src**: основная папка с кодом, компонентами и логикой.
- **global.css**: общий файл стилей.
- **layout.jsx**: настройка метаданных, глобальных шрифтов и макета.
- **page.jsx**: главная страница приложения.

---

## 8. Стилизация в Next.js

Варианты:

- **CSS-модули**
- **Tailwind CSS**
- **Sass**
- **StyleX**

---

## 9. Маршрутизация в Next.js

Next.js использует маршрутизатор, основанный на файловой системе. Вот как это работает:

- Каждый файл внутри папки `src/app` становится страницей.
  
  - Пример: `src/app/page.jsx` — это главная страница.
  - `src/app/about/page.jsx` — страница "/about".

- Вложенные маршруты:

  - `app/blog/page.jsx` — страница "/blog".
  - `app/blog/first/page.tsx` — страница "/blog/first".

### Динамические маршруты

- Для создания динамических маршрутов используется синтаксис с квадратными скобками.
  - Пример: `app/products/[productById].jsx` — страница для каждого продукта.

### Навигация между страницами

- Для навигации используется компонент `next/link`:

```jsx
import Link from 'next/link';

<Link href="/about">О нас</Link>
```

- Можно программно изменять маршруты с помощью `useRouter`:

```jsx
import { useRouter } from 'next/router';

const router = useRouter();
router.push('/home');
```

### Страница "Не найдено"

- По умолчанию можно создать страницу `app/not-found.jsx` для отображения ошибки 404.

### Макеты (Layouts)

- Макеты используются для элементов интерфейса, общих для нескольких страниц (например, шапка, подвал).
  - Макеты можно вложить, добавляя их в соответствующие папки маршрутов.
  - Пример: `app/layout.jsx` — общий макет для всех страниц.
  - `app/dashboard/layout.jsx` — макет только для маршрутов внутри `/dashboard`.

---

## 10. Работа с изображениями и шрифтами в Next.js

### Компонент Image

Next.js предоставляет компонент `<Image>`, который:

- Оптимизирует изображения автоматически.
- Уменьшает размер файлов для ускорения загрузки.

Пример использования:

```jsx
import Image from 'next/image';

<Image src="/example.jpg" width={500} height={300} alt="Пример изображения" />
```

### Работа с шрифтами

Next.js поддерживает оптимизированные шрифты, включая Google Fonts. Это делает их использование проще и эффективнее.

Пример добавления шрифта:

```jsx
import { Roboto } from 'next/font/google';

const roboto = Roboto({ subsets: ['latin'], weight: ['400', '700'] });

export default function Home() {
  return (
    <div style={{ fontFamily: roboto.style.fontFamily }}>
      Привет, мир!
    </div>
  );
}
```

### Метаданные (Metadata)

Метаданные — это информация о данных или объекте. Next.js предоставляет больше контроля над метаданными сайта по сравнению с React. Например, можно настроить заголовки страниц, описания и другие SEO-аспекты:

```jsx
export const metadata = {
  title: 'Мой сайт',
  description: 'Описание моего сайта',
};
```

---

## 11. UI-библиотеки для Next.js

- Material UI
- Ant Design
- Material-Tailwind
- Chakra UI
- Mantine
- PrimeReact
- Shadcn/UI

---

## 12. Заключение

Next.js — это мощный инструмент для создания современных веб-приложений. Его гибкость и оптимизация делают его отличным выбором как для начинающих, так и для опытных разработчиков.

> "Самое важное — не то, как быстро вы движетесь, а то, что вы продолжаете идти вперёд."

