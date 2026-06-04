# SolidJS — Полное руководство на русском

> Версия SolidJS: 1.9.x  
> Все примеры на TypeScript  
> Источник: docs.solidjs.com

---

## Содержание

### Часть I — Введение
1. [Что такое SolidJS](#1-что-такое-solidjs)
2. [Сравнение с другими фреймворками](#2-сравнение-с-другими-фреймворками)
3. [Установка и первый проект](#3-установка-и-первый-проект)

### Часть II — JavaScript / TypeScript фундамент (для Python разработчиков)
4. [JS отличия от Python](#4-js-отличия-от-python)
5. [TypeScript фундамент](#5-typescript-фундамент)
6. [Async / Await / Promise](#6-async--await--promise)

### Часть III — Реактивность
7. [createSignal — полный API](#7-createsignal--полный-api)
8. [createEffect](#8-createeffect)
9. [createMemo](#9-creatememo)
10. [Реактивный граф под капотом](#10-реактивный-граф-под-капотом)
11. [createRenderEffect](#11-createrendereffect)
12. [createDeferred](#12-createdeferred)
13. [createReaction](#13-createreaction)
14. [createSelector](#14-createselector)
15. [untrack — выход из реактивности](#15-untrack--выход-из-реактивности)
16. [batch — батчинг обновлений](#16-batch--батчинг-обновлений)
17. [on() — явные зависимости](#17-on--явные-зависимости)
18. [🛠 Практика: автокомплит с дебаунсом](#18--практика-автокомплит-с-дебаунсом)

### Часть IV — Компоненты
19. [Основы компонентов](#19-основы-компонентов)
20. [Пропсы](#20-пропсы)
21. [mergeProps и splitProps](#21-mergeprops-и-splitprops)
22. [children helper](#22-children-helper)
23. [Типы компонентов](#23-типы-компонентов)
24. [Refs](#24-refs)
25. [\<Dynamic\>](#25-dynamic)
26. [\<Portal\>](#26-portal)
27. [lazy() — code splitting](#27-lazy--code-splitting)
28. [🛠 Практика: переиспользуемый Modal с фокус-ловушкой](#28--практика-переиспользуемый-modal-с-фокус-ловушкой)

### Часть V — Управление потоком
29. [\<Show\>](#29-show)
30. [\<For\> vs \<Index\>](#30-for-vs-index)
31. [\<Switch\> / \<Match\>](#31-switch--match)
32. [\<ErrorBoundary\>](#32-errorboundary)
33. [🛠 Практика: дискриминированные состояния UI](#33--практика-дискриминированные-состояния-ui)

### Часть VI — Lifecycle
34. [onMount / onCleanup](#34-onmount--oncleanup)
35. [onError](#35-onerror)

### Часть VII — Stores
36. [createStore](#36-createstore)
37. [Обновление через путь](#37-обновление-через-путь)
38. [produce — мутации](#38-produce--мутации)
39. [reconcile](#39-reconcile)
40. [unwrap](#40-unwrap)
41. [createMutable](#41-createmutable)
42. [🛠 Практика: канбан-доска с drag-and-drop](#42--практика-канбан-доска-с-drag-and-drop)

### Часть VIII — Context
43. [createContext / useContext](#43-createcontext--usecontext)
44. [Паттерн Provider + Hook](#44-паттерн-provider--hook)
45. [Множественные контексты](#45-множественные-контексты)

### Часть IX — Async и данные
46. [createResource](#46-createresource)
47. [\<Suspense\>](#47-suspense)
48. [\<SuspenseList\>](#48-suspenselist)
49. [useTransition / startTransition](#49-usetransition--starttransition)
50. [🛠 Практика: infinite scroll с пагинацией](#50--практика-infinite-scroll-с-пагинацией)

### Часть X — Роутинг
51. [@solidjs/router основы](#51-solidjsrouter-основы)
52. [Вложенные роуты и Outlet](#52-вложенные-роуты-и-outlet)
53. [Лэйауты](#53-лэйауты)
54. [Защищённые роуты](#54-защищённые-роуты)
55. [useSearchParams, useLocation, useNavigate](#55-usesearchparams-uselocation-usenavigate)
56. [Загрузка данных на уровне роута](#56-загрузка-данных-на-уровне-роута)

### Часть XI — Формы (НОВАЯ)
57. [Контролируемые инпуты](#57-контролируемые-инпуты)
58. [Все типы полей](#58-все-типы-полей)
59. [Валидация](#59-валидация)
60. [Отправка формы и состояния](#60-отправка-формы-и-состояния)
61. [Динамические формы](#61-динамические-формы)
62. [Библиотеки форм: @modular-forms/solid](#62-библиотеки-форм-modular-formssolid)
63. [🛠 Практика: форма регистрации с валидацией](#63--практика-форма-регистрации-с-валидацией)

### Часть XII — Работа с DOM и интеграции (НОВАЯ)
64. [Refs и DOM API](#64-refs-и-dom-api)
65. [События окна и документа](#65-события-окна-и-документа)
66. [Анимации через CSS и Web Animations API](#66-анимации-через-css-и-web-animations-api)
67. [Интеграция с Canvas](#67-интеграция-с-canvas)
68. [Интеграция с не-Solid библиотеками](#68-интеграция-с-не-solid-библиотеками)
69. [🛠 Практика: drag-and-drop без библиотек](#69--практика-drag-and-drop-без-библиотек)

### Часть XIII — TypeScript глубоко (ПЕРЕРАБОТАНО)
70. [Дискриминированные unions для состояний](#70-дискриминированные-unions-для-состояний)
71. [Типизация props.children как функции](#71-типизация-propschildren-как-функции)
72. [Generic components — все способы](#72-generic-components--все-способы)
73. [Типизация custom directives](#73-типизация-custom-directives)
74. [satisfies оператор для props](#74-satisfies-оператор-для-props)
75. [JSX типы и event handlers](#75-jsx-типы-и-event-handlers)
76. [Полиморфные компоненты (as prop)](#76-полиморфные-компоненты-as-prop)

### Часть XIV — Продвинутые темы
77. [SSR — Server-Side Rendering](#77-ssr--server-side-rendering)
78. [Hydration](#78-hydration)
79. [createComputed](#79-createcomputed)
80. [createRoot / runWithOwner / getOwner](#80-createroot--runwithowner--getowner)
81. [Custom directives (use:)](#81-custom-directives-use)
82. [Custom primitives — библиотека](#82-custom-primitives--библиотека)

### Часть XV — Стилизация
83. [UnoCSS подробно](#83-unocss-подробно)
84. [CSS Modules](#84-css-modules)
85. [style атрибут](#85-style-атрибут)
86. [classList](#86-classlist)

### Часть XVI — Тестирование
87. [Vitest + @solidjs/testing-library](#87-vitest--solidjstesting-library)
88. [Тестирование сигналов, стора, контекста](#88-тестирование-сигналов-стора-контекста)
89. [Моки fetch и async](#89-моки-fetch-и-async)
90. [E2E через Playwright](#90-e2e-через-playwright)

### Часть XVII — Debugging и Devtools (НОВАЯ)
91. [Solid Devtools — установка и обзор](#91-solid-devtools--установка-и-обзор)
92. [Чтение реактивного графа в devtools](#92-чтение-реактивного-графа-в-devtools)
93. [Типичные проблемы реактивности](#93-типичные-проблемы-реактивности)
94. [Логирование сигналов и эффектов](#94-логирование-сигналов-и-эффектов)
95. [Стектрейсы из реактивных вычислений](#95-стектрейсы-из-реактивных-вычислений)

### Часть XVIII — Производительность (УГЛУБЛЕНО)
96. [Профилирование через Devtools](#96-профилирование-через-devtools)
97. [Анти-паттерны производительности](#97-анти-паттерны-производительности)
98. [Виртуализация списков](#98-виртуализация-списков)
99. [Code splitting и lazy](#99-code-splitting-и-lazy)
100. [Когда createSelector действительно нужен](#100-когда-createselector-действительно-нужен)

### Часть XIX — SolidStart (БОЛЬШАЯ ЧАСТЬ)
101. [Что такое SolidStart](#101-что-такое-solidstart)
102. [Создание проекта и структура](#102-создание-проекта-и-структура)
103. [File-based routing](#103-file-based-routing)
104. [Server functions ("use server")](#104-server-functions-use-server)
105. [Actions и формы с прогрессивным enhancement](#105-actions-и-формы-с-прогрессивным-enhancement)
106. [Загрузка данных: query, createAsync, preload](#106-загрузка-данных-query-createasync-preload)
107. [Cookies и сессии](#107-cookies-и-сессии)
108. [Middleware](#108-middleware)
109. [API routes](#109-api-routes)
110. [SSR / SSG / SPA стратегии рендера](#110-ssr--ssg--spa-стратегии-рендера)
111. [Streaming и Suspense на сервере](#111-streaming-и-suspense-на-сервере)
112. [Deploy: Vercel, Netlify, Cloudflare, Node](#112-deploy-vercel-netlify-cloudflare-node)

### Часть XX — Экосистема
113. [Kobalte](#113-kobalte)
114. [Solid Primitives](#114-solid-primitives)
115. [TanStack Query for Solid](#115-tanstack-query-for-solid)

### Часть XXI — Анти-паттерны (НОВАЯ)
116. [Деструктуризация props](#116-деструктуризация-props)
117. [Сигналы вне реактивного скоупа](#117-сигналы-вне-реактивного-скоупа)
118. [Эффекты вместо мемо](#118-эффекты-вместо-мемо)
119. [Перебор с подписками](#119-перебор-с-подписками)
120. [Index когда нужен For (и наоборот)](#120-index-когда-нужен-for-и-наоборот)
121. [Прямая мутация store](#121-прямая-мутация-store)
122. [Забытый onCleanup](#122-забытый-oncleanup)

### Часть XXII — Практика и справочники
123. [Финальный проект — блог с авторизацией](#123-финальный-проект--блог-с-авторизацией)
124. [Структура проекта в продакшене](#124-структура-проекта-в-продакшене)
125. [Полная шпаргалка API](#125-полная-шпаргалка-api)
126. [UnoCSS шпаргалка](#126-unocss-шпаргалка)
127. [Частые ошибки и решения](#127-частые-ошибки-и-решения)
128. [Глоссарий специфичных терминов](#128-глоссарий-специфичных-терминов)
129. [Полезные ссылки](#129-полезные-ссылки)

### Часть XXIII — Дополнительные практические примеры
130. [🛠 Toast система через Context](#130--toast-система-через-context)
131. [🛠 Тёмная тема с тремя состояниями](#131--тёмная-тема-с-тремя-состояниями)
132. [🛠 Data table с URL-синхронизацией](#132--data-table-с-url-синхронизацией)
133. [🛠 Файловый загрузчик с прогрессом и preview](#133--файловый-загрузчик-с-прогрессом-и-preview)

---
---

# Часть I — Введение

## 1. Что такое SolidJS

SolidJS — современный JavaScript фреймворк для создания пользовательских интерфейсов. Создатель — Ryan Carniato (Principal Engineer at Netlify), разработка ведётся с 2018 года.

### Главные принципы

**1. Fine-grained reactivity (гранулярная реактивность)**

Когда данные меняются — обновляется только конкретный DOM узел который их использует. Не пересчитывается виртуальный DOM, не перезапускается компонент.

**2. Компоненты запускаются один раз**

Компонент — это функция-инициализатор. Она вызывается при монтировании, настраивает реактивную систему, и больше никогда не запускается.

```tsx
const Counter = () => {
  console.log("Это выведется ОДИН раз"); // ← запустится только при монтировании
  
  const [count, setCount] = createSignal(0);
  
  return <button onClick={() => setCount(count() + 1)}>{count()}</button>;
};
```

**3. Без Virtual DOM**

SolidJS компилирует JSX в прямые DOM операции. Никакого диффинга — изменения сразу применяются к нужным узлам.

**4. Signals — единая модель реактивности**

Сигналы — фундамент всей реактивности. Из них строится всё: эффекты, мемо, ресурсы, сторы.

### Преимущества

- **Производительность** — стабильно входит в топ-3 самых быстрых фреймворков (js-framework-benchmark)
- **Размер бандла** — ~7 KB gzipped
- **Простая ментальная модель** — нет stale closures, нет правил хуков, нет dependency arrays
- **TypeScript first** — отличная поддержка типов из коробки
- **JSX совместимый синтаксис**

### Где используется

- Дашборды и админ-панели (real-time данные)
- Веб-приложения с высокой интерактивностью
- Игры и визуализации
- Embedded UI (благодаря маленькому бандлу)
- Любые приложения где важна скорость

---

## 2. Сравнение с другими фреймворками

| Характеристика | React | Vue 3 | Angular | SolidJS |
|---|---|---|---|---|
| Реактивность | Virtual DOM | Прокси + рендер | Zone.js / Signals | Fine-grained signals |
| Размер (gzipped) | ~45 KB | ~34 KB | ~140 KB | ~7 KB |
| Компонент перезапускается | Да, при каждом рендере | Один раз | Один раз | Один раз |
| State | useState / useReducer | ref / reactive | signals (v17+) | createSignal |
| Side effects | useEffect | watchEffect | effects | createEffect |
| Computed values | useMemo | computed | computed | createMemo |
| Списки | .map() с key | v-for | *ngFor | \<For\> |
| Условия | && / ternary | v-if | *ngIf | \<Show\> |
| Templating | JSX | Templates | Templates | JSX |
| Скорость рендера | Хорошая | Хорошая | Средняя | Очень высокая |

### Ментальная модель — что это значит для разработчика

В большинстве UI фреймворков (React особенно) единица работы — это **ре-рендер компонента**. Когда меняется state — компонент перезапускается, фреймворк сравнивает новый результат со старым, применяет изменения.

В SolidJS единица работы — это **узел реактивного графа**. Сигналы знают какие эффекты от них зависят. При изменении сигнала запускаются только нужные эффекты — компоненты вообще не задействованы после монтирования.

Это даёт три практических следствия:
1. **Нет stale closure problems** — все колбэки всегда видят актуальные значения
2. **useMemo / useCallback не нужны** — компонент не перезапускается, нечего мемоизировать
3. **Реактивность зависит от вызова сигнала** — забыл скобки `count()` → подписки нет → реактивность сломана

---

## 3. Установка и первый проект

### Требования

- Node.js 18+
- pnpm / npm / yarn
- Любой IDE (PyCharm/WebStorm/VS Code)

### Создание проекта

```bash
pnpm create solid
```

Скрипт задаст вопросы:
```
Project name: my-app
Project type: SolidJS + Vite
Use TypeScript: Yes
Template: with-unocss (или базовый)
```

### Запуск

```bash
cd my-app
pnpm install
pnpm dev
```

Откроется dev сервер на `http://localhost:3000`.

### Структура проекта

```
my-app/
├── src/
│   ├── App.tsx              ← главный компонент
│   ├── index.tsx            ← точка входа
│   └── index.css            ← глобальные стили
├── index.html               ← HTML шаблон
├── vite.config.ts           ← конфиг Vite
├── tsconfig.json            ← конфиг TypeScript
└── package.json
```

### Точка входа — index.tsx

```tsx
import { render } from "solid-js/web";
import "./index.css";
import App from "./App";

const root = document.getElementById("root");

render(() => <App />, root!);
```

### Минимальный App.tsx

```tsx
import { Component, createSignal } from "solid-js";

const App: Component = () => {
  const [count, setCount] = createSignal(0);

  return (
    <div>
      <h1>Counter: {count()}</h1>
      <button onClick={() => setCount(count() + 1)}>+1</button>
    </div>
  );
};

export default App;
```

### Установка в существующий проект

```bash
pnpm add solid-js
pnpm add -D vite-plugin-solid typescript
```

`vite.config.ts`:
```ts
import { defineConfig } from "vite";
import solidPlugin from "vite-plugin-solid";

export default defineConfig({
  plugins: [solidPlugin()],
});
```

`tsconfig.json` — главное настроить JSX:
```json
{
  "compilerOptions": {
    "jsx": "preserve",
    "jsxImportSource": "solid-js",
    "moduleResolution": "bundler",
    "strict": true,
    "target": "ESNext"
  }
}
```

---
---

# Часть II — JavaScript / TypeScript фундамент (для Python разработчиков)

## 4. JS отличия от Python

Эта глава — для тех кто пришёл из Python. Освежает JS-специфичные моменты которые отличаются от Python. Подробное введение в JS не даётся — предполагается базовое знакомство.

### Переменные

```ts
const name = "Jesus";   // не меняется — используй по умолчанию (как Python tuple)
let age = 25;           // можно менять (как Python переменная)
// var — устаревшее, не используй
```

**Правило:** начинай с `const`. Если IDE подскажет что значение меняется — поменяй на `let`.

### Типы — отличия от Python

| Python | JavaScript |
|---|---|
| `None` | `null` (явно пусто), `undefined` (не задано) |
| `int`, `float` | `number` (нет различия) |
| `True`, `False` | `true`, `false` |
| `dict` | объект `{}` |
| `list` | массив `[]` |
| `tuple` | массив `[]` (но в TS можно зафиксировать через `as const`) |

### Объекты — словари в JS

```ts
// Python: user = {"name": "Jesus", "age": 25}
const user = { name: "Jesus", age: 25 };

// Обращение — два способа
user.name      // "Jesus" — обычно используется
user["name"]   // "Jesus" — когда ключ в переменной
```

### Массивы — методы которые отличаются от Python

```ts
const nums = [1, 2, 3, 4, 5];

// map / filter / reduce — есть в обоих, но в JS это методы массива
nums.map((n) => n * 2);                  // Python: [n*2 for n in nums]
nums.filter((n) => n > 2);               // Python: [n for n in nums if n > 2]
nums.reduce((acc, n) => acc + n, 0);     // Python: sum(nums) или functools.reduce

// find — первый подходящий
nums.find((n) => n > 3);                 // Python: next((n for n in nums if n > 3), None)

// includes — есть ли элемент
nums.includes(3);                        // Python: 3 in nums

// sort — мутирует массив! (в Python list.sort() тоже мутирует, sorted() — нет)
[...nums].sort((a, b) => a - b);         // Копируем перед сортировкой через spread
```

**Важное отличие:** в JS `arr.sort()` БЕЗ компаратора сортирует как строки. Всегда передавай функцию сравнения:

```ts
[10, 1, 2].sort();              // ["1", "10", "2"] — НЕПРАВИЛЬНО для чисел
[10, 1, 2].sort((a, b) => a - b); // [1, 2, 10] — правильно
```

### Spread оператор

В JS `...` — мощный универсальный оператор:

```ts
// Копирование объекта с изменением (Python: {**user, "age": 26})
const updated = { ...user, age: 26 };

// Объединение массивов (Python: [*a, *b])
const merged = [...arr1, ...arr2];

// Распаковка аргументов
function greet(...names: string[]) { /* names — массив */ }
greet("a", "b", "c");
```

### Деструктуризация

В Python есть unpacking — в JS похожее но шире:

```ts
// Из массива
const [a, b, ...rest] = [1, 2, 3, 4, 5];

// Из объекта (в Python такого нет, нужно явно)
const { name, age } = user;

// С переименованием
const { name: userName } = user;

// С default значением
const { theme = "light" } = settings;
```

**КРИТИЧЕСКИ ВАЖНО для SolidJS:** не деструктурируй props в компонентах. Об этом подробно в разделе 20.

### Стрелочные функции

В Python нет аналога стрелочной функции — лямбды ограничены одним выражением. В JS:

```ts
// Одно выражение — return неявный
const double = (n: number) => n * 2;

// Тело с возвратом
const calc = (a: number, b: number) => {
  const sum = a + b;
  return sum * 2;
};

// Возврат объекта — обернуть в скобки
const makeUser = (name: string) => ({ name, age: 25 });
//                                  ^ без скобок JS подумает что это блок
```

### Сравнение — всегда строгое

```ts
// ❌ == делает приведение типов — НЕ используй
1 == "1"     // true (!)
0 == false   // true (!)

// ✅ === строгое сравнение
1 === "1"    // false
0 === false  // false
```

В Python `==` строгое (с учётом типа в большинстве случаев). В JS используется `===`. ESLint обычно ругается на `==`.

### Nullish coalescing — `??`

```ts
// Если хочешь default только для null/undefined (не для 0 или "")
const port = config.port ?? 3000;

// Отличие от ||
0 || 3000      // 3000 (0 — falsy)
0 ?? 3000      // 0 (только null/undefined)

"" || "default"  // "default"
"" ?? "default"  // ""
```

В Python аналог — `value if value is not None else default`.

### Опциональная цепочка — `?.`

```ts
const name = user?.profile?.name;
// Если user или profile равны null/undefined → undefined
// Без падения

// Вызов метода
const result = obj?.method?.();

// Массив
const first = arr?.[0];
```

В Python есть похожее в pydantic/SQLAlchemy через `.first()`, но это библиотечное.

### Импорты и экспорты

В JS два вида экспортов — named и default. Это отличается от Python:

```ts
// helpers.ts
export const greet = (name: string) => `Hi ${name}`;    // named
export const PI = 3.14;                                  // named

const App = () => <div />;
export default App;                                       // default (один в файле)
```

```ts
// Использование
import { greet, PI } from "./helpers";    // named — нужны фигурные скобки
import App from "./App";                  // default — без скобок, имя любое
import * as helpers from "./helpers";     // namespace
import type { User } from "./types";      // только тип (компилируется в ничто)
```

### События в JS

В JS есть глобальные события — `addEventListener`. В Python веб-фреймворки этого обычно не имеют (они серверные).

```ts
window.addEventListener("resize", handler);
document.addEventListener("keydown", handler);
element.addEventListener("click", handler);

// Снятие (обязательно — иначе утечка памяти)
window.removeEventListener("resize", handler);
```

В SolidJS события на элементах через JSX:
```tsx
<button onClick={(e) => handle(e)}>Click</button>
```

### Что ещё стоит знать для SolidJS

- **JSX синтаксис** — HTML-подобный код внутри JS. Компилируется в DOM операции
- **Замыкания (closures)** — функции захватывают переменные из окружающего скоупа. Как в Python
- **Promise / async / await** — следующий раздел

---

## 5. TypeScript фундамент

TypeScript — это JavaScript + статическая типизация. Похоже на Python с type hints + mypy, но более глубоко интегрирован в язык.

### Базовая типизация

```ts
const name: string = "Jesus";          // как str
const age: number = 25;                 // как int/float
const isActive: boolean = true;         // как bool
const skills: string[] = ["TS", "Solid"]; // как list[str]
const user: { name: string; age: number } = { name: "Jesus", age: 25 };
```

TS обычно сам выводит тип:

```ts
const name = "Jesus";  // TS знает что это string
const age = 25;        // TS знает что это number
```

### Интерфейсы

Описывают форму объекта (аналог TypedDict / pydantic BaseModel в Python):

```ts
interface User {
  id: number;
  name: string;
  email: string;
  age?: number;              // опциональное (как Optional[int])
  readonly createdAt: Date;  // нельзя изменить (как final)
}

const user: User = {
  id: 1,
  name: "Jesus",
  email: "j@example.com",
  createdAt: new Date(),
};
```

### Расширение интерфейсов

```ts
interface Animal {
  name: string;
}

interface Dog extends Animal {
  breed: string;
}
```

### Type aliases

`type` — альтернатива `interface`, более гибкая:

```ts
type ID = number | string;                          // union
type Status = "active" | "inactive" | "pending";    // literal union
type Point = { x: number; y: number };              // объект как тип

// Пересечение типов
type Employee = User & { department: string };
```

**Когда что использовать:**
- `interface` — для объектов и классов
- `type` — для union, primitives, сложных композиций

### Union типы — мощная штука

В Python — `Union[X, Y]` или `X | Y` (Python 3.10+). В TS работает гораздо лучше:

```ts
type Status = "loading" | "success" | "error";

const handleStatus = (status: Status) => {
  if (status === "loading") return "⏳";
  if (status === "success") return "✅";
  return "❌";
};

handleStatus("invalid"); // ❌ Ошибка типа — компилятор не пропустит
```

### Дискриминированные unions (важно для SolidJS!)

Это самый мощный паттерн в TypeScript — используем активно в разделе 70.

```ts
type FetchState<T> =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: T }
  | { status: "error"; error: string };

const render = (state: FetchState<User>) => {
  switch (state.status) {
    case "idle":
      return "Не начато";
    case "loading":
      return "Загрузка...";
    case "success":
      return state.data.name;       // TS знает что data есть
    case "error":
      return state.error;            // TS знает что error есть
  }
};
```

Это даёт **гарантию типов на уровне компилятора** — невозможно прочитать `data` пока ты не проверил что `status === "success"`.

### Дженерики

Делают функции и типы универсальными (как `TypeVar` в Python typing):

```ts
function identity<T>(value: T): T {
  return value;
}

identity<string>("hello");  // T = string
identity(42);               // T = number (выведен сам)

// Дженерик с ограничением (как TypeVar(bound=...))
function getId<T extends { id: number }>(item: T): number {
  return item.id;
}
```

### Дженерики в интерфейсах

```ts
interface ApiResponse<T> {
  data: T;
  status: number;
  error?: string;
}

const userResponse: ApiResponse<User> = { data: { ... }, status: 200 };
const listResponse: ApiResponse<User[]> = { data: [...], status: 200 };
```

### Utility типы — самое нужное

```ts
interface User {
  id: number;
  name: string;
  email: string;
  age: number;
}

// Partial — все поля опциональные (как Python TypedDict total=False)
type UserUpdate = Partial<User>;
// { id?: number; name?: string; email?: string; age?: number }

// Required — все обязательные
type StrictUser = Required<User>;

// Pick — взять только указанные поля
type UserPreview = Pick<User, "id" | "name">;

// Omit — исключить поля
type UserPublic = Omit<User, "email">;

// Readonly — все поля только для чтения
type FrozenUser = Readonly<User>;

// Record — словарь с известными ключами
type Permissions = Record<"admin" | "user" | "guest", boolean>;

// ReturnType — тип возвращаемого значения функции
function getUser() { return { name: "Jesus", age: 25 }; }
type UserType = ReturnType<typeof getUser>;
// { name: string; age: number }

// Parameters — типы параметров функции
type GetUserParams = Parameters<typeof getUser>;
// []

// Awaited — развернуть Promise
type UserData = Awaited<ReturnType<typeof fetchUser>>;
```

### Type assertions

```ts
const value = "hello" as string;
const elem = document.getElementById("root") as HTMLDivElement;

// Двойное assertion (если TS не пропускает)
const num = ("123" as unknown) as number;
```

### as const — заморозка значения

```ts
// Без as const — тип string[]
const colors = ["red", "green", "blue"];

// С as const — тип readonly ["red", "green", "blue"]
const colors = ["red", "green", "blue"] as const;

// Полезно для констант
const STATUS = {
  ACTIVE: "active",
  INACTIVE: "inactive",
} as const;
// STATUS.ACTIVE имеет тип "active", не string
```

### satisfies оператор

Новый оператор (TS 4.9+). Проверяет соответствие типу но сохраняет конкретный тип значения:

```ts
type RouteConfig = Record<string, { path: string; auth?: boolean }>;

// Без satisfies — теряем точные ключи
const routes: RouteConfig = {
  home: { path: "/" },
  profile: { path: "/profile", auth: true },
};
routes.home;     // тип: { path: string; auth?: boolean }
routes.unknown;  // TS не ругается — RouteConfig индексируется любой строкой

// С satisfies — сохраняем точные ключи
const routes = {
  home: { path: "/" },
  profile: { path: "/profile", auth: true },
} satisfies RouteConfig;
routes.home;     // тип: { path: string }
routes.unknown;  // ❌ Ошибка — такого ключа нет
```

Используем в SolidJS для props (раздел 74).

### Non-null assertion (!)

Говорит TS "это точно не null/undefined":

```ts
const elem = document.getElementById("root")!;  // HTMLElement (без ! было бы | null)

let ref!: HTMLInputElement;  // ref будет инициализирован позже
```

Используй осторожно — если ошибёшься, получишь runtime ошибку.

### Type guards — сужение типа

```ts
function isString(value: unknown): value is string {
  return typeof value === "string";
}

const value: unknown = "hello";
if (isString(value)) {
  value.toUpperCase(); // TS знает что value: string
}
```

---

## 6. Async / Await / Promise

Async код в JS похож на Python `asyncio`. Главные отличия:
- В JS асинхронность встроена в язык (event loop в браузере)
- `await` можно использовать только в `async` функции
- В JS чаще используют `async/await`, в Python — оба стиля

### Promise — что это

Promise — объект который представляет асинхронную операцию. Три состояния: `pending`, `fulfilled`, `rejected`.

```ts
const promise = new Promise<string>((resolve, reject) => {
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("Успех!");
    } else {
      reject(new Error("Провал"));
    }
  }, 1000);
});
```

### async / await

Современный синтаксис для работы с Promise (аналог Python `async def` / `await`):

```ts
async function fetchUser(id: number): Promise<User> {
  const response = await fetch(`/api/users/${id}`);
  const user = await response.json();
  return user;
}

// Стрелочная — так чаще пишут в SolidJS
const fetchUser = async (id: number): Promise<User> => {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
};

// Использование
const user = await fetchUser(1);
```

### try / catch

```ts
const fetchUser = async (id: number): Promise<User | null> => {
  try {
    const response = await fetch(`/api/users/${id}`);
    if (!response.ok) {
      throw new Error(`HTTP ${response.status}`);
    }
    return await response.json();
  } catch (error) {
    console.error("Ошибка загрузки:", error);
    return null;
  }
};
```

### Promise.all — параллельная загрузка

Аналог `asyncio.gather()` в Python:

```ts
const loadDashboard = async () => {
  const [user, projects, notifications] = await Promise.all([
    fetchUser(1),
    fetchProjects(),
    fetchNotifications(),
  ]);
  
  return { user, projects, notifications };
};
```

Все три запроса идут параллельно. Если делать через последовательный `await` — будет в 3 раза медленнее.

### Promise.allSettled — игнорировать ошибки

`Promise.all` падает если хоть один Promise rejected. `Promise.allSettled` возвращает результат всех:

```ts
const results = await Promise.allSettled([
  fetchUser(1),
  fetchUser(2),
  fetchUser(3),
]);

results.forEach((result) => {
  if (result.status === "fulfilled") {
    console.log(result.value);
  } else {
    console.error(result.reason);
  }
});
```

### Fetch API

Стандартный способ HTTP запросов в браузере:

```ts
// GET
const response = await fetch("/api/users");
const users = await response.json();

// С параметрами
const response = await fetch(`/api/users?limit=10&offset=20`);

// POST
const response = await fetch("/api/users", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ name: "Jesus", age: 25 }),
});

// С авторизацией
const response = await fetch("/api/users/me", {
  headers: { "Authorization": `Bearer ${token}` },
});

// Проверка статуса
if (!response.ok) {
  throw new Error(`HTTP ${response.status}`);
}
```

### Типизированный fetch wrapper

В реальных проектах часто пишут обёртку:

```ts
async function api<T>(url: string, options?: RequestInit): Promise<T> {
  const response = await fetch(url, {
    headers: {
      "Content-Type": "application/json",
      ...options?.headers,
    },
    ...options,
  });
  
  if (!response.ok) {
    throw new Error(`HTTP ${response.status}: ${response.statusText}`);
  }
  
  return response.json();
}

// Использование
const user = await api<User>("/api/users/1");
const users = await api<User[]>("/api/users");
const newUser = await api<User>("/api/users", {
  method: "POST",
  body: JSON.stringify({ name: "Jesus" }),
});
```

### AbortController — отмена запросов

Полезно когда пользователь быстро переключается между страницами:

```ts
const controller = new AbortController();

fetch("/api/data", { signal: controller.signal })
  .then((r) => r.json())
  .catch((err) => {
    if (err.name === "AbortError") {
      console.log("Запрос отменён");
    }
  });

// Отменить
controller.abort();
```

В SolidJS этот паттерн обычно скрыт за `createResource` — об этом в разделе 46.

---
---
---

# Часть III — Реактивность

Это самая важная часть книги. Если ты понимаешь реактивность — ты понимаешь SolidJS.

## 7. createSignal — полный API

Сигналы — основа реактивности в SolidJS. Это реактивная переменная: при изменении автоматически обновляются все места где она используется.

### Базовый синтаксис

```tsx
import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);
//     ^геттер  ^сеттер           ^начальное значение
```

### Полная сигнатура

```ts
function createSignal<T>(): Signal<T | undefined>;
function createSignal<T>(value: T, options?: SignalOptions<T>): Signal<T>;

type Signal<T> = [get: Accessor<T>, set: Setter<T>];
type Accessor<T> = () => T;
type Setter<T> = (value: T | ((prev: T) => T)) => T;

interface SignalOptions<T> {
  name?: string;
  equals?: false | ((prev: T, next: T) => boolean);
}
```

### Чтение значения

```tsx
const [count, setCount] = createSignal(0);

count();  // 0 — всегда вызывай со скобками!
```

`count` это **функция**, не значение. Забыть скобки — самая частая ошибка новичков.

### Запись значения

```tsx
// Прямое значение
setCount(5);

// Функция от предыдущего значения
setCount((prev) => prev + 1);

// Для массивов и объектов — всегда новые ссылки (как в Python с tuple)
setItems([...items(), newItem]);
setUser({ ...user(), name: "Ivan" });
```

### Типизация

```tsx
// Явный тип
const [count, setCount] = createSignal<number>(0);

// Union тип
const [status, setStatus] = createSignal<"idle" | "loading" | "error">("idle");

// Может быть null
const [user, setUser] = createSignal<User | null>(null);

// Массив
const [items, setItems] = createSignal<Item[]>([]);

// Без начального значения — добавляется undefined в тип
const [data, setData] = createSignal<Data>();
// data: () => Data | undefined
```

### Опция equals

По умолчанию SolidJS сравнивает старое и новое значение через `===`. Если значение не изменилось — обновление не происходит.

```tsx
// equals: false — обновляет всегда, даже если значение не изменилось
const [obj, setObj] = createSignal({ name: "Jesus" }, { equals: false });

// Кастомная функция сравнения
const [user, setUser] = createSignal(initialUser, {
  equals: (prev, next) => prev.id === next.id,
});
// Обновляется только когда меняется id, остальные поля игнорируются
```

**Когда полезно:**
- `equals: false` — для триггера эффектов даже при том же значении
- Кастомный equals — для сложных объектов где `===` не подходит

### Опция name (для devtools)

```tsx
const [count, setCount] = createSignal(0, { name: "counter" });
// В Solid Devtools этот сигнал будет назван "counter"
```

### Полный пример — счётчик

```tsx
import { Component, createSignal } from "solid-js";

const Counter: Component = () => {
  const [count, setCount] = createSignal(0);

  const increment = () => setCount((prev) => prev + 1);
  const decrement = () => setCount((prev) => prev - 1);
  const reset = () => setCount(0);

  return (
    <div class="flex flex-col gap-2 p-4">
      <p
        class={`text-2xl font-bold ${
          count() > 0 ? "text-green-500"
          : count() < 0 ? "text-red-500"
          : "text-gray-500"
        }`}
      >
        Счётчик: {count()}
      </p>
      <div class="flex gap-2">
        <button onClick={increment} class="bg-blue-500 text-white px-3 py-1 rounded">+1</button>
        <button onClick={decrement} class="bg-blue-500 text-white px-3 py-1 rounded">-1</button>
        <button onClick={reset} class="bg-gray-300 px-3 py-1 rounded">Сброс</button>
      </div>
    </div>
  );
};
```

### Главное правило: реактивность через ВЫЗОВ

```tsx
const [count, setCount] = createSignal(0);

// ❌ НЕ работает — count не вызывается
createEffect(() => {
  const c = count; // ссылка на функцию, не значение
  console.log(c);
});

// ✅ Работает — count() вызывается, эффект подписывается
createEffect(() => {
  console.log(count());
});
```

---

## 8. createEffect

Эффект — функция которая выполняется при изменении используемых сигналов. Для side effects: логирование, синхронизация с DOM, API запросы.

### Базовый синтаксис

```tsx
import { createSignal, createEffect } from "solid-js";

const [count, setCount] = createSignal(0);

createEffect(() => {
  console.log("count изменился:", count());
});
```

При создании эффекта он выполняется первый раз (с count = 0). Дальше — каждый раз когда `count` меняется.

### Полная сигнатура

```ts
function createEffect<T>(fn: (prev: T | undefined) => T, value?: T): void;
function createEffect<T>(fn: (prev: T) => T, value: T): void;
```

### Доступ к предыдущему значению

Эффект может возвращать значение, которое получит на следующем запуске:

```tsx
createEffect((prev) => {
  const current = count();
  console.log(`Было: ${prev}, стало: ${current}`);
  return current;
}, 0); // начальное предыдущее значение
```

### Несколько зависимостей

Эффект автоматически отслеживает ВСЕ сигналы, которые читаются внутри:

```tsx
const [firstName, setFirstName] = createSignal("Jesus");
const [lastName, setLastName] = createSignal("Yurchenko");

createEffect(() => {
  // Подписывается на оба сигнала
  console.log(`${firstName()} ${lastName()}`);
});

setFirstName("Ivan");  // эффект сработает
setLastName("Petrov"); // эффект сработает снова
```

### Условные зависимости — динамические подписки

Эффект подписывается только на те сигналы которые реально читаются в текущем запуске:

```tsx
const [showName, setShowName] = createSignal(true);
const [name, setName] = createSignal("Jesus");

createEffect(() => {
  if (showName()) {
    console.log(name()); // подписка на name создаётся
  } else {
    console.log("Имя скрыто"); // подписки на name нет
  }
});

setShowName(false);
setName("Ivan"); // эффект НЕ сработает — нет подписки на name
```

Это принципиальное отличие от React `useEffect` где зависимости фиксированы в массиве.

### Когда срабатывает

Первый запуск эффекта происходит **после** монтирования компонента — когда DOM уже создан:

```tsx
const Component: Component = () => {
  let ref!: HTMLDivElement;

  createEffect(() => {
    console.log(ref.offsetWidth); // DOM уже доступен
  });

  return <div ref={ref}>Hello</div>;
};
```

### Типичные сценарии

**1. Логирование изменений**

```tsx
createEffect(() => {
  console.log("Состояние:", state());
});
```

**2. Синхронизация с localStorage**

```tsx
const [theme, setTheme] = createSignal(localStorage.getItem("theme") ?? "light");

createEffect(() => {
  localStorage.setItem("theme", theme());
});
```

**3. Обновление title страницы**

```tsx
const [pageName, setPageName] = createSignal("Главная");

createEffect(() => {
  document.title = `${pageName()} | CGHub`;
});
```

### Опасность бесконечных циклов

Установка сигнала внутри эффекта, который от него зависит → бесконечный цикл:

```tsx
// ❌ БЕСКОНЕЧНЫЙ ЦИКЛ
createEffect(() => {
  setCount(count() + 1); // меняет count → эффект запускается снова
});
```

**Правило:** не устанавливай сигналы внутри эффектов которые их читают. Если нужно вычислить значение — используй `createMemo`.

### Очистка ресурсов

Эффект может использовать `onCleanup`:

```tsx
import { createEffect, onCleanup } from "solid-js";

createEffect(() => {
  const interval = setInterval(() => {
    console.log("tick");
  }, 1000);

  // Очистка перед следующим запуском эффекта или размонтированием
  onCleanup(() => clearInterval(interval));
});
```

### Когда НЕ использовать createEffect

Если вычисляешь значение из сигнала — используй **createMemo**:

```tsx
// ❌ Плохо — эффект для вычислений
const [doubled, setDoubled] = createSignal(0);
createEffect(() => {
  setDoubled(count() * 2);
});

// ✅ Хорошо — мемо для вычислений
const doubled = createMemo(() => count() * 2);
```

Если хочешь запустить код один раз при монтировании — **onMount**:

```tsx
// ❌ Плохо
createEffect(() => {
  console.log("Компонент смонтирован");
});

// ✅ Хорошо
onMount(() => {
  console.log("Компонент смонтирован");
});
```

---

## 9. createMemo

Мемо — вычисляемое значение которое пересчитывается только когда меняются зависимости.

### Базовый синтаксис

```tsx
import { createSignal, createMemo } from "solid-js";

const [price, setPrice] = createSignal(100);
const [quantity, setQuantity] = createSignal(3);

const total = createMemo(() => price() * quantity());

total(); // 300 — читается как сигнал
```

### Полная сигнатура

```ts
function createMemo<T>(
  fn: (prev: T | undefined) => T,
  value?: T,
  options?: MemoOptions<T>
): Accessor<T>;

interface MemoOptions<T> {
  name?: string;
  equals?: false | ((prev: T, next: T) => boolean);
}
```

### Чем отличается от вычисления в JSX

```tsx
// Вычисление в JSX — каждый раз когда JSX обновляется
<p>Сумма: {price() * quantity()}</p>

// createMemo — кэширует результат, пересчитывает только при изменении зависимостей
const total = createMemo(() => price() * quantity());
<p>Сумма: {total()}</p>
```

Разница важна когда:
1. Вычисление дорогое (сортировка, фильтрация большого массива)
2. Результат используется в нескольких местах
3. Производные эффекты должны срабатывать только при реальном изменении

### Пример — фильтрация и сортировка

```tsx
const [users, setUsers] = createSignal<User[]>([]);
const [search, setSearch] = createSignal("");
const [sortBy, setSortBy] = createSignal<"name" | "age">("name");

const filteredAndSorted = createMemo(() => {
  return users()
    .filter((u) => u.name.toLowerCase().includes(search().toLowerCase()))
    .sort((a, b) => {
      if (sortBy() === "name") return a.name.localeCompare(b.name);
      return a.age - b.age;
    });
});

<For each={filteredAndSorted()}>
  {(user) => <UserCard user={user} />}
</For>
```

Мемо пересчитается только когда изменится `users`, `search` или `sortBy`.

### Опция equals — пропуск обновлений

Если результат мемо такой же как был — подписчики не уведомляются:

```tsx
const [dateString, setDateString] = createSignal("2024-01-01");

const dateObject = createMemo(
  () => new Date(dateString()),
  undefined,
  {
    equals: (prev, next) => prev.getTime() === next.getTime(),
  }
);

createEffect(() => {
  // Запускается только когда меняется timestamp, не сама ссылка
  console.log(dateObject());
});

setDateString("2024-01-01"); // тот же date string → новый Date объект, но timestamp тот же
// Эффект НЕ запустится
```

### Цепочка мемо

Мемо могут зависеть от других мемо:

```tsx
const [items, setItems] = createSignal<CartItem[]>([]);

const subtotal = createMemo(() =>
  items().reduce((sum, item) => sum + item.price * item.quantity, 0)
);

const tax = createMemo(() => subtotal() * 0.2);

const total = createMemo(() => subtotal() + tax());

// Меняется items → пересчитывается subtotal → tax → total
```

---

## 10. Реактивный граф под капотом

Чтобы понять SolidJS глубже — нужно разобраться как работает реактивная система. Это не academic exercise — это знание поможет тебе писать эффективный код и отлаживать сложные баги.

### Узлы реактивного графа

SolidJS строит **направленный граф зависимостей** из реактивных примитивов:

- **Sources (источники)** — `createSignal`. Только пишут, не читают.
- **Computations (вычисления)** — `createMemo`, `createEffect`, `createRenderEffect`. Читают источники и реагируют на их изменения.
- **Memos** — особенные: и читают (от других сигналов/мемо), и являются источником (для подписчиков).

```
[Signal A] ──┐
             ├──> [Memo X] ──> [Effect 1]
[Signal B] ──┘                 [Effect 2]
                     │
                     └──> [Memo Y] ──> [Effect 3]
```

### Что хранит узел

Каждый узел в графе хранит:

```
Signal:
  - value: текущее значение
  - observers: Set<Computation>  ← кто на меня подписан
  - comparator: функция сравнения

Computation (Memo/Effect):
  - fn: функция-вычислитель
  - value: последнее вычисленное значение (для мемо)
  - sources: Set<Signal>  ← на кого я подписан
  - state: PRISTINE | DIRTY | PENDING | STALE
```

### Алгоритм propagation (распространения изменений)

Когда вызывается `setSignal(newValue)` — SolidJS делает следующее:

**Фаза 1 — пометка как dirty**
1. Сигнал проверяет: новое значение === старое? Если да — стоп
2. Сигнал помечает все свои observers как **DIRTY**
3. Каждый DIRTY computation помечает всех своих observers как **PENDING** (это касается мемо — они источники для своих подписчиков)
4. Распространение продолжается рекурсивно вверх по графу

**Фаза 2 — выполнение**
1. SolidJS обходит все DIRTY/PENDING computations в правильном порядке
2. Для каждого computation: запускается его функция, получается новое значение
3. Если это мемо и значение === предыдущему — observers остаются PRISTINE
4. Если значение изменилось — observers становятся DIRTY и выполнятся в свою очередь

### Состояния узла — диаграмма переходов

Узел реактивного графа всегда в одном из четырёх состояний:

```
                            ┌─ значение изменилось ──┐
                            │   (от источника)        │
                            ▼                         │
   ┌──────────────┐                          ┌────────────────┐
   │   PRISTINE   │                          │     DIRTY      │
   │ (clean/ready)│◄─── вычислен заново ────┤ (нужен пересчёт)│
   └──────────────┘     значение готово      └────────────────┘
          ▲                                          ▲
          │                                          │
          │ значение мемо не               одна из зависимостей
          │ изменилось (equals)              стала DIRTY
          │                                          │
   ┌──────────────┐                          ┌────────────────┐
   │     STALE    │                          │    PENDING     │
   │ (был DIRTY,  │◄─── зависимость осталась │ (зависимость   │
   │  но не нужно)│      без изменений       │  потенциально  │
   └──────────────┘                          │   изменилась)  │
                                             └────────────────┘
```

**Когда что происходит:**
- **PRISTINE** → **DIRTY**: подписанный сигнал изменился
- **DIRTY** → **PRISTINE**: вычислили заново, всё готово
- **PRISTINE** → **PENDING**: одна из косвенных зависимостей (через мемо) изменилась
- **PENDING** → **DIRTY**: подтвердилось что upstream мемо реально изменилось
- **PENDING** → **STALE**: upstream мемо вернуло то же значение (`equals`), нам ничего не нужно делать
- **STALE** → **PRISTINE**: помечаем как готовый и едем дальше

Это то что позволяет SolidJS пропускать лишнюю работу: если мемо в середине цепочки вернуло то же значение — нижестоящие effects не запускаются.

### Почему это эффективно

В отличие от React (где при изменении state весь компонент пересчитывается), здесь:

- **Пропуск работы при равных значениях** — мемо не обновляет observers если результат не изменился
- **Точечные обновления** — обновляются только реально зависящие узлы
- **Топологический порядок** — узлы выполняются в правильной последовательности, без двойной работы

### Пример с диаграммой

```tsx
const [price, setPrice] = createSignal(100);      // Signal A
const [qty, setQty] = createSignal(2);             // Signal B
const [tax, setTax] = createSignal(0.2);           // Signal C

const subtotal = createMemo(() => price() * qty());    // Memo X
const total = createMemo(() => subtotal() * (1 + tax())); // Memo Y

createEffect(() => {
  console.log("Total:", total());                       // Effect 1
});
```

Граф:
```
[Signal A: price]──┐
                   ├──> [Memo X: subtotal] ──┐
[Signal B: qty]────┘                          │
                                              ├──> [Memo Y: total] ──> [Effect 1]
[Signal C: tax]───────────────────────────────┘
```

**Сценарий: `setQty(3)`**

1. Signal B меняется с 2 на 3 (не равно — продолжаем)
2. Signal B помечает Memo X как DIRTY
3. Memo X помечает Memo Y как PENDING
4. Memo Y помечает Effect 1 как PENDING

Выполнение:
1. Memo X запускается: `subtotal = 100 * 3 = 300` (было 200 → изменилось)
2. Memo Y становится DIRTY, запускается: `total = 300 * 1.2 = 360` (было 240 → изменилось)
3. Effect 1 становится DIRTY, запускается: выводит "Total: 360"

### Визуализация propagation по времени

Тот же сценарий — но как time-сequence (читать сверху вниз):

```
Time │  Signal B    Memo X     Memo Y     Effect 1
     │  (qty=2)     (subtotal) (total)    (log)
─────┼──────────────────────────────────────────────
  t0 │  ━━━━━━ ▼      ⬜          ⬜          ⬜       состояние PRISTINE
     │  setQty(3) ───►│
─────┼──────────────────────────────────────────────
  t1 │     ━━━     [DIRTY]       ⬜          ⬜       Memo X помечен dirty
     │             ──────►│
─────┼──────────────────────────────────────────────
  t2 │     ━━━     [DIRTY]    [PENDING]      ⬜       Memo Y помечен pending
     │                       ──────►│
─────┼──────────────────────────────────────────────
  t3 │     ━━━     [DIRTY]    [PENDING]   [PENDING]   Effect 1 помечен pending
─────┼──────────────────────────────────────────────
       ↓ Фаза выполнения (порядок обхода — топологический)
─────┼──────────────────────────────────────────────
  t4 │     ━━━    300=100*3    [PENDING]   [PENDING]   Memo X пересчитал
     │             [PRISTINE]
─────┼──────────────────────────────────────────────
  t5 │     ━━━     [PRISTINE]  360=300*1.2 [PENDING]   Memo Y увидел новое
     │                          [PRISTINE]              значение → пересчитал
─────┼──────────────────────────────────────────────
  t6 │     ━━━     [PRISTINE]  [PRISTINE]  log("360")   Effect 1 выполнен
     │                                     [PRISTINE]
─────┴──────────────────────────────────────────────
```

Ключевое — **порядок обхода топологический**. Сначала ближе к источнику изменения, потом дальше. Это гарантирует что когда Memo Y запускается — оно читает уже свежее значение Memo X. Без этого порядка были бы лишние пересчёты.

**Сценарий: `setTax(0.2)`** (то же значение)

1. Signal C проверяет: 0.2 === 0.2 → **стоп**, ничего не происходит

**Сценарий: `setPrice(100)` → `setPrice(100)`**

То же самое — `equals` фильтрует одинаковые значения.

### Динамические подписки

Важная особенность: набор source'ов у computation **пересчитывается каждый раз** при выполнении:

```tsx
const [showName, setShowName] = createSignal(true);
const [name, setName] = createSignal("Jesus");
const [age, setAge] = createSignal(25);

createEffect(() => {
  if (showName()) {
    console.log(name());  // подписка на name создаётся
  } else {
    console.log(age());   // подписка на age создаётся
  }
});
```

Когда `showName === true` — sources эффекта = `{showName, name}`. Когда `false` — sources = `{showName, age}`.

При каждом запуске computation SolidJS:
1. Снимает все старые подписки
2. Выполняет функцию, собирает новые подписки
3. Сравнивает старые и новые, оптимизирует переподключение

Это решает проблему "useEffect с dependency array" из React — здесь зависимости всегда актуальные.

### Tracking scope (отслеживаемая область)

Сигналы создают подписку только если вызываются внутри **tracking scope**:

```tsx
// Tracking scopes:
createEffect(() => { count(); });        // ✓ подписка
createMemo(() => count() * 2);            // ✓ подписка
createRenderEffect(() => { count(); }); // ✓ подписка
<div>{count()}</div>                      // ✓ подписка (JSX — это tracking scope)

// Не tracking scope:
const value = count();                    // ✗ нет подписки — просто читает значение
console.log(count());                     // ✗ нет подписки
setTimeout(() => count(), 1000);          // ✗ нет подписки (callback вне scope)
```

### Owner tree — иерархия владельцев

Параллельно с реактивным графом существует **дерево владельцев** (owner tree). Это связано с lifecycle и cleanup:

```
<Root>                          ← createRoot
  ├─ <Component A>              ← owner для всего внутри
  │   ├─ createSignal           ← живёт пока жив owner
  │   ├─ createEffect           ← остановится когда owner размонтируется
  │   └─ <Component B>          ← вложенный owner
  │       └─ onCleanup(...)     ← запустится при размонтировании B
  └─ <Component C>
```

`onCleanup` регистрирует функцию для очистки в текущий owner. Когда owner размонтируется — все cleanup функции вызываются автоматически.

### Минимальная реализация для понимания

```ts
// Упрощённая версия — не для production
let currentObserver: Computation | null = null;

class Signal<T> {
  private observers = new Set<Computation>();
  constructor(private value: T) {}

  get(): T {
    if (currentObserver) {
      this.observers.add(currentObserver);
      currentObserver.sources.add(this);
    }
    return this.value;
  }

  set(value: T): void {
    if (this.value === value) return;  // фильтр equals
    this.value = value;
    for (const obs of this.observers) {
      obs.execute();
    }
  }
}

class Computation {
  sources = new Set<Signal<any>>();
  constructor(private fn: () => void) {
    this.execute();
  }

  execute(): void {
    // Снимаем старые подписки
    for (const src of this.sources) {
      src["observers"].delete(this);
    }
    this.sources.clear();

    // Запускаем с трекингом
    const prev = currentObserver;
    currentObserver = this;
    try {
      this.fn();
    } finally {
      currentObserver = prev;
    }
  }
}

// Использование
const count = new Signal(0);
new Computation(() => console.log("count =", count.get()));

count.set(1); // выведет: count = 1
count.set(2); // выведет: count = 2
count.set(2); // ничего — equals
```

Реальная реализация SolidJS — это десятки KB кода с оптимизациями (batching, transitions, suspense, оптимизация подписок), но принцип тот же.

### Что это даёт на практике

1. **Скорость** — обновляются только реально изменившиеся узлы
2. **Корректность** — нет stale closures, всё всегда актуально
3. **Предсказуемость** — порядок выполнения детерминирован (топологический)
4. **Лёгкая отладка** — граф можно визуализировать (Solid Devtools)

---

## 11. createRenderEffect

Похож на `createEffect`, но запускается синхронно **во время рендера**, до того как DOM показан пользователю.

### Сигнатура

```ts
function createRenderEffect<T>(fn: (prev: T) => T, value?: T): void;
```

### Когда использовать

Обычно никогда — для большинства задач подходит `createEffect`. RenderEffect полезен для:
- Установки атрибутов DOM до отрисовки
- Синхронизации с внешними системами рендера

### Отличие от createEffect

```tsx
const Counter: Component = () => {
  const [count, setCount] = createSignal(0);

  console.log("1. Setup");

  createEffect(() => {
    console.log("3. Effect:", count()); // после рендера
  });

  createRenderEffect(() => {
    console.log("2. RenderEffect:", count()); // во время рендера
  });

  return <button onClick={() => setCount(count() + 1)}>{count()}</button>;
};

// При монтировании:
// 1. Setup
// 2. RenderEffect: 0
// 3. Effect: 0
```

В 99% случаев используй `createEffect`.

---

## 12. createDeferred

Создаёт реактивное значение которое обновляется не сразу, а когда браузер свободен (через `requestIdleCallback`).

### Сигнатура

```ts
function createDeferred<T>(
  source: Accessor<T>,
  options?: { timeoutMs?: number; equals?: false | ((a: T, b: T) => boolean) }
): Accessor<T>;
```

### Использование

```tsx
const [search, setSearch] = createSignal("");

// Отложенное значение — обновится когда браузер свободен
const deferredSearch = createDeferred(search, { timeoutMs: 250 });

// Тяжёлая фильтрация работает на отложенном значении
const results = createMemo(() => {
  return expensiveFilter(items(), deferredSearch());
});

// Инпут реагирует мгновенно, фильтрация — с задержкой
<input value={search()} onInput={(e) => setSearch(e.target.value)} />
<For each={results()}>{(item) => <Item item={item} />}</For>
```

**Когда полезно:** при быстром вводе в поиск, чтобы не блокировать UI тяжёлыми вычислениями.

---

## 13. createReaction

Реакция — отдельный эффект для **одноразового** срабатывания при изменении.

### Сигнатура

```ts
function createReaction(onInvalidate: () => void): (fn: () => void) => void;
```

### Использование

```tsx
import { createSignal, createReaction } from "solid-js";

const [count, setCount] = createSignal(0);

const track = createReaction(() => {
  console.log("Изменение обнаружено!");
});

// Указываем что отслеживать
track(() => count());

setCount(1); // выведет "Изменение обнаружено!"
setCount(2); // НЕ выведет — реакция одноразовая

// Нужно перерегистрировать
track(() => count());
setCount(3); // снова сработает
```

**Когда полезно:** для one-time подписок ("сработай один раз при первом изменении").

---

## 14. createSelector

Оптимизация для случая когда у тебя много элементов и нужно знать какой из них выбран.

### Без createSelector — медленно

```tsx
const [selectedId, setSelectedId] = createSignal(1);

<For each={items()}>
  {(item) => (
    <div class={selectedId() === item.id ? "selected" : ""}>
      {item.name}
    </div>
  )}
</For>
```

При изменении `selectedId` — пересчитываются ВСЕ элементы списка.

### С createSelector — быстро

```tsx
import { createSelector } from "solid-js";

const [selectedId, setSelectedId] = createSignal(1);
const isSelected = createSelector(selectedId);

<For each={items()}>
  {(item) => (
    <div class={isSelected(item.id) ? "selected" : ""}>
      {item.name}
    </div>
  )}
</For>
```

`createSelector` ведёт keyed-подписки — обновляются только два элемента: тот что был выбран и тот что стал.

Под капотом это работает так: для каждого вызова `isSelected(item.id)` создаётся keyed подписка. Когда `selectedId` меняется с 1 на 5 — нотифицируются только подписки с key=1 и key=5.

**Когда полезно:** списки 100+ элементов с выделением. О реальной выгоде подробнее в разделе 100.

---

## 15. untrack — выход из реактивности

`untrack` позволяет прочитать сигнал БЕЗ создания зависимости.

```tsx
import { createSignal, createEffect, untrack } from "solid-js";

const [a, setA] = createSignal(0);
const [b, setB] = createSignal(0);

createEffect(() => {
  // Подписываемся только на a, b читаем без подписки
  console.log(a(), untrack(b));
});

setA(1); // эффект сработает
setB(1); // эффект НЕ сработает
```

### Реальный пример: логирование с timestamp

```tsx
const [count, setCount] = createSignal(0);
const [logs, setLogs] = createSignal<string[]>([]);

createEffect(() => {
  const c = count();
  // Не хотим что бы эффект пересоздавался при изменении logs
  setLogs([...untrack(logs), `count = ${c} at ${Date.now()}`]);
});
```

**Когда полезно:** когда нужно прочитать значение для вычисления, но не хочешь подписываться на его изменения.

---

## 16. batch — батчинг обновлений

Группирует несколько обновлений сигналов в одно — эффекты сработают один раз.

```tsx
import { createSignal, createEffect, batch } from "solid-js";

const [first, setFirst] = createSignal("Jesus");
const [last, setLast] = createSignal("Yurchenko");

createEffect(() => {
  console.log(`${first()} ${last()}`);
});

// Без batch — эффект сработает 2 раза
setFirst("Ivan");
setLast("Petrov");

// С batch — эффект сработает 1 раз
batch(() => {
  setFirst("Ivan");
  setLast("Petrov");
});
```

### Когда полезно

- Обновление нескольких связанных сигналов
- В обработчиках формы где меняешь много полей сразу
- При синхронизации с сервером (новые данные → обновить много сигналов)

**Замечание:** SolidJS уже использует batch автоматически в event handlers — поэтому ручной batch нужен в основном в async коде:

```tsx
// В event handler — batch не нужен (он автоматический)
<button onClick={() => {
  setFirst("Ivan");
  setLast("Petrov");
  // оба setX сработают, но эффект запустится один раз
}}>

// В async — нужен явный batch
const handleAsync = async () => {
  const data = await fetchData();
  batch(() => {
    setFirst(data.first);
    setLast(data.last);
  });
};
```

---

## 17. on() — явные зависимости

Хелпер `on` создаёт эффект с явным указанием зависимостей.

```tsx
import { createEffect, on } from "solid-js";

const [a, setA] = createSignal(0);
const [b, setB] = createSignal(0);

// Без on — отслеживает все сигналы внутри
createEffect(() => {
  console.log(a(), b());
});

// С on — только указанные
createEffect(on(a, (current, prev) => {
  console.log(`a изменилось с ${prev} на ${current}`);
}));

// Несколько зависимостей
createEffect(on([a, b], ([currentA, currentB]) => {
  console.log(currentA, currentB);
}));

// defer — не запускать при инициализации
createEffect(on(a, (current) => {
  console.log("a изменилось:", current);
}, { defer: true }));
```

### Когда использовать on()

- Когда нужен `defer: true` (не запускать при инициализации)
- Когда нужен предыдущее значение в удобном виде
- Для явного декларирования зависимостей (читаемее в сложных случаях)

В большинстве случаев обычный `createEffect` достаточно.

---

## 18. 🛠 Практика: автокомплит с дебаунсом

Соберём всё что прошли в одном живом примере — автокомплит для поиска городов. Использует:
- `createSignal` — для текста поиска и результатов
- `createMemo` — для производных значений
- `createEffect` — для запросов
- `createDeferred` — для отложенной обработки
- `onCleanup` — для отмены запросов
- `untrack` — для логики без подписок

```tsx
import {
  Component,
  createSignal,
  createMemo,
  createEffect,
  createDeferred,
  onCleanup,
  Show,
  For,
} from "solid-js";

interface City {
  id: number;
  name: string;
  country: string;
  population: number;
}

const CityAutocomplete: Component = () => {
  // Состояние поиска
  const [query, setQuery] = createSignal("");
  const [results, setResults] = createSignal<City[]>([]);
  const [isLoading, setIsLoading] = createSignal(false);
  const [error, setError] = createSignal<string | null>(null);
  const [selectedIndex, setSelectedIndex] = createSignal(-1);

  // Отложенный query — обновится через 300мс после остановки ввода
  const deferredQuery = createDeferred(query, { timeoutMs: 300 });

  // Производные значения через createMemo
  const trimmedQuery = createMemo(() => deferredQuery().trim());
  const shouldSearch = createMemo(() => trimmedQuery().length >= 2);
  const hasResults = createMemo(() => results().length > 0);

  // Эффект для загрузки данных
  createEffect(() => {
    if (!shouldSearch()) {
      setResults([]);
      return;
    }

    const q = trimmedQuery();
    const controller = new AbortController();
    setIsLoading(true);
    setError(null);

    // Имитация API — в реальности здесь fetch к серверу
    fetch(`https://api.example.com/cities?q=${encodeURIComponent(q)}`, {
      signal: controller.signal,
    })
      .then((r) => {
        if (!r.ok) throw new Error(`HTTP ${r.status}`);
        return r.json();
      })
      .then((data: City[]) => {
        setResults(data);
        setSelectedIndex(-1);
      })
      .catch((err) => {
        if (err.name !== "AbortError") {
          setError(err.message);
          setResults([]);
        }
      })
      .finally(() => setIsLoading(false));

    // Очистка — отмена запроса если query изменится
    onCleanup(() => controller.abort());
  });

  // Навигация по клавиатуре
  const handleKeyDown = (e: KeyboardEvent) => {
    if (!hasResults()) return;

    if (e.key === "ArrowDown") {
      e.preventDefault();
      setSelectedIndex((i) => Math.min(i + 1, results().length - 1));
    } else if (e.key === "ArrowUp") {
      e.preventDefault();
      setSelectedIndex((i) => Math.max(i - 1, 0));
    } else if (e.key === "Enter") {
      e.preventDefault();
      const city = results()[selectedIndex()];
      if (city) selectCity(city);
    } else if (e.key === "Escape") {
      setResults([]);
    }
  };

  const selectCity = (city: City) => {
    setQuery(city.name);
    setResults([]);
    console.log("Выбран город:", city);
  };

  // Подсветка совпадающей части
  const highlight = (text: string) => {
    const q = trimmedQuery().toLowerCase();
    const idx = text.toLowerCase().indexOf(q);
    if (idx === -1) return text;
    return (
      <>
        {text.slice(0, idx)}
        <strong class="text-blue-600">{text.slice(idx, idx + q.length)}</strong>
        {text.slice(idx + q.length)}
      </>
    );
  };

  return (
    <div class="max-w-md mx-auto p-4">
      <div class="relative">
        <input
          type="text"
          value={query()}
          onInput={(e) => setQuery(e.currentTarget.value)}
          onKeyDown={handleKeyDown}
          placeholder="Начни вводить город..."
          class="w-full border rounded px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
        />

        <Show when={isLoading()}>
          <div class="absolute right-3 top-2.5">
            <div class="w-5 h-5 border-2 border-blue-500 border-t-transparent rounded-full animate-spin" />
          </div>
        </Show>
      </div>

      <Show when={error()}>
        <p class="text-red-500 mt-2">Ошибка: {error()}</p>
      </Show>

      <Show when={hasResults()}>
        <ul class="mt-2 border rounded shadow-lg bg-white">
          <For each={results()}>
            {(city, index) => (
              <li
                onMouseEnter={() => setSelectedIndex(index())}
                onClick={() => selectCity(city)}
                class={`px-4 py-2 cursor-pointer ${
                  selectedIndex() === index() ? "bg-blue-100" : "hover:bg-gray-50"
                }`}
              >
                <div>{highlight(city.name)}, {city.country}</div>
                <div class="text-sm text-gray-500">
                  Население: {city.population.toLocaleString()}
                </div>
              </li>
            )}
          </For>
        </ul>
      </Show>

      <Show
        when={shouldSearch() && !isLoading() && !hasResults() && !error()}
      >
        <p class="text-gray-500 mt-2">Ничего не найдено</p>
      </Show>
    </div>
  );
};

export default CityAutocomplete;
```

### Что здесь происходит

1. **Пользователь печатает** → `query` обновляется мгновенно (UI отзывчив)
2. **`deferredQuery`** ждёт 300мс простоя → обновляется
3. **`shouldSearch` мемо** проверяет длину — фильтр против пустых запросов
4. **`createEffect`** запускается на каждое изменение `deferredQuery` → отправляет fetch
5. **`onCleanup`** отменяет предыдущий запрос если query изменился (нет гонки данных)
6. **Навигация по клавиатуре** работает через `selectedIndex` сигнал
7. **Подсветка совпадения** — функция `highlight` использует `trimmedQuery()` реактивно

### Что важно понять

- **Реактивный граф здесь автоматически собирается** — мы не указываем "что от чего зависит" руками
- **`createDeferred` + `createEffect`** — пара которая решает классическую задачу debounce
- **`onCleanup` внутри эффекта** — очистка перед следующим запуском, а не только при размонтировании
- **Отдельные сигналы для query и deferredQuery** — UI и API живут с разной скоростью

В разделе про формы (Часть XI) этот пример углубим — добавим валидацию и работу с серверными ошибками.

---
---
---

# Часть IV — Компоненты

## 19. Основы компонентов

Компонент в SolidJS — это **функция** которая возвращает JSX.

```tsx
import { Component } from "solid-js";

const Hello: Component = () => {
  return <h1>Привет!</h1>;
};

export default Hello;
```

### Главное правило

Компонент запускается **только один раз** — при монтировании.

```tsx
const Counter: Component = () => {
  console.log("Setup");  // выведется ОДИН раз

  const [count, setCount] = createSignal(0);

  return <button onClick={() => setCount(count() + 1)}>{count()}</button>;
};
```

### Что это значит на практике

1. **Создание объектов в компоненте безопасно** — они создаются один раз
2. **useMemo / useCallback не нужны** — нечего мемоизировать
3. **Деструктуризация props ломает реактивность** — см. раздел 20
4. **Логика в JSX выполняется при каждом обновлении JSX** — но не функции компонента

### Именование компонентов

- **Всегда с большой буквы** — `<Button />`, `<UserCard />`
- С маленькой буквы JSX считает HTML-элементом: `<button />`

### Возврат JSX

Компонент должен возвращать одно из:
- Один JSX-элемент: `<div>...</div>`
- Массив элементов: `[<a />, <b />]`
- Фрагмент: `<>...</>`
- Строку: `"Hello"`
- Число: `42`
- `null` — ничего не рендерится

```tsx
// Один элемент
const A: Component = () => <div>A</div>;

// Фрагмент — несколько без обёртки
const B: Component = () => (
  <>
    <h1>Заголовок</h1>
    <p>Параграф</p>
  </>
);

// Массив
const C: Component = () => [<div>1</div>, <div>2</div>];

// Условный рендер
const D: Component = () => {
  if (!showAnything()) return null;
  return <div>Hello</div>;
};
```

### Композиция

Компоненты можно вкладывать друг в друга:

```tsx
const Header: Component = () => <header><h1>CGHub</h1></header>;
const Footer: Component = () => <footer>© 2026</footer>;

const App: Component = () => {
  return (
    <div>
      <Header />
      <main>Контент</main>
      <Footer />
    </div>
  );
};
```

---

## 20. Пропсы

Props — данные передаваемые от родителя к ребёнку.

### Базовое использование

```tsx
interface ButtonProps {
  label: string;
  onClick: () => void;
}

const Button: Component<ButtonProps> = (props) => {
  return (
    <button onClick={props.onClick}>
      {props.label}
    </button>
  );
};

// Использование
<Button label="Сохранить" onClick={() => save()} />
```

### Опциональные props

```tsx
interface ButtonProps {
  label: string;
  variant?: "primary" | "secondary";
  disabled?: boolean;
}

const Button: Component<ButtonProps> = (props) => {
  return (
    <button
      class={props.variant === "primary" ? "bg-blue-500" : "bg-gray-200"}
      disabled={props.disabled}
    >
      {props.label}
    </button>
  );
};
```

### КРИТИЧЕСКОЕ ПРАВИЛО: не деструктурируй props!

Это самая частая ошибка новичков в SolidJS:

```tsx
// ❌ НЕПРАВИЛЬНО — реактивность теряется
const Button: Component<ButtonProps> = ({ label, onClick }) => {
  return <button onClick={onClick}>{label}</button>;
};

// ✅ ПРАВИЛЬНО — всегда через props.xxx
const Button: Component<ButtonProps> = (props) => {
  return <button onClick={props.onClick}>{props.label}</button>;
};
```

### Почему деструктуризация ломает реактивность

`props` в SolidJS — это **прокси-объект**. Когда читаешь `props.label` — это вызов геттера, который создаёт подписку. Деструктуризация вызывает геттер один раз при монтировании и фиксирует значение навсегда.

```tsx
// Что происходит при деструктуризации
const { label } = props;
// label = props.label  ← вызвано ОДИН раз, навсегда зафиксировано

// Правильно
props.label  // вызывается КАЖДЫЙ раз когда JSX обновляется, реактивно
```

Это поведение — следствие того что компонент запускается один раз. Подробно об этом в части про анти-паттерны (раздел 116).

### Дефолтные значения props

Поскольку нельзя деструктурировать с `=`, используй `mergeProps`:

```tsx
import { mergeProps } from "solid-js";

interface ButtonProps {
  label: string;
  variant?: "primary" | "secondary";
}

const Button: Component<ButtonProps> = (rawProps) => {
  const props = mergeProps({ variant: "primary" as const }, rawProps);
  // теперь props.variant всегда определён
  
  return <button class={props.variant === "primary" ? "..." : "..."}>{props.label}</button>;
};
```

### Передача children

```tsx
interface CardProps {
  title: string;
  children: JSX.Element;
}

const Card: Component<CardProps> = (props) => {
  return (
    <div class="border rounded p-4">
      <h2>{props.title}</h2>
      <div>{props.children}</div>
    </div>
  );
};

<Card title="Моя карточка">
  <p>Содержимое карточки</p>
  <button>Кнопка</button>
</Card>
```

### Spread пропсов

Передать все props дальше:

```tsx
const Button: Component<any> = (props) => {
  return <button {...props} />;
};
```

Полезно для wrapper компонентов (см. раздел 21).

### Колбэки (передача функций вверх)

```tsx
interface InputProps {
  value: string;
  onChange: (newValue: string) => void;
}

const Input: Component<InputProps> = (props) => {
  return (
    <input
      value={props.value}
      onInput={(e) => props.onChange(e.currentTarget.value)}
    />
  );
};

// Использование
const [value, setValue] = createSignal("");
<Input value={value()} onChange={setValue} />
```

---

## 21. mergeProps и splitProps

### mergeProps — дефолтные значения

```tsx
import { mergeProps } from "solid-js";

interface ButtonProps {
  label?: string;
  variant?: "primary" | "secondary";
  disabled?: boolean;
}

const Button: Component<ButtonProps> = (rawProps) => {
  const props = mergeProps(
    { label: "Кнопка", variant: "primary" as const, disabled: false },
    rawProps
  );

  return (
    <button
      class={props.variant === "primary" ? "bg-blue-500" : "bg-gray-200"}
      disabled={props.disabled}
    >
      {props.label}
    </button>
  );
};
```

`mergeProps` сохраняет реактивность — если родитель меняет проп, компонент это увидит.

### splitProps — разделить props

Используется в wrapper компонентах когда нужно часть props обработать, остальные передать дальше:

```tsx
import { splitProps, JSX } from "solid-js";

interface CustomButtonProps extends JSX.ButtonHTMLAttributes<HTMLButtonElement> {
  variant?: "primary" | "secondary";
  loading?: boolean;
}

const CustomButton: Component<CustomButtonProps> = (props) => {
  const [local, others] = splitProps(props, ["variant", "loading", "class"]);

  return (
    <button
      class={`${local.variant === "primary" ? "bg-blue-500" : "bg-gray-200"} ${local.class ?? ""}`}
      disabled={local.loading}
      {...others} // все остальные props (onClick, type, etc.)
    >
      {local.loading ? "Загрузка..." : props.children}
    </button>
  );
};
```

### Комбинирование mergeProps + splitProps

```tsx
const Button: Component<CustomButtonProps> = (rawProps) => {
  const merged = mergeProps({ variant: "primary" as const }, rawProps);
  const [local, others] = splitProps(merged, ["variant", "class"]);

  return (
    <button class={`base-classes ${local.class ?? ""}`} {...others}>
      {merged.children}
    </button>
  );
};
```

### Реальный сценарий — Input компонент

```tsx
interface InputProps extends JSX.InputHTMLAttributes<HTMLInputElement> {
  label?: string;
  error?: string;
}

const Input: Component<InputProps> = (props) => {
  const [local, inputProps] = splitProps(props, ["label", "error", "class"]);

  return (
    <div class="flex flex-col gap-1">
      <Show when={local.label}>
        <label class="text-sm font-medium">{local.label}</label>
      </Show>
      <input
        {...inputProps}
        class={`border rounded px-3 py-2 ${local.error ? "border-red-500" : "border-gray-300"} ${local.class ?? ""}`}
      />
      <Show when={local.error}>
        <span class="text-sm text-red-500">{local.error}</span>
      </Show>
    </div>
  );
};

// Использование
<Input
  label="Email"
  type="email"
  placeholder="example@mail.com"
  value={email()}
  onInput={(e) => setEmail(e.currentTarget.value)}
  error={emailError()}
/>
```

---

## 22. children helper

Когда работаешь с `props.children` несколько раз — используй хелпер `children`:

```tsx
import { children, Component, JSX } from "solid-js";

interface WrapperProps {
  children: JSX.Element;
}

const Wrapper: Component<WrapperProps> = (props) => {
  const resolved = children(() => props.children);

  // Теперь можно использовать resolved() несколько раз
  return (
    <div>
      <div class="header">{resolved()}</div>
      <div class="content">{resolved()}</div>
    </div>
  );
};
```

### Зачем нужен

Без `children` helper повторное обращение к `props.children` может создавать новые элементы каждый раз. Хелпер кэширует результат и нормализует типы.

### Когда обязательно

- Children используются больше одного раза
- Нужно итерировать children как массив
- Нужно манипулировать children (добавлять props, оборачивать)

```tsx
const TabList: Component<{ children: JSX.Element }> = (props) => {
  const resolved = children(() => props.children);
  
  // Можно итерировать
  const items = () => resolved.toArray();
  
  return (
    <div>
      <For each={items()}>
        {(item, i) => (
          <div class={`tab tab-${i()}`}>{item}</div>
        )}
      </For>
    </div>
  );
};
```

---

## 23. Типы компонентов

SolidJS предоставляет несколько типов для компонентов.

### Component\<P\>

Базовый тип — для компонентов БЕЗ children:

```tsx
import { Component } from "solid-js";

interface ButtonProps {
  label: string;
  onClick: () => void;
}

const Button: Component<ButtonProps> = (props) => {
  return <button onClick={props.onClick}>{props.label}</button>;
};
```

Если попытаешься передать children — TS выдаст ошибку:

```tsx
<Button label="OK" onClick={...}>
  Текст {/* ❌ Ошибка типа */}
</Button>
```

### ParentComponent\<P\>

Для компонентов которые принимают children:

```tsx
import { ParentComponent } from "solid-js";

interface CardProps {
  title: string;
}

const Card: ParentComponent<CardProps> = (props) => {
  return (
    <div>
      <h2>{props.title}</h2>
      <div>{props.children}</div>
    </div>
  );
};

<Card title="Hello">
  <p>Контент</p>
</Card>
```

### VoidComponent\<P\>

Явно говорит "никаких children":

```tsx
import { VoidComponent } from "solid-js";

const Icon: VoidComponent<{ name: string }> = (props) => {
  return <i class={`icon-${props.name}`} />;
};
```

### FlowComponent\<P, C\>

Для компонентов которые принимают children как функцию (как `<For>`):

```tsx
import { FlowComponent } from "solid-js";

interface MyListProps<T> {
  items: T[];
}

const MyList: FlowComponent<MyListProps<any>, (item: any) => JSX.Element> = (props) => {
  return (
    <div>
      <For each={props.items}>
        {(item) => props.children(item)}
      </For>
    </div>
  );
};

<MyList items={users()}>
  {(user) => <UserCard user={user} />}
</MyList>
```

### ParentProps — utility тип

Альтернатива для функционального стиля:

```tsx
import { ParentProps } from "solid-js";

function Card(props: ParentProps<{ title: string }>) {
  return (
    <div>
      <h2>{props.title}</h2>
      {props.children}
    </div>
  );
}
```

---

## 24. Refs

Ref — прямая ссылка на DOM элемент.

### Базовое использование

```tsx
import { Component, onMount } from "solid-js";

const FocusInput: Component = () => {
  let inputRef!: HTMLInputElement;

  onMount(() => {
    inputRef.focus();
  });

  return <input ref={inputRef} />;
};
```

Используем `!` (non-null assertion) потому что TS не знает что ref будет инициализирован до использования.

### Реактивный ref через callback

```tsx
const Component: Component = () => {
  const [width, setWidth] = createSignal(0);

  return (
    <div
      ref={(el) => {
        setWidth(el.offsetWidth);
      }}
    >
      Содержимое
    </div>
  );
};
```

### Forwarding refs (передача ref в дочерний компонент)

```tsx
interface InputProps {
  ref?: HTMLInputElement | ((el: HTMLInputElement) => void);
  placeholder?: string;
}

const CustomInput: Component<InputProps> = (props) => {
  return <input ref={props.ref} placeholder={props.placeholder} />;
};

// Использование
const App: Component = () => {
  let inputRef!: HTMLInputElement;
  
  onMount(() => inputRef.focus());
  
  return <CustomInput ref={inputRef} placeholder="Введи текст" />;
};
```

### Когда использовать refs

- Фокус на инпуте (`element.focus()`)
- Измерение размеров (`element.offsetWidth`)
- Интеграция с библиотеками которые работают с DOM напрямую (Three.js, Chart.js)
- Скролл к элементу (`element.scrollIntoView()`)
- Анимации через библиотеки (GSAP, Motion)

**Не используй refs** когда задачу можно решить через сигналы и условный рендер.

Подробнее о работе с DOM — в Части XII.

---

## 25. \<Dynamic\>

Рендерит компонент или HTML-тег динамически по значению.

```tsx
import { Dynamic } from "solid-js/web";
import { createSignal, Component } from "solid-js";

const RedDiv: Component = () => <div style="color: red">Red</div>;
const GreenDiv: Component = () => <div style="color: green">Green</div>;
const BlueDiv: Component = () => <div style="color: blue">Blue</div>;

const App: Component = () => {
  const [color, setColor] = createSignal<"red" | "green" | "blue">("red");

  const components = {
    red: RedDiv,
    green: GreenDiv,
    blue: BlueDiv,
  };

  return (
    <>
      <Dynamic component={components[color()]} />
      <select onChange={(e) => setColor(e.currentTarget.value as any)}>
        <option value="red">Red</option>
        <option value="green">Green</option>
        <option value="blue">Blue</option>
      </select>
    </>
  );
};
```

### С HTML тегом

```tsx
const [tag, setTag] = createSignal<"h1" | "h2" | "h3">("h1");

<Dynamic component={tag()}>Заголовок</Dynamic>
// Рендерит <h1>Заголовок</h1>, <h2>...</h2>, или <h3>...</h3>
```

### С пропсами

```tsx
<Dynamic
  component={selectedComponent()}
  title="Заголовок"
  onClick={handleClick}
/>
```

### Когда использовать

Альтернатива большому `<Switch>` или цепочке тернарных операторов:

```tsx
// Вместо этого
<Switch>
  <Match when={type() === "user"}><UserCard /></Match>
  <Match when={type() === "post"}><PostCard /></Match>
  <Match when={type() === "comment"}><CommentCard /></Match>
</Switch>

// Можно так
const components = { user: UserCard, post: PostCard, comment: CommentCard };
<Dynamic component={components[type()]} />
```

---

## 26. \<Portal\>

Рендерит контент в другое место DOM. Полезно для модалок, тултипов, нотификаций.

```tsx
import { Portal } from "solid-js/web";

const Modal: Component<{ open: boolean; onClose: () => void }> = (props) => {
  return (
    <Show when={props.open}>
      <Portal>
        <div class="fixed inset-0 bg-black/50 flex items-center justify-center">
          <div class="bg-white p-6 rounded">
            <h2>Модальное окно</h2>
            <button onClick={props.onClose}>Закрыть</button>
          </div>
        </div>
      </Portal>
    </Show>
  );
};
```

По умолчанию `<Portal>` рендерит в конец `document.body`. Можно указать `mount`:

```tsx
<Portal mount={document.getElementById("modal-root")!}>
  <div>Контент</div>
</Portal>
```

### Зачем нужен Portal

Решает проблему `overflow: hidden` и `z-index`. Модалка вложенная в компонент с `overflow: hidden` обрезалась бы. Portal вырывает её из дерева и рендерит на верхнем уровне.

---

## 27. lazy() — code splitting

Ленивая загрузка компонентов — компонент скачивается только когда нужен.

```tsx
import { lazy, Suspense } from "solid-js";

// Не загружается сразу при старте приложения
const HeavyComponent = lazy(() => import("./HeavyComponent"));

const App: Component = () => {
  return (
    <div>
      <Suspense fallback={<p>Загрузка...</p>}>
        <HeavyComponent />
      </Suspense>
    </div>
  );
};
```

### Использование с роутингом

```tsx
import { Router, Route } from "@solidjs/router";
import { lazy } from "solid-js";

const Home = lazy(() => import("./pages/Home"));
const About = lazy(() => import("./pages/About"));
const Profile = lazy(() => import("./pages/Profile"));

const App = () => (
  <Router>
    <Route path="/" component={Home} />
    <Route path="/about" component={About} />
    <Route path="/profile" component={Profile} />
  </Router>
);
```

Каждая страница загрузится только когда пользователь на неё перейдёт. Стартовый бандл становится меньше.

### Preload

Можно прелоадить компонент заранее:

```tsx
const HeavyComponent = lazy(() => import("./HeavyComponent"));

// Прелоад при наведении на ссылку
<a onMouseEnter={() => HeavyComponent.preload()}>Открыть</a>
```

---

## 28. 🛠 Практика: переиспользуемый Modal с фокус-ловушкой

Соберём production-grade модалку. Покрывает много нюансов: refs, портал, события клавиатуры, фокус-менеджмент.

```tsx
import {
  Component,
  ParentProps,
  Show,
  createEffect,
  onCleanup,
  onMount,
} from "solid-js";
import { Portal } from "solid-js/web";

interface ModalProps extends ParentProps {
  open: boolean;
  onClose: () => void;
  title?: string;
  closeOnEscape?: boolean;
  closeOnBackdrop?: boolean;
  size?: "sm" | "md" | "lg" | "xl";
}

const Modal: Component<ModalProps> = (props) => {
  let dialogRef!: HTMLDivElement;
  let previousFocus: HTMLElement | null = null;

  // Закрытие по Escape
  createEffect(() => {
    if (!props.open) return;
    if (props.closeOnEscape === false) return;

    const handler = (e: KeyboardEvent) => {
      if (e.key === "Escape") props.onClose();
    };

    document.addEventListener("keydown", handler);
    onCleanup(() => document.removeEventListener("keydown", handler));
  });

  // Блокировка скролла body когда модалка открыта
  createEffect(() => {
    if (props.open) {
      const originalOverflow = document.body.style.overflow;
      document.body.style.overflow = "hidden";
      onCleanup(() => {
        document.body.style.overflow = originalOverflow;
      });
    }
  });

  // Управление фокусом
  createEffect(() => {
    if (props.open) {
      // Запоминаем где был фокус
      previousFocus = document.activeElement as HTMLElement;

      // Переносим фокус внутрь модалки
      queueMicrotask(() => {
        const firstFocusable = dialogRef?.querySelector<HTMLElement>(
          "button, [href], input, select, textarea, [tabindex]:not([tabindex='-1'])"
        );
        firstFocusable?.focus();
      });

      onCleanup(() => {
        // Возвращаем фокус когда закрываем
        previousFocus?.focus();
      });
    }
  });

  // Trap фокуса — Tab не должен уходить за пределы модалки
  const handleKeyDown = (e: KeyboardEvent) => {
    if (e.key !== "Tab" || !dialogRef) return;

    const focusable = dialogRef.querySelectorAll<HTMLElement>(
      "button, [href], input, select, textarea, [tabindex]:not([tabindex='-1'])"
    );
    if (focusable.length === 0) return;

    const first = focusable[0];
    const last = focusable[focusable.length - 1];

    if (e.shiftKey && document.activeElement === first) {
      e.preventDefault();
      last.focus();
    } else if (!e.shiftKey && document.activeElement === last) {
      e.preventDefault();
      first.focus();
    }
  };

  // Размеры
  const sizeClass = () => {
    switch (props.size ?? "md") {
      case "sm": return "max-w-sm";
      case "md": return "max-w-md";
      case "lg": return "max-w-lg";
      case "xl": return "max-w-xl";
    }
  };

  return (
    <Show when={props.open}>
      <Portal>
        <div
          class="fixed inset-0 z-50 flex items-center justify-center bg-black/50 backdrop-blur-sm"
          onClick={(e) => {
            // Закрытие по клику на фон
            if (e.target === e.currentTarget && props.closeOnBackdrop !== false) {
              props.onClose();
            }
          }}
        >
          <div
            ref={dialogRef}
            role="dialog"
            aria-modal="true"
            aria-labelledby={props.title ? "modal-title" : undefined}
            onKeyDown={handleKeyDown}
            class={`bg-white rounded-lg shadow-xl ${sizeClass()} w-full mx-4 max-h-[90vh] overflow-auto`}
          >
            <Show when={props.title}>
              <div class="flex items-center justify-between p-4 border-b">
                <h2 id="modal-title" class="text-lg font-semibold">
                  {props.title}
                </h2>
                <button
                  onClick={props.onClose}
                  aria-label="Закрыть"
                  class="text-gray-400 hover:text-gray-600 text-2xl leading-none"
                >
                  ×
                </button>
              </div>
            </Show>
            <div class="p-4">{props.children}</div>
          </div>
        </div>
      </Portal>
    </Show>
  );
};

export default Modal;
```

### Использование

```tsx
import { Component, createSignal } from "solid-js";
import Modal from "./Modal";

const App: Component = () => {
  const [isOpen, setIsOpen] = createSignal(false);

  return (
    <div class="p-8">
      <button
        onClick={() => setIsOpen(true)}
        class="bg-blue-500 text-white px-4 py-2 rounded"
      >
        Открыть модалку
      </button>

      <Modal
        open={isOpen()}
        onClose={() => setIsOpen(false)}
        title="Подтверждение"
        size="md"
      >
        <p class="mb-4">Вы уверены что хотите удалить этот элемент?</p>
        <div class="flex gap-2 justify-end">
          <button
            onClick={() => setIsOpen(false)}
            class="px-4 py-2 border rounded"
          >
            Отмена
          </button>
          <button
            onClick={() => {
              console.log("Удалено");
              setIsOpen(false);
            }}
            class="px-4 py-2 bg-red-500 text-white rounded"
          >
            Удалить
          </button>
        </div>
      </Modal>
    </div>
  );
};
```

### Что важно понять

1. **Portal** — модалка живёт в `document.body`, не зависит от `overflow: hidden` родителей
2. **Несколько `createEffect`** — каждый отвечает за свой аспект (Escape, scroll lock, focus). Чище чем один большой
3. **`onCleanup` внутри эффекта** — отписки и восстановление состояния происходят автоматически
4. **`queueMicrotask`** — переносит фокус после того как DOM отрендерится
5. **Focus trap** — пользователь не может Tab-нуть за пределы модалки. Это требование accessibility
6. **aria-* атрибуты** — модалка работает со screen readers

В production вместо самописной модалки чаще берут готовую из Kobalte (раздел 113) — там это всё уже есть. Но понимать как это устроено — важно.

---
---

# Часть V — Управление потоком

## 29. \<Show\>

Условный рендер. Замена тернарного оператора.

### Базовое использование

```tsx
import { Show } from "solid-js";

<Show when={isLoggedIn()}>
  <p>Добро пожаловать!</p>
</Show>
```

### С fallback

```tsx
<Show when={items().length > 0} fallback={<p>Список пуст</p>}>
  <ul>
    <For each={items()}>{(item) => <li>{item}</li>}</For>
  </ul>
</Show>
```

### С деструктурированным значением

`when` может возвращать значение — оно передаётся в children как функция:

```tsx
<Show when={user()} fallback={<p>Не авторизован</p>}>
  {(user) => <p>Привет, {user().name}!</p>}
</Show>
```

Это полезно когда нужно сузить тип. Внутри `<Show>` TS знает что `user` не null.

### Сигнатура

```ts
interface ShowProps<T> {
  when: T | undefined | null | false;
  fallback?: JSX.Element;
  keyed?: boolean;
  children: JSX.Element | ((item: Accessor<T>) => JSX.Element);
}
```

### keyed prop

По умолчанию `<Show>` не пересоздаёт children при изменении `when` (если оно остаётся truthy). С `keyed` — пересоздаёт при каждом изменении значения.

```tsx
<Show when={user()} keyed>
  {(user) => <UserProfile user={user} />}
  {/* пересоздаётся при каждом изменении user */}
</Show>
```

---

## 30. \<For\> vs \<Index\>

Два компонента для рендера списков. Используй правильный.

### \<For\> — для большинства случаев

`<For>` использует **значение** как ключ. Идеально для динамических списков где элементы добавляются, удаляются, перемешиваются.

```tsx
import { For } from "solid-js";

<For each={items()}>
  {(item, index) => (
    <li>
      {index() + 1}. {item.name}
    </li>
  )}
</For>
```

`index` — функция (Accessor), вызывай со скобками: `index()`.

### \<Index\> — для статичных списков

`<Index>` использует **индекс** как ключ. Подходит когда меняются ТОЛЬКО значения, а структура списка стабильна.

```tsx
import { Index } from "solid-js";

<Index each={items()}>
  {(item, index) => (
    <li>
      {index + 1}. {item().name}
    </li>
  )}
</Index>
```

Заметь — `item` теперь функция (Accessor), а `index` — обычное число.

### Когда что использовать

| Сценарий | Использовать |
|---|---|
| Динамический список (todo, чат) | `<For>` |
| Перестановка элементов | `<For>` |
| Список примитивов (числа, строки) | `<Index>` |
| Фиксированное количество слотов | `<Index>` |
| Грид с одинаковыми ячейками | `<Index>` |

### Сравнение поведения

```tsx
const [items, setItems] = createSignal([1, 2, 3]);

// <For>
<For each={items()}>
  {(item) => <div>{item}</div>}
</For>

// Если переставить элементы [3, 1, 2]:
// — DOM узлы переиспользуются, переставляются местами
// — Это эффективно для сложных DOM поддеревьев

// <Index>
<Index each={items()}>
  {(item) => <div>{item()}</div>}
</Index>

// Если переставить элементы [3, 1, 2]:
// — DOM узлы остаются на месте
// — Меняются только их содержимое
```

### Визуализация — что происходит с DOM

При перестановке `[1,2,3]` → `[3,1,2]`:

```
                  ┌──────── <For> ────────┐    ┌─────── <Index> ───────┐
                  │ (key = value)          │    │ (key = position)       │
                  ├────────────────────────┤    ├────────────────────────┤
  До:    pos 0 →  │ DOM_A (text=1)         │    │ DOM_A (text=1)         │
         pos 1 →  │ DOM_B (text=2)         │    │ DOM_B (text=2)         │
         pos 2 →  │ DOM_C (text=3)         │    │ DOM_C (text=3)         │
                  └────────────────────────┘    └────────────────────────┘
                              │                              │
                  setItems([3,1,2])              setItems([3,1,2])
                              │                              │
                              ▼                              ▼
                  ┌────────────────────────┐    ┌────────────────────────┐
  После: pos 0 →  │ DOM_C (text=3) ← moved │    │ DOM_A (text=3) ← updated│
         pos 1 →  │ DOM_A (text=1) ← moved │    │ DOM_B (text=1) ← updated│
         pos 2 →  │ DOM_B (text=2) ← moved │    │ DOM_C (text=2) ← updated│
                  └────────────────────────┘    └────────────────────────┘

           Те же DOM узлы, переставлены        Те же DOM узлы, обновили текст
```

**Когда это критично:**
- `<For>` для динамических списков с дорогим children (формы, видео, сложные UI) — DOM узлы и их состояние (фокус, скролл, локальный state) сохраняются при перестановке
- `<Index>` для статичных позиций с примитивными значениями — дешевле потому что не двигает DOM

Подробно про разницу в производительности — раздел 120 (анти-паттерны).

---

## 31. \<Switch\> / \<Match\>

Замена цепочки if/else или switch/case.

### Базовое использование

```tsx
import { Switch, Match } from "solid-js";

<Switch fallback={<p>Неизвестный статус</p>}>
  <Match when={status() === "loading"}>
    <Spinner />
  </Match>
  <Match when={status() === "error"}>
    <ErrorMessage />
  </Match>
  <Match when={status() === "success"}>
    <Content />
  </Match>
</Switch>
```

Рендерится **первый** `<Match>` чьё условие истинно. Если ни одно — рендерится `fallback`.

### С деструктурированным значением

```tsx
<Switch>
  <Match when={user()}>
    {(user) => <p>Привет, {user().name}!</p>}
  </Match>
  <Match when={loading()}>
    <Spinner />
  </Match>
</Switch>
```

### Когда использовать

- Больше двух условий → `<Switch>` вместо вложенных `<Show>`
- Взаимоисключающие состояния (loading / error / success)

---

## 32. \<ErrorBoundary\>

Перехватывает ошибки в дочерних компонентах. Без него ошибка в одном компоненте крашит всё приложение.

```tsx
import { ErrorBoundary } from "solid-js";

<ErrorBoundary
  fallback={(err, reset) => (
    <div>
      <p>Что-то пошло не так:</p>
      <pre>{err.message}</pre>
      <button onClick={reset}>Попробовать снова</button>
    </div>
  )}
>
  <RiskyComponent />
</ErrorBoundary>
```

### Вложенные ErrorBoundary

Можно вложить несколько — каждый ловит ошибки в своём поддереве:

```tsx
<ErrorBoundary fallback={<p>Глобальная ошибка</p>}>
  <Header />
  
  <ErrorBoundary fallback={<p>Ошибка в основном контенте</p>}>
    <MainContent />
  </ErrorBoundary>
  
  <Footer />
</ErrorBoundary>
```

### С createResource

ErrorBoundary ловит ошибки из `createResource`:

```tsx
const [data] = createResource(fetchData);

<ErrorBoundary fallback={(err) => <p>Ошибка: {err.message}</p>}>
  <Suspense fallback={<p>Загрузка...</p>}>
    <div>{data()?.name}</div>
  </Suspense>
</ErrorBoundary>
```

---

## 33. 🛠 Практика: дискриминированные состояния UI

Распространённая ошибка — представлять состояние UI как несколько независимых булевых сигналов (`isLoading`, `hasError`, `data`). Это позволяет невалидные комбинации (`isLoading=true, hasError=true`). Лучший паттерн — **дискриминированный union**.

```tsx
import { Component, createSignal, Match, Switch, Show, For } from "solid-js";

interface User {
  id: number;
  name: string;
  email: string;
}

// Состояние через дискриминированный union
type UserListState =
  | { status: "idle" }
  | { status: "loading"; progress?: number }
  | { status: "success"; users: User[]; lastFetch: Date }
  | { status: "error"; message: string; canRetry: boolean }
  | { status: "empty"; reason: "no-data" | "no-permissions" };

const UserListWithStates: Component = () => {
  const [state, setState] = createSignal<UserListState>({ status: "idle" });

  const loadUsers = async () => {
    setState({ status: "loading", progress: 0 });

    try {
      // Имитация прогресса
      const totalSteps = 5;
      for (let i = 1; i <= totalSteps; i++) {
        await new Promise((r) => setTimeout(r, 200));
        setState({ status: "loading", progress: (i / totalSteps) * 100 });
      }

      const response = await fetch("https://jsonplaceholder.typicode.com/users");
      if (!response.ok) {
        throw new Error(`HTTP ${response.status}`);
      }
      const users: User[] = await response.json();

      if (users.length === 0) {
        setState({ status: "empty", reason: "no-data" });
      } else {
        setState({ status: "success", users, lastFetch: new Date() });
      }
    } catch (err) {
      setState({
        status: "error",
        message: (err as Error).message,
        canRetry: true,
      });
    }
  };

  return (
    <div class="max-w-2xl mx-auto p-4">
      <div class="flex items-center justify-between mb-4">
        <h2 class="text-xl font-bold">Пользователи</h2>
        <button
          onClick={loadUsers}
          disabled={state().status === "loading"}
          class="bg-blue-500 text-white px-4 py-2 rounded disabled:opacity-50"
        >
          Загрузить
        </button>
      </div>

      <Switch>
        {/* idle */}
        <Match when={state().status === "idle"}>
          <div class="text-center text-gray-500 py-8">
            Нажми "Загрузить" чтобы получить список
          </div>
        </Match>

        {/* loading */}
        <Match when={state().status === "loading"}>
          {(_) => {
            const s = state();
            if (s.status !== "loading") return null;
            return (
              <div class="text-center py-8">
                <div class="w-12 h-12 mx-auto border-4 border-blue-500 border-t-transparent rounded-full animate-spin" />
                <Show when={s.progress !== undefined}>
                  <div class="mt-4">
                    <div class="w-full bg-gray-200 rounded h-2">
                      <div
                        class="bg-blue-500 h-2 rounded transition-all"
                        style={{ width: `${s.progress}%` }}
                      />
                    </div>
                    <p class="text-sm text-gray-600 mt-2">
                      Загружено {Math.round(s.progress ?? 0)}%
                    </p>
                  </div>
                </Show>
              </div>
            );
          }}
        </Match>

        {/* error */}
        <Match when={state().status === "error"}>
          {(_) => {
            const s = state();
            if (s.status !== "error") return null;
            return (
              <div class="bg-red-50 border border-red-200 rounded p-4">
                <h3 class="font-semibold text-red-700">Ошибка загрузки</h3>
                <p class="text-red-600 mt-1">{s.message}</p>
                <Show when={s.canRetry}>
                  <button
                    onClick={loadUsers}
                    class="mt-3 text-red-700 underline"
                  >
                    Попробовать снова
                  </button>
                </Show>
              </div>
            );
          }}
        </Match>

        {/* empty */}
        <Match when={state().status === "empty"}>
          {(_) => {
            const s = state();
            if (s.status !== "empty") return null;
            return (
              <div class="text-center py-8">
                <p class="text-gray-500">
                  {s.reason === "no-data"
                    ? "Список пуст"
                    : "Нет прав доступа"}
                </p>
              </div>
            );
          }}
        </Match>

        {/* success */}
        <Match when={state().status === "success"}>
          {(_) => {
            const s = state();
            if (s.status !== "success") return null;
            return (
              <>
                <p class="text-sm text-gray-500 mb-2">
                  Обновлено: {s.lastFetch.toLocaleTimeString()}
                </p>
                <ul class="divide-y border rounded">
                  <For each={s.users}>
                    {(user) => (
                      <li class="p-3 hover:bg-gray-50">
                        <div class="font-medium">{user.name}</div>
                        <div class="text-sm text-gray-500">{user.email}</div>
                      </li>
                    )}
                  </For>
                </ul>
              </>
            );
          }}
        </Match>
      </Switch>
    </div>
  );
};

export default UserListWithStates;
```

### Что здесь важно

1. **Невозможные состояния невозможны** — TypeScript не даст представить `loading + error` одновременно
2. **`Switch/Match` идеально подходит** — каждый вариант обрабатывается отдельно
3. **Сужение типа внутри ветки** — после проверки `state().status === "success"` TS знает что есть `users` и `lastFetch`
4. **Гранулярные данные в каждом состоянии** — `loading` несёт `progress`, `error` несёт `message` и `canRetry`
5. **Альтернатива boolean флагам** — никаких `[isLoading, hasError, data, errorMessage]` россыпью

Этот паттерн масштабируется на любую сложность UI состояний. Подробнее про дискриминированные unions — раздел 70.

---
---

# Часть VI — Lifecycle

## 34. onMount / onCleanup

### onMount — один раз при монтировании

Запускается **после** того как компонент смонтирован в DOM.

```tsx
import { onMount } from "solid-js";

const Component: Component = () => {
  onMount(() => {
    console.log("Компонент смонтирован");
    // DOM доступен, refs инициализированы
  });

  return <div>...</div>;
};
```

### Типичные сценарии onMount

**1. Загрузка данных (если не используешь createResource)**

```tsx
const [data, setData] = createSignal<Data | null>(null);

onMount(async () => {
  const result = await fetch("/api/data").then((r) => r.json());
  setData(result);
});
```

**2. Установка фокуса**

```tsx
let inputRef!: HTMLInputElement;

onMount(() => {
  inputRef.focus();
});

return <input ref={inputRef} />;
```

**3. Подписка на события**

```tsx
onMount(() => {
  window.addEventListener("resize", handleResize);
});
```

**4. Интеграция с библиотеками**

```tsx
let canvasRef!: HTMLCanvasElement;

onMount(() => {
  const chart = new Chart(canvasRef, chartConfig);
});
```

### onCleanup — при размонтировании или перед перезапуском

Запускается при удалении компонента из DOM или перед следующим запуском эффекта.

```tsx
import { onCleanup } from "solid-js";

onMount(() => {
  const handleResize = () => console.log("resize");
  window.addEventListener("resize", handleResize);
  
  onCleanup(() => {
    window.removeEventListener("resize", handleResize);
  });
});
```

### onCleanup внутри createEffect

Очень частый паттерн:

```tsx
createEffect(() => {
  const id = userId();
  const ws = new WebSocket(`wss://api.example.com/user/${id}`);
  
  onCleanup(() => {
    ws.close();
  });
});
// При изменении userId — сначала onCleanup закроет старый WebSocket,
// потом создастся новый
```

### Когда обязательно onCleanup

- `setInterval` / `setTimeout` — `clearInterval` / `clearTimeout`
- `addEventListener` — `removeEventListener`
- WebSocket, EventSource — `.close()`
- Подписки на observables, signals из библиотек
- Все ресурсы которые нужно явно освобождать

Без `onCleanup` — утечки памяти и баги. Подробнее об этой ошибке — раздел 122.

---

## 35. onError

Перехват ошибок в реактивных вычислениях:

```tsx
import { onError } from "solid-js";

const Component: Component = () => {
  onError((error) => {
    console.error("Поймана ошибка в реактивности:", error);
    // отправить в Sentry, показать toast, etc.
  });

  return <div>...</div>;
};
```

Для большинства задач используй `<ErrorBoundary>`. `onError` — для специальных случаев когда нужен глобальный обработчик.

---
---
---

# Часть VII — Stores

## 36. createStore

Store — для сложного состояния: объекты, массивы с вложенными данными. Альтернатива `createSignal` для не-примитивов.

### Базовое использование

```tsx
import { createStore } from "solid-js/store";

interface AppState {
  user: {
    name: string;
    age: number;
  };
  todos: { id: number; text: string; done: boolean }[];
}

const [store, setStore] = createStore<AppState>({
  user: { name: "Jesus", age: 25 },
  todos: [
    { id: 1, text: "Купить хлеб", done: false },
    { id: 2, text: "Сделать зарядку", done: true },
  ],
});

// Чтение — БЕЗ скобок (в отличие от signal!)
store.user.name      // "Jesus"
store.todos[0].text  // "Купить хлеб"
store.todos.length   // 2
```

### Чем отличается от createSignal с объектом

```tsx
// Signal с объектом — нужно ВСЕГДА создавать новый объект
const [user, setUser] = createSignal({ name: "Jesus", age: 25 });
setUser({ ...user(), age: 26 });

// Store — можно обновлять конкретные поля точечно
const [store, setStore] = createStore({ user: { name: "Jesus", age: 25 } });
setStore("user", "age", 26); // меняется только age, реактивность точечная
```

При обновлении поля в store обновляются только те места UI которые читают именно это поле. Signal с объектом обновлял бы всё.

### Когда использовать Signal vs Store

```
createSignal → примитивы (число, строка, булево) или простые объекты
createStore  → сложные структуры с вложенностью, массивы объектов
```

---

## 37. Обновление через путь

Главная особенность store — обновление через путь.

### Простое поле

```tsx
setStore("user", "name", "Ivan");
// store.user.name = "Ivan"
```

### Вложенное поле

```tsx
const [store, setStore] = createStore({
  settings: {
    theme: {
      primary: "blue",
    },
  },
});

setStore("settings", "theme", "primary", "red");
// store.settings.theme.primary = "red"
```

### Элемент массива по индексу

```tsx
setStore("todos", 0, "done", true);
// store.todos[0].done = true
```

### Элемент по условию

```tsx
// Изменить done у todo с id=1
setStore("todos", (t) => t.id === 1, "done", true);

// Несколько элементов
setStore("todos", (t) => t.done, "archived", true);
// все где done === true получат archived = true
```

### Обновление функцией

```tsx
// Получить текущее значение, вернуть новое
setStore("todos", 0, "done", (prev) => !prev);

// Обновить весь объект
setStore("user", (prev) => ({ ...prev, age: prev.age + 1 }));
```

### Все индексы массива

```tsx
// Изменить done у ВСЕХ todos
setStore("todos", {}, "done", false);
// {} означает "все элементы"
```

### Диапазон индексов

```tsx
setStore("todos", [0, 1, 2, 3, 4], "done", true);
```

### Замена массива целиком

```tsx
setStore("todos", [
  { id: 1, text: "Новая задача", done: false }
]);
```

### Добавление в массив

```tsx
// Через spread
setStore("todos", [...store.todos, newTodo]);

// Или через путь — добавление в конец
setStore("todos", store.todos.length, newTodo);
```

### Удаление из массива

```tsx
setStore("todos", store.todos.filter((t) => t.id !== 1));
```

### Объединение полей объекта

```tsx
setStore("user", { name: "Ivan", age: 26 });
// store.user.name = "Ivan", store.user.age = 26, остальные поля сохранены
```

---

## 38. produce — мутации

`produce` позволяет писать "мутирующий" код, который под капотом работает иммутабельно:

```tsx
import { produce } from "solid-js/store";

setStore(
  produce((s) => {
    s.user.name = "Ivan";
    s.user.age = 26;
    s.todos[0].done = true;
    s.todos.push({ id: 3, text: "Новое", done: false });
  })
);
```

### Когда использовать produce

Когда нужно сделать несколько связанных изменений:

```tsx
// Без produce — много setStore
setStore("user", "name", "Ivan");
setStore("user", "age", 26);
setStore("todos", 0, "done", true);

// С produce — атомарно
setStore(produce((s) => {
  s.user.name = "Ivan";
  s.user.age = 26;
  s.todos[0].done = true;
}));
```

### produce и массивы

```tsx
// Push
setStore("todos", produce((todos) => {
  todos.push({ id: 3, text: "Новое", done: false });
}));

// Удаление по индексу
setStore("todos", produce((todos) => {
  todos.splice(0, 1); // удалить первый
}));

// Изменение элемента
setStore("todos", produce((todos) => {
  const todo = todos.find((t) => t.id === 1);
  if (todo) todo.done = true;
}));
```

---

## 39. reconcile

Используется когда нужно полностью заменить часть store, сохранив реактивность для не изменившихся полей.

```tsx
import { reconcile } from "solid-js/store";

// Сценарий: получили новые данные с сервера
const newUserData = await fetchUser();

// Без reconcile — потеряем все подписки, всё перерендерится
setStore("user", newUserData);

// С reconcile — обновятся только реально изменившиеся поля
setStore("user", reconcile(newUserData));
```

### С key

```tsx
// Для массивов объектов с id
setStore("todos", reconcile(newTodos, { key: "id" }));
// SolidJS сравнит по id, обновит только изменившиеся объекты
```

### Полезно для синхронизации с сервером

```tsx
createEffect(async () => {
  const fresh = await fetch("/api/data").then((r) => r.json());
  setStore(reconcile(fresh, { key: "id" }));
});
```

---

## 40. unwrap

Получить обычный JS объект из reactive store (без прокси):

```tsx
import { unwrap } from "solid-js/store";

const plainUser = unwrap(store.user);
// Обычный объект, не реактивный

// Полезно для отправки на сервер
fetch("/api/user", {
  method: "POST",
  body: JSON.stringify(unwrap(store.user)),
});
```

---

## 41. createMutable

Альтернативный API — можно мутировать напрямую:

```tsx
import { createMutable } from "solid-js/store";

const state = createMutable({
  count: 0,
  user: { name: "Jesus" },
});

// Прямая мутация — работает!
state.count++;
state.user.name = "Ivan";

createEffect(() => {
  console.log(state.count);
});
```

### Когда использовать

Редко. Большинство SolidJS разработчиков предпочитают явный `setStore`. Минусы:
- Менее предсказуемо
- Сложнее отлаживать
- Нельзя так же гибко использовать `produce`, `reconcile`

---

## 42. 🛠 Практика: канбан-доска с drag-and-drop

Полноценная канбан-доска с тремя колонками и перетаскиванием карточек. Использует store с массивами объектов, drag and drop API, produce для атомарных обновлений.

```tsx
import { Component, For, Show } from "solid-js";
import { createStore, produce } from "solid-js/store";

type ColumnId = "todo" | "in-progress" | "done";

interface Card {
  id: string;
  title: string;
  description: string;
  column: ColumnId;
  priority: "low" | "medium" | "high";
}

interface BoardState {
  cards: Card[];
  draggedId: string | null;
  dragOverColumn: ColumnId | null;
}

const COLUMNS: { id: ColumnId; title: string; color: string }[] = [
  { id: "todo", title: "К выполнению", color: "bg-gray-100" },
  { id: "in-progress", title: "В работе", color: "bg-blue-50" },
  { id: "done", title: "Готово", color: "bg-green-50" },
];

const PRIORITY_COLORS = {
  low: "border-l-gray-400",
  medium: "border-l-yellow-500",
  high: "border-l-red-500",
};

const KanbanBoard: Component = () => {
  const [state, setState] = createStore<BoardState>({
    cards: [
      { id: "1", title: "Купить хлеб", description: "В супермаркете", column: "todo", priority: "low" },
      { id: "2", title: "Доделать отчёт", description: "Q4 отчёт по продажам", column: "in-progress", priority: "high" },
      { id: "3", title: "Позвонить маме", description: "", column: "done", priority: "medium" },
    ],
    draggedId: null,
    dragOverColumn: null,
  });

  // Производные данные через геттеры — это работает в SolidJS благодаря прокси
  const cardsInColumn = (col: ColumnId) =>
    state.cards.filter((c) => c.column === col);

  // Drag handlers
  const handleDragStart = (e: DragEvent, cardId: string) => {
    setState("draggedId", cardId);
    if (e.dataTransfer) {
      e.dataTransfer.effectAllowed = "move";
      e.dataTransfer.setData("text/plain", cardId);
    }
  };

  const handleDragEnd = () => {
    setState({ draggedId: null, dragOverColumn: null });
  };

  const handleDragOver = (e: DragEvent, col: ColumnId) => {
    e.preventDefault();
    if (state.dragOverColumn !== col) {
      setState("dragOverColumn", col);
    }
  };

  const handleDrop = (e: DragEvent, targetCol: ColumnId) => {
    e.preventDefault();
    const cardId = state.draggedId;
    if (!cardId) return;

    setState(
      produce((s) => {
        const card = s.cards.find((c) => c.id === cardId);
        if (card) card.column = targetCol;
        s.draggedId = null;
        s.dragOverColumn = null;
      })
    );
  };

  // CRUD операции
  const addCard = (col: ColumnId) => {
    const title = prompt("Название задачи?");
    if (!title?.trim()) return;

    setState("cards", (cards) => [
      ...cards,
      {
        id: crypto.randomUUID(),
        title: title.trim(),
        description: "",
        column: col,
        priority: "medium",
      },
    ]);
  };

  const deleteCard = (id: string) => {
    setState("cards", (cards) => cards.filter((c) => c.id !== id));
  };

  const togglePriority = (id: string) => {
    setState("cards", (c) => c.id === id, "priority", (p) => {
      const order: Card["priority"][] = ["low", "medium", "high"];
      const next = (order.indexOf(p) + 1) % order.length;
      return order[next];
    });
  };

  return (
    <div class="p-6 bg-gray-50 min-h-screen">
      <h1 class="text-2xl font-bold mb-6">Канбан доска</h1>

      <div class="grid grid-cols-3 gap-4">
        <For each={COLUMNS}>
          {(column) => (
            <div
              class={`rounded-lg p-4 ${column.color} ${
                state.dragOverColumn === column.id
                  ? "ring-2 ring-blue-500"
                  : ""
              }`}
              onDragOver={(e) => handleDragOver(e, column.id)}
              onDragLeave={() => setState("dragOverColumn", null)}
              onDrop={(e) => handleDrop(e, column.id)}
            >
              <div class="flex items-center justify-between mb-3">
                <h2 class="font-semibold">
                  {column.title}{" "}
                  <span class="text-sm text-gray-500">
                    ({cardsInColumn(column.id).length})
                  </span>
                </h2>
                <button
                  onClick={() => addCard(column.id)}
                  class="text-blue-500 hover:text-blue-700 text-xl leading-none"
                  title="Добавить задачу"
                >
                  +
                </button>
              </div>

              <div class="space-y-2 min-h-[100px]">
                <For each={cardsInColumn(column.id)}>
                  {(card) => (
                    <div
                      draggable
                      onDragStart={(e) => handleDragStart(e, card.id)}
                      onDragEnd={handleDragEnd}
                      class={`bg-white p-3 rounded shadow-sm border-l-4 cursor-move ${
                        PRIORITY_COLORS[card.priority]
                      } ${
                        state.draggedId === card.id ? "opacity-50" : ""
                      }`}
                    >
                      <div class="flex items-start justify-between gap-2">
                        <h3 class="font-medium flex-1">{card.title}</h3>
                        <button
                          onClick={() => deleteCard(card.id)}
                          class="text-gray-400 hover:text-red-500 text-sm"
                          title="Удалить"
                        >
                          ×
                        </button>
                      </div>
                      <Show when={card.description}>
                        <p class="text-sm text-gray-600 mt-1">
                          {card.description}
                        </p>
                      </Show>
                      <button
                        onClick={() => togglePriority(card.id)}
                        class="mt-2 text-xs text-gray-500 hover:text-gray-700"
                      >
                        Приоритет: {card.priority}
                      </button>
                    </div>
                  )}
                </For>
              </div>
            </div>
          )}
        </For>
      </div>

      <div class="mt-6 text-sm text-gray-600">
        Всего карточек: {state.cards.length}
      </div>
    </div>
  );
};

export default KanbanBoard;
```

### Что важно понять

1. **`createStore` для сложного состояния** — массив + два UI-только поля (`draggedId`, `dragOverColumn`) под одной крышей
2. **`cardsInColumn` как функция-геттер** — производная от `state.cards`, не нужно `createMemo` для каждой колонки
3. **`produce` для drop handler** — атомарно меняем карточку, сбрасываем drag state
4. **Path-based updates** — `setState("cards", (c) => c.id === id, "priority", ...)` обновляет конкретное поле без копирования всего массива
5. **HTML5 Drag API** — встроенный браузерный механизм, без библиотек

В Части XII покажем drag-and-drop без HTML5 API (через mouse events) — для случаев когда нужна более тонкая настройка.

---
---

# Часть VIII — Context

## 43. createContext / useContext

Context — способ передать данные через всё дерево компонентов без prop drilling.

### Базовое использование

```tsx
import { createContext, useContext } from "solid-js";

// 1. Создаём контекст
const ThemeContext = createContext<string>("light");

// 2. Провайдер передаёт значение
const App: Component = () => {
  return (
    <ThemeContext.Provider value="dark">
      <Page />
    </ThemeContext.Provider>
  );
};

// 3. Любой компонент внутри может прочитать
const Button: Component = () => {
  const theme = useContext(ThemeContext);
  return <button class={theme === "dark" ? "bg-black" : "bg-white"}>OK</button>;
};
```

### Проблема — useContext может вернуть undefined

```tsx
const SomeContext = createContext<string>(); // без дефолта

const Component = () => {
  const value = useContext(SomeContext); // string | undefined
};
```

Решения:
1. Передать дефолтное значение в `createContext`
2. Использовать паттерн с кастомным хуком (см. следующую главу)

---

## 44. Паттерн Provider + Hook

Стандартный паттерн для контекста в реальных проектах.

### Полный пример — Auth контекст

```tsx
// src/context/AuthContext.tsx
import {
  createContext,
  useContext,
  createSignal,
  ParentComponent,
  Accessor,
} from "solid-js";

interface User {
  id: number;
  name: string;
  email: string;
}

interface AuthContextType {
  user: Accessor<User | null>;
  login: (email: string, password: string) => Promise<void>;
  logout: () => void;
  isLoggedIn: Accessor<boolean>;
}

const AuthContext = createContext<AuthContextType>();

export const AuthProvider: ParentComponent = (props) => {
  const [user, setUser] = createSignal<User | null>(null);

  const login = async (email: string, password: string) => {
    const response = await fetch("/api/login", {
      method: "POST",
      body: JSON.stringify({ email, password }),
    });
    const userData = await response.json();
    setUser(userData);
  };

  const logout = () => {
    setUser(null);
  };

  const isLoggedIn = () => user() !== null;

  return (
    <AuthContext.Provider value={{ user, login, logout, isLoggedIn }}>
      {props.children}
    </AuthContext.Provider>
  );
};

export const useAuth = () => {
  const ctx = useContext(AuthContext);
  if (!ctx) {
    throw new Error("useAuth должен использоваться внутри AuthProvider");
  }
  return ctx;
};
```

### Использование

```tsx
// App.tsx
import { AuthProvider } from "./context/AuthContext";

const App: Component = () => {
  return (
    <AuthProvider>
      <Router>
        <Route path="/" component={Home} />
      </Router>
    </AuthProvider>
  );
};
```

```tsx
// components/Header.tsx
import { Show } from "solid-js";
import { useAuth } from "../context/AuthContext";

const Header: Component = () => {
  const { user, isLoggedIn, logout } = useAuth();

  return (
    <header>
      <Show when={isLoggedIn()} fallback={<a href="/login">Войти</a>}>
        <p>Привет, {user()?.name}!</p>
        <button onClick={logout}>Выйти</button>
      </Show>
    </header>
  );
};
```

### Преимущества паттерна

1. **Безопасность типов** — `useAuth()` всегда возвращает объект, не undefined
2. **Понятная ошибка** — если забыл провайдер, увидишь чёткое сообщение
3. **Инкапсуляция** — логика логина живёт в одном месте
4. **Легко тестировать** — провайдер можно мокать

---

## 45. Множественные контексты

В реальных приложениях обычно несколько контекстов.

### Композиция провайдеров

```tsx
const App: Component = () => {
  return (
    <AuthProvider>
      <ThemeProvider>
        <CartProvider>
          <Router>
            <Route path="/" component={Home} />
          </Router>
        </CartProvider>
      </ThemeProvider>
    </AuthProvider>
  );
};
```

Минус — вложенность ("provider hell"). Можно сделать хелпер:

```tsx
// utils/composeProviders.tsx
import { JSX, ParentComponent } from "solid-js";

export const composeProviders = (providers: ParentComponent[]) => {
  const ComposedProvider: ParentComponent = (props) => {
    return providers.reduceRight(
      (children, Provider) => <Provider>{children}</Provider>,
      props.children
    ) as JSX.Element;
  };
  return ComposedProvider;
};

// Использование
const AppProviders = composeProviders([
  AuthProvider,
  ThemeProvider,
  CartProvider,
]);

const App: Component = () => {
  return (
    <AppProviders>
      <Router>...</Router>
    </AppProviders>
  );
};
```

### Один контекст использует другой

```tsx
const CartProvider: ParentComponent = (props) => {
  const { user } = useAuth(); // используем другой контекст
  
  createEffect(() => {
    if (user()) {
      // Загрузить корзину пользователя
    }
  });
  
  // ...
};
```

Важно: внешний провайдер должен быть выше в дереве.

---
---

# Часть IX — Async и данные

## 46. createResource

Специальный примитив для асинхронной загрузки данных.

### Базовое использование

```tsx
import { createResource } from "solid-js";

const fetchUser = async (): Promise<User> => {
  const response = await fetch("/api/user");
  return response.json();
};

const Profile: Component = () => {
  const [user] = createResource(fetchUser);

  return (
    <div>
      <Show when={user()} fallback={<p>Загрузка...</p>}>
        <p>{user()?.name}</p>
      </Show>
    </div>
  );
};
```

### Полная сигнатура

```ts
function createResource<T, S = true>(
  fetcher: (source: S) => Promise<T>,
  options?: ResourceOptions<T>
): [Resource<T>, ResourceActions<T>];

function createResource<T, S>(
  source: Accessor<S | false | null | undefined>,
  fetcher: (source: S) => Promise<T>,
  options?: ResourceOptions<T>
): [Resource<T>, ResourceActions<T>];

interface Resource<T> {
  (): T | undefined;
  loading: boolean;
  error: any;
  state: "unresolved" | "pending" | "ready" | "refreshing" | "errored";
}

interface ResourceActions<T> {
  mutate: (value: T | undefined) => void;
  refetch: (info?: unknown) => Promise<T | undefined>;
}
```

### С реактивным источником

Первый аргумент — реактивный источник. Когда он меняется — данные перезагружаются:

```tsx
const [userId, setUserId] = createSignal(1);

const fetchUser = async (id: number): Promise<User> => {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
};

const [user] = createResource(userId, fetchUser);
// При изменении userId() — автоматический refetch
```

### Условная загрузка

Если источник возвращает `false`, `null` или `undefined` — fetcher не вызывается:

```tsx
const [userId, setUserId] = createSignal<number | null>(null);

const [user] = createResource(userId, fetchUser);
// Пока userId === null — fetcher не запускается

setUserId(1); // теперь запустится
```

### Состояния

```tsx
const [data] = createResource(fetchData);

data()           // T | undefined — значение
data.loading     // boolean — идёт ли загрузка
data.error       // ошибка если упало
data.state       // "unresolved" | "pending" | "ready" | "refreshing" | "errored"
```

### Полный пример — обработка состояний

```tsx
const ProductPage: Component = () => {
  const params = useParams<{ id: string }>();
  const [product] = createResource(() => params.id, fetchProduct);

  return (
    <div>
      <Switch>
        <Match when={product.loading}>
          <Spinner />
        </Match>
        <Match when={product.error}>
          <p>Ошибка: {product.error.message}</p>
        </Match>
        <Match when={product()}>
          {(product) => (
            <div>
              <h1>{product().name}</h1>
              <p>{product().price} грн</p>
            </div>
          )}
        </Match>
      </Switch>
    </div>
  );
};
```

### Refetch — перезагрузка

```tsx
const [data, { refetch }] = createResource(fetchData);

<button onClick={() => refetch()}>Обновить</button>
```

### Mutate — локальное изменение без запроса

Полезно для оптимистических обновлений:

```tsx
const [todos, { mutate, refetch }] = createResource(fetchTodos);

const toggleTodo = async (id: number) => {
  // Оптимистическое обновление
  mutate(
    todos()?.map((t) => (t.id === id ? { ...t, done: !t.done } : t))
  );
  
  try {
    // Реальный запрос
    await fetch(`/api/todos/${id}/toggle`, { method: "POST" });
  } catch (error) {
    // Откатить при ошибке
    refetch();
  }
};
```

### Опции

```tsx
const [data] = createResource(fetchData, {
  initialValue: [],         // значение пока грузится
  name: "users-resource",   // для devtools
  deferStream: false,       // для SSR
  ssrLoadFrom: "initial",   // SSR стратегия
});
```

---

## 47. \<Suspense\>

Граница которая показывает fallback пока внутри идёт async загрузка.

### Базовое использование

```tsx
import { Suspense } from "solid-js";

<Suspense fallback={<p>Загрузка...</p>}>
  <UserProfile /> {/* использует createResource внутри */}
</Suspense>
```

`<Suspense>` автоматически отслеживает все `createResource` внутри. Пока хоть один грузится — показывается fallback.

### Несколько ресурсов

```tsx
const UserProfile: Component = () => {
  const [user] = createResource(fetchUser);
  const [posts] = createResource(fetchPosts);
  const [followers] = createResource(fetchFollowers);

  return (
    <Suspense fallback={<p>Загрузка...</p>}>
      {/* Покажется только когда ВСЕ три загрузятся */}
      <div>
        <h1>{user()?.name}</h1>
        <PostList posts={posts()} />
        <FollowerList followers={followers()} />
      </div>
    </Suspense>
  );
};
```

### Вложенные Suspense

```tsx
<Suspense fallback={<MainSpinner />}>
  <UserInfo />
  
  <Suspense fallback={<SmallSpinner />}>
    <UserPosts />
  </Suspense>
</Suspense>
```

Внутренний Suspense ловит только своё поддерево.

### Suspense vs Show с loading

```tsx
// Подход 1 — через Show (плохо для нескольких ресурсов)
const [data] = createResource(fetchData);
<Show when={!data.loading} fallback={<Spinner />}>
  <Content data={data()!} />
</Show>

// Подход 2 — через Suspense (лучше)
<Suspense fallback={<Spinner />}>
  <Content /> {/* читает data() внутри */}
</Suspense>
```

---

## 48. \<SuspenseList\>

Координирует несколько Suspense — задаёт порядок их раскрытия.

```tsx
import { SuspenseList, Suspense } from "solid-js";

<SuspenseList revealOrder="forwards">
  <Suspense fallback={<Spinner />}>
    <FirstSection />
  </Suspense>
  <Suspense fallback={<Spinner />}>
    <SecondSection />
  </Suspense>
  <Suspense fallback={<Spinner />}>
    <ThirdSection />
  </Suspense>
</SuspenseList>
```

Опции `revealOrder`:
- `"forwards"` — сверху вниз
- `"backwards"` — снизу вверх
- `"together"` — всё сразу когда последний загрузится

---

## 49. useTransition / startTransition

Помечают обновления как "не срочные" — UI остаётся отзывчивым пока обновления применяются.

### Использование

```tsx
import { useTransition, createSignal } from "solid-js";

const Component: Component = () => {
  const [isPending, start] = useTransition();
  const [tab, setTab] = createSignal("home");

  const switchTab = (newTab: string) => {
    start(() => {
      setTab(newTab); // тяжёлое обновление
    });
  };

  return (
    <div>
      <button onClick={() => switchTab("home")}>Home</button>
      <button onClick={() => switchTab("about")}>About</button>
      <Show when={isPending()}>
        <Spinner />
      </Show>
      <TabContent tab={tab()} />
    </div>
  );
};
```

### Когда полезно

- Переключение между табами с тяжёлым контентом
- Изменение фильтров над большим списком
- Любые обновления state которые могут вызывать заметные подвисания UI

---

## 50. 🛠 Практика: infinite scroll с пагинацией

Бесконечная лента — классический паттерн для социалок и e-commerce. Использует IntersectionObserver, createResource, store с массивом.

```tsx
import {
  Component,
  For,
  Show,
  createSignal,
  createEffect,
  onMount,
  onCleanup,
} from "solid-js";
import { createStore } from "solid-js/store";

interface Post {
  id: number;
  title: string;
  body: string;
}

interface FeedState {
  posts: Post[];
  page: number;
  hasMore: boolean;
  isLoading: boolean;
  error: string | null;
}

const PAGE_SIZE = 10;

const fetchPosts = async (page: number): Promise<Post[]> => {
  const response = await fetch(
    `https://jsonplaceholder.typicode.com/posts?_page=${page}&_limit=${PAGE_SIZE}`
  );
  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }
  return response.json();
};

const InfiniteFeed: Component = () => {
  const [state, setState] = createStore<FeedState>({
    posts: [],
    page: 1,
    hasMore: true,
    isLoading: false,
    error: null,
  });

  let sentinelRef!: HTMLDivElement;
  let observer: IntersectionObserver | null = null;

  const loadMore = async () => {
    if (state.isLoading || !state.hasMore) return;

    setState({ isLoading: true, error: null });

    try {
      const newPosts = await fetchPosts(state.page);
      setState((s) => ({
        posts: [...s.posts, ...newPosts],
        page: s.page + 1,
        hasMore: newPosts.length === PAGE_SIZE,
        isLoading: false,
      }));
    } catch (err) {
      setState({
        isLoading: false,
        error: (err as Error).message,
      });
    }
  };

  onMount(() => {
    // Загружаем первую страницу
    loadMore();

    // IntersectionObserver — следит когда sentinel виден
    observer = new IntersectionObserver(
      (entries) => {
        if (entries[0].isIntersecting) {
          loadMore();
        }
      },
      { rootMargin: "200px" } // начинаем загружать за 200px до конца
    );

    observer.observe(sentinelRef);

    onCleanup(() => observer?.disconnect());
  });

  const retry = () => {
    setState("error", null);
    loadMore();
  };

  return (
    <div class="max-w-2xl mx-auto p-4">
      <h1 class="text-2xl font-bold mb-4">Лента постов</h1>

      <div class="space-y-4">
        <For each={state.posts}>
          {(post) => (
            <article class="bg-white p-4 rounded shadow">
              <h2 class="font-semibold mb-2">{post.title}</h2>
              <p class="text-gray-700 text-sm">{post.body}</p>
            </article>
          )}
        </For>
      </div>

      {/* Sentinel — невидимый элемент в конце списка */}
      <div ref={sentinelRef} class="h-1" />

      <div class="py-4 text-center">
        <Show when={state.isLoading}>
          <div class="flex items-center justify-center gap-2">
            <div class="w-5 h-5 border-2 border-blue-500 border-t-transparent rounded-full animate-spin" />
            <span class="text-gray-600">Загрузка...</span>
          </div>
        </Show>

        <Show when={state.error}>
          <div class="text-red-500">
            <p>Ошибка: {state.error}</p>
            <button
              onClick={retry}
              class="mt-2 text-blue-500 underline"
            >
              Попробовать снова
            </button>
          </div>
        </Show>

        <Show when={!state.hasMore && state.posts.length > 0}>
          <p class="text-gray-500">Больше постов нет</p>
        </Show>
      </div>

      <div class="text-xs text-gray-400 mt-4">
        Загружено: {state.posts.length} | Страница: {state.page - 1}
      </div>
    </div>
  );
};

export default InfiniteFeed;
```

### Что здесь происходит

1. **`createStore` для feed state** — пагинация требует много связанных полей
2. **`IntersectionObserver`** — браузерный API для отслеживания видимости элементов. Эффективнее чем onScroll
3. **Sentinel pattern** — невидимый `<div>` в конце списка. Когда он становится виден — загружаем следующую страницу
4. **`rootMargin: "200px"`** — начинаем загружать за 200px до конца, чтобы пользователь не видел паузы
5. **`onCleanup` для observer** — без него утечка памяти
6. **`hasMore`** — флаг что данные закончились (если сервер вернул меньше PAGE_SIZE)

### Преимущества этого подхода

- Не дёргается на каждый scroll event (как было бы с onScroll)
- Работает на любом устройстве и в любых размерах окна
- Можно настроить когда срабатывать через `rootMargin`

В Части XII (DOM) разберём `IntersectionObserver` подробнее — он используется для lazy images, sticky elements, analytics.

---
---
---

# Часть X — Роутинг

Роутинг в SolidJS — пакет `@solidjs/router`. Не входит в core, ставится отдельно.

```bash
pnpm add @solidjs/router
```

## 51. @solidjs/router основы

### Минимальный пример

```tsx
import { Router, Route } from "@solidjs/router";
import { Component, lazy } from "solid-js";

const Home = lazy(() => import("./pages/Home"));
const About = lazy(() => import("./pages/About"));
const NotFound = lazy(() => import("./pages/NotFound"));

const App: Component = () => {
  return (
    <Router>
      <Route path="/" component={Home} />
      <Route path="/about" component={About} />
      <Route path="*" component={NotFound} />
    </Router>
  );
};
```

### Динамические сегменты

```tsx
<Route path="/users/:id" component={UserPage} />
<Route path="/posts/:slug" component={PostPage} />
```

Получение параметров:

```tsx
import { useParams } from "@solidjs/router";

const UserPage: Component = () => {
  const params = useParams<{ id: string }>();
  return <div>User ID: {params.id}</div>;
};
```

`params` реактивный — при смене URL обновляется автоматически.

### Опциональные сегменты

```tsx
<Route path="/products/:category?" component={ProductsPage} />
// /products → category = undefined
// /products/shoes → category = "shoes"
```

### Wildcard / catch-all

```tsx
<Route path="/docs/*" component={DocsPage} />
// matches /docs, /docs/intro, /docs/api/foo

// Получить остаток пути
const params = useParams<{ "*": string }>();
```

### Навигация — Link и A

```tsx
import { A } from "@solidjs/router";

<A href="/about">О нас</A>
<A href="/users/1" activeClass="text-blue-500">User 1</A>
```

`A` (alias `Link`) автоматически применяет `activeClass` если текущий URL совпадает.

---

## 52. Вложенные роуты и Outlet

Вложенные роуты позволяют создавать лэйауты с общими частями (header, sidebar).

```tsx
import { Outlet } from "@solidjs/router";

const DashboardLayout: Component = () => {
  return (
    <div class="flex">
      <Sidebar />
      <main class="flex-1 p-4">
        <Outlet /> {/* сюда подставится содержимое вложенного роута */}
      </main>
    </div>
  );
};

const App: Component = () => {
  return (
    <Router>
      <Route path="/dashboard" component={DashboardLayout}>
        <Route path="/" component={DashboardHome} />
        <Route path="/users" component={UsersPage} />
        <Route path="/settings" component={SettingsPage} />
      </Route>
    </Router>
  );
};
```

- `/dashboard` → DashboardLayout + DashboardHome
- `/dashboard/users` → DashboardLayout + UsersPage
- `/dashboard/settings` → DashboardLayout + SettingsPage

### Вложенность 3+ уровней

```tsx
<Route path="/admin" component={AdminLayout}>
  <Route path="/users" component={UsersLayout}>
    <Route path="/" component={UserList} />
    <Route path="/:id" component={UserDetail} />
    <Route path="/:id/edit" component={UserEdit} />
  </Route>
</Route>
```

---

## 53. Лэйауты

Часто нужны разные лэйауты для разных частей приложения (публичный, аутентифицированный, админ).

```tsx
const PublicLayout: Component = () => (
  <>
    <PublicHeader />
    <Outlet />
    <Footer />
  </>
);

const AuthLayout: Component = () => (
  <div class="flex">
    <UserSidebar />
    <main><Outlet /></main>
  </div>
);

const App: Component = () => (
  <Router>
    <Route path="/" component={PublicLayout}>
      <Route path="/" component={Home} />
      <Route path="/about" component={About} />
      <Route path="/login" component={Login} />
    </Route>
    
    <Route path="/app" component={AuthLayout}>
      <Route path="/" component={Dashboard} />
      <Route path="/profile" component={Profile} />
    </Route>
  </Router>
);
```

---

## 54. Защищённые роуты

Паттерн для роутов которые требуют авторизации:

```tsx
import { Navigate, RouteSectionProps } from "@solidjs/router";
import { useAuth } from "./context/AuthContext";
import { Show } from "solid-js";

const ProtectedRoute: Component<RouteSectionProps> = (props) => {
  const { isLoggedIn } = useAuth();
  
  return (
    <Show when={isLoggedIn()} fallback={<Navigate href="/login" />}>
      {props.children}
    </Show>
  );
};

// Использование
<Route path="/app" component={ProtectedRoute}>
  <Route path="/" component={Dashboard} />
  <Route path="/profile" component={Profile} />
</Route>
```

### С ролями

```tsx
const RequireRole: Component<{ role: "admin" | "user"; children: JSX.Element }> = (props) => {
  const { user } = useAuth();
  
  return (
    <Show
      when={user()?.role === props.role}
      fallback={<Navigate href="/403" />}
    >
      {props.children}
    </Show>
  );
};

<Route path="/admin" component={(p) => (
  <RequireRole role="admin">{p.children}</RequireRole>
)}>
  <Route path="/users" component={AdminUsers} />
</Route>
```

---

## 55. useSearchParams, useLocation, useNavigate

### useSearchParams — query параметры

```tsx
import { useSearchParams } from "@solidjs/router";

const SearchPage: Component = () => {
  const [params, setParams] = useSearchParams<{ q?: string; page?: string }>();
  
  // Чтение
  const query = () => params.q ?? "";
  const page = () => Number(params.page ?? 1);
  
  // Запись
  const setQuery = (q: string) => setParams({ q });
  const nextPage = () => setParams({ page: String(page() + 1) });
  
  return (
    <div>
      <input
        value={query()}
        onInput={(e) => setQuery(e.currentTarget.value)}
      />
      <p>Страница: {page()}</p>
      <button onClick={nextPage}>Далее</button>
    </div>
  );
};
```

URL автоматически обновляется: `/search?q=solid&page=2`.

### useLocation

```tsx
import { useLocation } from "@solidjs/router";

const Component: Component = () => {
  const location = useLocation();
  
  location.pathname    // "/users/1"
  location.search      // "?tab=posts"
  location.hash        // "#comments"
  location.query       // { tab: "posts" }
  location.state       // данные переданные при navigate
};
```

### useNavigate — программная навигация

```tsx
import { useNavigate } from "@solidjs/router";

const LoginForm: Component = () => {
  const navigate = useNavigate();
  
  const handleSubmit = async () => {
    await login();
    navigate("/dashboard");
    
    // С опциями
    navigate("/profile", { replace: true });  // replace вместо push
    navigate("/dashboard", { state: { from: "login" } });  // передать state
    navigate(-1);  // назад
  };
};
```

---

## 56. Загрузка данных на уровне роута

Современный подход — `query` + `createAsync` + `preload`. Старые API (`useRouteData`, `data` пропа на роуте) удалены в новых версиях `@solidjs/router`.

### Основной паттерн

```tsx
import { query, createAsync, useParams, RouteDefinition } from "@solidjs/router";

// 1. Объявляем query — кэшируемую async функцию
const getUser = query(async (id: string): Promise<User> => {
  const response = await fetch(`/api/users/${id}`);
  if (!response.ok) throw new Error(`HTTP ${response.status}`);
  return response.json();
}, "user");

// 2. preload запускает загрузку до того как компонент смонтируется
export const route = {
  preload({ params }) {
    void getUser(params.id);
  },
} satisfies RouteDefinition;

// 3. В компоненте — реактивная подписка через createAsync
const UserPage: Component = () => {
  const params = useParams<{ id: string }>();
  const user = createAsync(() => getUser(params.id));

  return (
    <Suspense fallback={<p>Загрузка...</p>}>
      <Show when={user()}>
        {(user) => <div>{user().name}</div>}
      </Show>
    </Suspense>
  );
};

// 4. Подключаем как обычный роут
<Route path="/users/:id" component={UserPage} />
```

### Зачем preload отдельно от компонента

Преимущества:
- Загрузка начинается параллельно с загрузкой JS-чанка компонента
- При переходе пользователь почти не видит fallback
- query кэширует результат — повторный заход не делает новый запрос

### Preload при наведении

```tsx
<A href="/users/1" preload>User 1</A>
// При наведении мышкой — запускается preload роута и его query
```

### Когда query/createAsync vs createResource

| Случай | Использовать |
|---|---|
| Данные привязаны к роуту | `query` + `createAsync` + `preload` |
| Данные внутри компонента, не зависят от роута | `createResource` |
| Нужно кэширование на уровне приложения | `query` (имеет ключ, может revalidate) |
| Простая загрузка в виджете | `createResource` |

Подробнее `query` и actions разбираются в Части XIX (SolidStart) — там их применение раскрывается полнее.

---
---

# Часть XI — Формы (НОВАЯ)

Формы — 40% работы фронтенда. Эта глава покрывает всё что нужно для production форм.

## 57. Контролируемые инпуты

В SolidJS компоненты не перерендеривают весь UI при изменении — поэтому "контролируемые" инпуты работают эффективно из коробки.

### Текстовый инпут

```tsx
import { Component, createSignal } from "solid-js";

const Form: Component = () => {
  const [name, setName] = createSignal("");
  
  return (
    <input
      type="text"
      value={name()}
      onInput={(e) => setName(e.currentTarget.value)}
    />
  );
};
```

### Важно: onInput vs onChange

В отличие от React, где `onChange` срабатывает на каждый ввод — в DOM API:
- `onInput` — при каждом изменении значения (то что обычно нужно)
- `onChange` — при потере фокуса (как у `<select>`, или у `<input>` после blur)

В SolidJS используется DOM-семантика — **используй `onInput`** для текстовых полей.

```tsx
// ❌ Так делают по привычке из React — неправильно для текста
<input onChange={(e) => setName(e.currentTarget.value)} />

// ✅ В Solid правильно onInput
<input onInput={(e) => setName(e.currentTarget.value)} />
```

### Получение значения — e.currentTarget vs e.target

```tsx
// ✅ Предпочтительнее — e.currentTarget типизирован правильно
<input onInput={(e) => setName(e.currentTarget.value)} />

// ❌ e.target может быть undefined в TS из-за event bubbling
<input onInput={(e) => setName(e.target.value)} /> // TS ругается
```

`e.currentTarget` — это элемент на котором висит обработчик (всегда тот же). `e.target` — где событие изначально произошло (может отличаться при делегировании).

---

## 58. Все типы полей

### Text, email, password, tel, url

```tsx
<input type="text" value={name()} onInput={(e) => setName(e.currentTarget.value)} />
<input type="email" value={email()} onInput={(e) => setEmail(e.currentTarget.value)} />
<input type="password" value={password()} onInput={(e) => setPassword(e.currentTarget.value)} />
<input type="tel" value={phone()} onInput={(e) => setPhone(e.currentTarget.value)} />
<input type="url" value={url()} onInput={(e) => setUrl(e.currentTarget.value)} />
```

### Number

```tsx
const [age, setAge] = createSignal(0);

<input
  type="number"
  value={age()}
  onInput={(e) => setAge(Number(e.currentTarget.value))}
  min="0"
  max="120"
  step="1"
/>
```

**Внимание:** `e.currentTarget.value` всегда string. Нужно конвертировать в number.

### Textarea

```tsx
<textarea
  value={description()}
  onInput={(e) => setDescription(e.currentTarget.value)}
  rows="5"
/>
```

### Checkbox

```tsx
const [agreed, setAgreed] = createSignal(false);

<label class="flex items-center gap-2">
  <input
    type="checkbox"
    checked={agreed()}
    onChange={(e) => setAgreed(e.currentTarget.checked)}
  />
  <span>Согласен с условиями</span>
</label>
```

**Для checkbox используется `checked`, не `value`. И `onChange`, не `onInput`.**

### Группа чекбоксов

```tsx
const [hobbies, setHobbies] = createSignal<string[]>([]);

const toggleHobby = (hobby: string) => {
  setHobbies((prev) =>
    prev.includes(hobby) ? prev.filter((h) => h !== hobby) : [...prev, hobby]
  );
};

<For each={["sport", "music", "gaming", "reading"]}>
  {(hobby) => (
    <label class="flex items-center gap-2">
      <input
        type="checkbox"
        checked={hobbies().includes(hobby)}
        onChange={() => toggleHobby(hobby)}
      />
      <span>{hobby}</span>
    </label>
  )}
</For>
```

### Radio

```tsx
const [gender, setGender] = createSignal<"male" | "female" | "other">("male");

<For each={["male", "female", "other"] as const}>
  {(g) => (
    <label class="flex items-center gap-2">
      <input
        type="radio"
        name="gender"
        value={g}
        checked={gender() === g}
        onChange={() => setGender(g)}
      />
      <span>{g}</span>
    </label>
  )}
</For>
```

### Select

```tsx
const [country, setCountry] = createSignal("UA");

<select
  value={country()}
  onChange={(e) => setCountry(e.currentTarget.value)}
>
  <option value="UA">Украина</option>
  <option value="PL">Польша</option>
  <option value="DE">Германия</option>
</select>
```

### Multi-select

```tsx
const [selectedTags, setSelectedTags] = createSignal<string[]>([]);

<select
  multiple
  onChange={(e) => {
    const opts = Array.from(e.currentTarget.selectedOptions);
    setSelectedTags(opts.map((o) => o.value));
  }}
>
  <option value="js" selected={selectedTags().includes("js")}>JavaScript</option>
  <option value="ts" selected={selectedTags().includes("ts")}>TypeScript</option>
  <option value="py" selected={selectedTags().includes("py")}>Python</option>
</select>
```

### Date / Time

```tsx
const [birthday, setBirthday] = createSignal("");

<input
  type="date"
  value={birthday()}
  onInput={(e) => setBirthday(e.currentTarget.value)}
  max={new Date().toISOString().split("T")[0]}
/>

// Time
const [time, setTime] = createSignal("12:00");
<input type="time" value={time()} onInput={(e) => setTime(e.currentTarget.value)} />

// Datetime
const [dt, setDt] = createSignal("");
<input type="datetime-local" value={dt()} onInput={(e) => setDt(e.currentTarget.value)} />
```

### File

```tsx
const [file, setFile] = createSignal<File | null>(null);

<input
  type="file"
  accept="image/*"
  onChange={(e) => setFile(e.currentTarget.files?.[0] ?? null)}
/>

<Show when={file()}>
  <p>Выбран: {file()!.name} ({(file()!.size / 1024).toFixed(1)} KB)</p>
</Show>
```

### Multiple files

```tsx
const [files, setFiles] = createSignal<File[]>([]);

<input
  type="file"
  multiple
  onChange={(e) => setFiles(Array.from(e.currentTarget.files ?? []))}
/>

<For each={files()}>
  {(file) => <p>{file.name}</p>}
</For>
```

### Range slider

```tsx
const [volume, setVolume] = createSignal(50);

<input
  type="range"
  min="0"
  max="100"
  value={volume()}
  onInput={(e) => setVolume(Number(e.currentTarget.value))}
/>
<p>Громкость: {volume()}%</p>
```

### Color picker

```tsx
const [color, setColor] = createSignal("#3b82f6");

<input
  type="color"
  value={color()}
  onInput={(e) => setColor(e.currentTarget.value)}
/>
```

---

## 59. Валидация

### Ручная валидация

```tsx
import { Component, createSignal, createMemo } from "solid-js";

const SignupForm: Component = () => {
  const [email, setEmail] = createSignal("");
  const [password, setPassword] = createSignal("");
  const [submitted, setSubmitted] = createSignal(false);
  
  // Ошибки как мемо — обновляются автоматически
  const emailError = createMemo(() => {
    if (!email()) return "Email обязателен";
    if (!/^[^@]+@[^@]+\.[^@]+$/.test(email())) return "Неверный формат";
    return null;
  });
  
  const passwordError = createMemo(() => {
    if (!password()) return "Пароль обязателен";
    if (password().length < 8) return "Минимум 8 символов";
    return null;
  });
  
  const isValid = createMemo(() => !emailError() && !passwordError());
  
  const handleSubmit = (e: SubmitEvent) => {
    e.preventDefault();
    setSubmitted(true);
    if (isValid()) {
      console.log("Отправка:", { email: email(), password: password() });
    }
  };
  
  // Показываем ошибки только после первой попытки submit
  const showEmailError = () => submitted() && emailError();
  const showPasswordError = () => submitted() && passwordError();
  
  return (
    <form onSubmit={handleSubmit} class="space-y-3">
      <div>
        <input
          type="email"
          value={email()}
          onInput={(e) => setEmail(e.currentTarget.value)}
          class={`border rounded px-3 py-2 ${
            showEmailError() ? "border-red-500" : ""
          }`}
        />
        <Show when={showEmailError()}>
          <p class="text-red-500 text-sm mt-1">{emailError()}</p>
        </Show>
      </div>
      
      <div>
        <input
          type="password"
          value={password()}
          onInput={(e) => setPassword(e.currentTarget.value)}
          class={`border rounded px-3 py-2 ${
            showPasswordError() ? "border-red-500" : ""
          }`}
        />
        <Show when={showPasswordError()}>
          <p class="text-red-500 text-sm mt-1">{passwordError()}</p>
        </Show>
      </div>
      
      <button
        type="submit"
        disabled={!isValid()}
        class="bg-blue-500 text-white px-4 py-2 rounded disabled:opacity-50"
      >
        Регистрация
      </button>
    </form>
  );
};
```

### Валидация через Zod

`zod` — самая популярная библиотека для валидации в TS экосистеме.

```bash
pnpm add zod
```

```tsx
import { z } from "zod";

const schema = z.object({
  email: z.string().email("Неверный email"),
  password: z.string().min(8, "Минимум 8 символов"),
  age: z.number().int().min(18, "Минимум 18 лет"),
});

type FormData = z.infer<typeof schema>;

// Валидация
const result = schema.safeParse({ email: "test@test", password: "123", age: 17 });

if (result.success) {
  console.log(result.data); // FormData с правильными типами
} else {
  console.log(result.error.flatten().fieldErrors);
  // { email: ["Неверный email"], password: ["Минимум 8 символов"], age: ["Минимум 18 лет"] }
}
```

### Интеграция Zod с формой

```tsx
import { z } from "zod";
import { createStore } from "solid-js/store";

const schema = z.object({
  email: z.string().email("Неверный email"),
  password: z.string().min(8, "Минимум 8 символов"),
});

type FormValues = z.infer<typeof schema>;
type FormErrors = Partial<Record<keyof FormValues, string>>;

const SignupForm: Component = () => {
  const [values, setValues] = createStore<FormValues>({ email: "", password: "" });
  const [errors, setErrors] = createStore<FormErrors>({});
  
  const validate = (): boolean => {
    const result = schema.safeParse(values);
    if (result.success) {
      setErrors({});
      return true;
    }
    const fieldErrors = result.error.flatten().fieldErrors;
    setErrors({
      email: fieldErrors.email?.[0],
      password: fieldErrors.password?.[0],
    });
    return false;
  };
  
  const handleSubmit = (e: SubmitEvent) => {
    e.preventDefault();
    if (validate()) {
      console.log("Submit:", values);
    }
  };
  
  return (
    <form onSubmit={handleSubmit} class="space-y-3">
      <input
        value={values.email}
        onInput={(e) => setValues("email", e.currentTarget.value)}
        onBlur={validate}
      />
      <Show when={errors.email}>
        <p class="text-red-500">{errors.email}</p>
      </Show>
      
      <input
        type="password"
        value={values.password}
        onInput={(e) => setValues("password", e.currentTarget.value)}
        onBlur={validate}
      />
      <Show when={errors.password}>
        <p class="text-red-500">{errors.password}</p>
      </Show>
      
      <button type="submit">Регистрация</button>
    </form>
  );
};
```

---

## 60. Отправка формы и состояния

Состояние отправки формы — классический случай для дискриминированного union (см. раздел 33):

```tsx
type SubmitState =
  | { status: "idle" }
  | { status: "submitting" }
  | { status: "success"; message: string }
  | { status: "error"; message: string };

const Form: Component = () => {
  const [submitState, setSubmitState] = createSignal<SubmitState>({ status: "idle" });
  
  const handleSubmit = async (e: SubmitEvent) => {
    e.preventDefault();
    setSubmitState({ status: "submitting" });
    
    try {
      const response = await fetch("/api/signup", {
        method: "POST",
        body: JSON.stringify(formData),
      });
      
      if (!response.ok) {
        const error = await response.json();
        throw new Error(error.message);
      }
      
      setSubmitState({ status: "success", message: "Регистрация успешна!" });
    } catch (err) {
      setSubmitState({
        status: "error",
        message: (err as Error).message,
      });
    }
  };
  
  return (
    <form onSubmit={handleSubmit}>
      {/* поля */}
      
      <Switch>
        <Match when={submitState().status === "idle"}>
          <button type="submit">Отправить</button>
        </Match>
        <Match when={submitState().status === "submitting"}>
          <button type="submit" disabled>Отправка...</button>
        </Match>
        <Match when={submitState().status === "success"}>
          {(_) => {
            const s = submitState();
            if (s.status !== "success") return null;
            return <p class="text-green-500">{s.message}</p>;
          }}
        </Match>
        <Match when={submitState().status === "error"}>
          {(_) => {
            const s = submitState();
            if (s.status !== "error") return null;
            return (
              <>
                <p class="text-red-500">{s.message}</p>
                <button type="submit">Попробовать снова</button>
              </>
            );
          }}
        </Match>
      </Switch>
    </form>
  );
};
```

---

## 61. Динамические формы

Формы где количество полей меняется (массивы, conditional fields).

### Массив полей — добавление/удаление

```tsx
import { createStore, produce } from "solid-js/store";

interface ContactsFormState {
  contacts: { name: string; email: string }[];
}

const ContactsForm: Component = () => {
  const [state, setState] = createStore<ContactsFormState>({
    contacts: [{ name: "", email: "" }],
  });
  
  const addContact = () => {
    setState("contacts", (prev) => [...prev, { name: "", email: "" }]);
  };
  
  const removeContact = (index: number) => {
    setState("contacts", (prev) => prev.filter((_, i) => i !== index));
  };
  
  const updateContact = (index: number, field: "name" | "email", value: string) => {
    setState("contacts", index, field, value);
  };
  
  return (
    <div class="space-y-3">
      <For each={state.contacts}>
        {(contact, index) => (
          <div class="flex gap-2">
            <input
              placeholder="Имя"
              value={contact.name}
              onInput={(e) => updateContact(index(), "name", e.currentTarget.value)}
              class="border rounded px-3 py-2 flex-1"
            />
            <input
              placeholder="Email"
              value={contact.email}
              onInput={(e) => updateContact(index(), "email", e.currentTarget.value)}
              class="border rounded px-3 py-2 flex-1"
            />
            <button
              onClick={() => removeContact(index())}
              type="button"
              class="text-red-500 px-2"
            >
              ×
            </button>
          </div>
        )}
      </For>
      <button
        onClick={addContact}
        type="button"
        class="text-blue-500"
      >
        + Добавить контакт
      </button>
    </div>
  );
};
```

### Условные поля

```tsx
const [hasCompany, setHasCompany] = createSignal(false);

<>
  <label class="flex items-center gap-2">
    <input
      type="checkbox"
      checked={hasCompany()}
      onChange={(e) => setHasCompany(e.currentTarget.checked)}
    />
    У меня есть компания
  </label>
  
  <Show when={hasCompany()}>
    <input placeholder="Название компании" />
    <input placeholder="ИНН" />
    <select>
      <option>ООО</option>
      <option>ИП</option>
    </select>
  </Show>
</>
```

---

## 62. Библиотеки форм: @modular-forms/solid

Для сложных форм с валидацией, ошибками, состояниями — лучше взять готовую библиотеку.

`@modular-forms/solid` — самая популярная в SolidJS экосистеме.

```bash
pnpm add @modular-forms/solid
```

### Базовый пример

```tsx
import { createForm, SubmitHandler, valiForm } from "@modular-forms/solid";
import * as v from "valibot";

const LoginSchema = v.object({
  email: v.pipe(v.string(), v.email("Неверный email")),
  password: v.pipe(v.string(), v.minLength(8, "Минимум 8 символов")),
});

type LoginFormValues = v.InferInput<typeof LoginSchema>;

const LoginForm: Component = () => {
  const [loginForm, { Form, Field }] = createForm<LoginFormValues>({
    validate: valiForm(LoginSchema),
  });
  
  const handleSubmit: SubmitHandler<LoginFormValues> = async (values) => {
    console.log("Submit:", values);
    await loginUser(values);
  };
  
  return (
    <Form onSubmit={handleSubmit}>
      <Field name="email">
        {(field, props) => (
          <div>
            <input {...props} type="email" value={field.value ?? ""} />
            {field.error && <p class="text-red-500">{field.error}</p>}
          </div>
        )}
      </Field>
      
      <Field name="password">
        {(field, props) => (
          <div>
            <input {...props} type="password" value={field.value ?? ""} />
            {field.error && <p class="text-red-500">{field.error}</p>}
          </div>
        )}
      </Field>
      
      <button type="submit" disabled={loginForm.submitting}>
        {loginForm.submitting ? "Вход..." : "Войти"}
      </button>
    </Form>
  );
};
```

### Что даёт библиотека

- Управление состоянием полей (value, error, touched, dirty)
- Валидация (с zod, valibot, yup или кастомной)
- Состояние submitting / submitted
- Field array helpers (добавление/удаление в массивах)
- Прогрессивное enhancement (работает без JS на сервере с SolidStart)

В простых формах из 2-3 полей библиотека избыточна. Для форм 5+ полей с серьёзной валидацией — стоит брать.

---

## 63. 🛠 Практика: форма регистрации с валидацией

Полнофункциональная форма регистрации. Включает: все типы полей, валидацию Zod, индикатор силы пароля, асинхронную проверку username, состояния submit.

```tsx
import { Component, createSignal, createMemo, Show, For, Match, Switch } from "solid-js";
import { createStore } from "solid-js/store";
import { z } from "zod";

const SignupSchema = z.object({
  username: z.string()
    .min(3, "Минимум 3 символа")
    .max(20, "Максимум 20 символов")
    .regex(/^[a-zA-Z0-9_]+$/, "Только буквы, цифры и _"),
  email: z.string().email("Неверный email"),
  password: z.string()
    .min(8, "Минимум 8 символов")
    .regex(/[A-Z]/, "Должна быть заглавная буква")
    .regex(/[0-9]/, "Должна быть цифра"),
  passwordConfirm: z.string(),
  age: z.number().int().min(18, "Минимум 18 лет").max(120, "Слишком много"),
  country: z.enum(["UA", "PL", "DE", "US"]),
  agreed: z.literal(true, { errorMap: () => ({ message: "Необходимо согласие" }) }),
}).refine((data) => data.password === data.passwordConfirm, {
  message: "Пароли не совпадают",
  path: ["passwordConfirm"],
});

type SignupValues = z.infer<typeof SignupSchema>;
type SignupErrors = Partial<Record<keyof SignupValues, string>>;

type SubmitState =
  | { status: "idle" }
  | { status: "submitting" }
  | { status: "success"; userId: number }
  | { status: "error"; message: string };

// Эмуляция проверки занятости username
const checkUsername = async (username: string): Promise<boolean> => {
  await new Promise((r) => setTimeout(r, 500));
  return !["admin", "root", "test"].includes(username.toLowerCase());
};

const SignupForm: Component = () => {
  const [values, setValues] = createStore<SignupValues>({
    username: "",
    email: "",
    password: "",
    passwordConfirm: "",
    age: 18,
    country: "UA",
    agreed: false as true,
  });
  
  const [errors, setErrors] = createStore<SignupErrors>({});
  const [touched, setTouched] = createStore<Record<keyof SignupValues, boolean>>({} as any);
  const [submitState, setSubmitState] = createSignal<SubmitState>({ status: "idle" });
  
  const [usernameStatus, setUsernameStatus] = createSignal<
    "idle" | "checking" | "available" | "taken"
  >("idle");
  
  // Сила пароля
  const passwordStrength = createMemo(() => {
    const p = values.password;
    let score = 0;
    if (p.length >= 8) score++;
    if (/[A-Z]/.test(p)) score++;
    if (/[0-9]/.test(p)) score++;
    if (/[^a-zA-Z0-9]/.test(p)) score++;
    if (p.length >= 12) score++;
    return score;
  });
  
  const passwordStrengthLabel = () => {
    const s = passwordStrength();
    if (s <= 1) return { label: "Слабый", color: "bg-red-500" };
    if (s <= 3) return { label: "Средний", color: "bg-yellow-500" };
    return { label: "Сильный", color: "bg-green-500" };
  };
  
  // Дебаунсная проверка username
  let usernameCheckTimer: number | undefined;
  const onUsernameInput = (val: string) => {
    setValues("username", val);
    setUsernameStatus("idle");
    
    if (val.length < 3) return;
    
    clearTimeout(usernameCheckTimer);
    usernameCheckTimer = window.setTimeout(async () => {
      setUsernameStatus("checking");
      const available = await checkUsername(val);
      setUsernameStatus(available ? "available" : "taken");
    }, 500);
  };
  
  const validate = (): boolean => {
    const result = SignupSchema.safeParse(values);
    if (result.success) {
      setErrors({});
      return true;
    }
    const fieldErrors: SignupErrors = {};
    for (const issue of result.error.issues) {
      const field = issue.path[0] as keyof SignupValues;
      if (!fieldErrors[field]) fieldErrors[field] = issue.message;
    }
    setErrors(fieldErrors);
    return false;
  };
  
  const handleBlur = (field: keyof SignupValues) => {
    setTouched(field, true);
    validate();
  };
  
  const handleSubmit = async (e: SubmitEvent) => {
    e.preventDefault();
    
    // Помечаем все как touched
    const allTouched = Object.keys(values).reduce(
      (acc, k) => ({ ...acc, [k]: true }),
      {} as Record<keyof SignupValues, boolean>
    );
    setTouched(allTouched);
    
    if (!validate()) return;
    if (usernameStatus() === "taken") return;
    
    setSubmitState({ status: "submitting" });
    
    try {
      await new Promise((r) => setTimeout(r, 1000));
      setSubmitState({ status: "success", userId: Math.floor(Math.random() * 1000) });
    } catch (err) {
      setSubmitState({
        status: "error",
        message: (err as Error).message,
      });
    }
  };
  
  const showError = (field: keyof SignupValues) => touched[field] && errors[field];
  
  return (
    <Switch>
      <Match when={submitState().status === "success"}>
        {(_) => {
          const s = submitState();
          if (s.status !== "success") return null;
          return (
            <div class="max-w-md mx-auto p-8 text-center">
              <div class="text-6xl mb-4">✅</div>
              <h2 class="text-2xl font-bold">Регистрация успешна!</h2>
              <p class="text-gray-600 mt-2">Ваш ID: {s.userId}</p>
            </div>
          );
        }}
      </Match>
      
      <Match when={submitState().status !== "success"}>
        <form onSubmit={handleSubmit} class="max-w-md mx-auto p-6 space-y-4">
          <h1 class="text-2xl font-bold">Регистрация</h1>
          
          {/* Username с асинхронной проверкой */}
          <div>
            <label class="block text-sm font-medium mb-1">Имя пользователя</label>
            <div class="relative">
              <input
                value={values.username}
                onInput={(e) => onUsernameInput(e.currentTarget.value)}
                onBlur={() => handleBlur("username")}
                class={`w-full border rounded px-3 py-2 ${
                  showError("username") || usernameStatus() === "taken"
                    ? "border-red-500"
                    : usernameStatus() === "available"
                    ? "border-green-500"
                    : ""
                }`}
              />
              <div class="absolute right-3 top-2.5 text-sm">
                <Switch>
                  <Match when={usernameStatus() === "checking"}>
                    <div class="w-4 h-4 border-2 border-blue-500 border-t-transparent rounded-full animate-spin" />
                  </Match>
                  <Match when={usernameStatus() === "available"}>
                    <span class="text-green-500">✓</span>
                  </Match>
                  <Match when={usernameStatus() === "taken"}>
                    <span class="text-red-500">✗</span>
                  </Match>
                </Switch>
              </div>
            </div>
            <Show when={showError("username")}>
              <p class="text-red-500 text-sm mt-1">{errors.username}</p>
            </Show>
            <Show when={usernameStatus() === "taken"}>
              <p class="text-red-500 text-sm mt-1">Имя занято</p>
            </Show>
          </div>
          
          {/* Email */}
          <div>
            <label class="block text-sm font-medium mb-1">Email</label>
            <input
              type="email"
              value={values.email}
              onInput={(e) => setValues("email", e.currentTarget.value)}
              onBlur={() => handleBlur("email")}
              class={`w-full border rounded px-3 py-2 ${
                showError("email") ? "border-red-500" : ""
              }`}
            />
            <Show when={showError("email")}>
              <p class="text-red-500 text-sm mt-1">{errors.email}</p>
            </Show>
          </div>
          
          {/* Password с индикатором силы */}
          <div>
            <label class="block text-sm font-medium mb-1">Пароль</label>
            <input
              type="password"
              value={values.password}
              onInput={(e) => setValues("password", e.currentTarget.value)}
              onBlur={() => handleBlur("password")}
              class={`w-full border rounded px-3 py-2 ${
                showError("password") ? "border-red-500" : ""
              }`}
            />
            <Show when={values.password}>
              <div class="mt-2">
                <div class="flex gap-1">
                  <For each={[1, 2, 3, 4, 5]}>
                    {(i) => (
                      <div
                        class={`h-1 flex-1 rounded ${
                          passwordStrength() >= i
                            ? passwordStrengthLabel().color
                            : "bg-gray-200"
                        }`}
                      />
                    )}
                  </For>
                </div>
                <p class="text-xs text-gray-600 mt-1">
                  {passwordStrengthLabel().label}
                </p>
              </div>
            </Show>
            <Show when={showError("password")}>
              <p class="text-red-500 text-sm mt-1">{errors.password}</p>
            </Show>
          </div>
          
          {/* Password confirm */}
          <div>
            <label class="block text-sm font-medium mb-1">Подтвердите пароль</label>
            <input
              type="password"
              value={values.passwordConfirm}
              onInput={(e) => setValues("passwordConfirm", e.currentTarget.value)}
              onBlur={() => handleBlur("passwordConfirm")}
              class={`w-full border rounded px-3 py-2 ${
                showError("passwordConfirm") ? "border-red-500" : ""
              }`}
            />
            <Show when={showError("passwordConfirm")}>
              <p class="text-red-500 text-sm mt-1">{errors.passwordConfirm}</p>
            </Show>
          </div>
          
          {/* Age */}
          <div>
            <label class="block text-sm font-medium mb-1">Возраст</label>
            <input
              type="number"
              value={values.age}
              onInput={(e) => setValues("age", Number(e.currentTarget.value))}
              onBlur={() => handleBlur("age")}
              class={`w-full border rounded px-3 py-2 ${
                showError("age") ? "border-red-500" : ""
              }`}
            />
            <Show when={showError("age")}>
              <p class="text-red-500 text-sm mt-1">{errors.age}</p>
            </Show>
          </div>
          
          {/* Country */}
          <div>
            <label class="block text-sm font-medium mb-1">Страна</label>
            <select
              value={values.country}
              onChange={(e) => setValues("country", e.currentTarget.value as any)}
              class="w-full border rounded px-3 py-2"
            >
              <option value="UA">Украина</option>
              <option value="PL">Польша</option>
              <option value="DE">Германия</option>
              <option value="US">США</option>
            </select>
          </div>
          
          {/* Agreement */}
          <div>
            <label class="flex items-center gap-2">
              <input
                type="checkbox"
                checked={values.agreed}
                onChange={(e) => {
                  setValues("agreed", e.currentTarget.checked as true);
                  setTouched("agreed", true);
                }}
              />
              <span class="text-sm">Соглашаюсь с условиями</span>
            </label>
            <Show when={showError("agreed")}>
              <p class="text-red-500 text-sm mt-1">{errors.agreed}</p>
            </Show>
          </div>
          
          {/* Submit */}
          <button
            type="submit"
            disabled={submitState().status === "submitting"}
            class="w-full bg-blue-500 text-white py-2 rounded disabled:opacity-50"
          >
            {submitState().status === "submitting" ? "Регистрация..." : "Зарегистрироваться"}
          </button>
          
          <Show when={submitState().status === "error"}>
            {(_) => {
              const s = submitState();
              if (s.status !== "error") return null;
              return (
                <p class="text-red-500 text-sm text-center">{s.message}</p>
              );
            }}
          </Show>
        </form>
      </Match>
    </Switch>
  );
};

export default SignupForm;
```

### Что важно понять

1. **`createStore` для values + отдельный для errors и touched** — три параллельных среза состояния
2. **`touched` показывает ошибки только после взаимодействия** — UX-паттерн, не пугать пользователя сразу
3. **`createMemo` для производных** — сила пароля автоматически обновляется
4. **Дебаунс асинхронной проверки** — обычный JS `setTimeout`, ничего реактивного не нужно
5. **Zod refine для cross-field валидации** — пароли совпадают только в схеме
6. **Submit state как union** — невозможно представить "submitting + success" одновременно

---
---
---

# Часть XII — Работа с DOM и интеграции (НОВАЯ)

## 64. Refs и DOM API

В Части IV мы видели базовое использование refs. Здесь — продвинутые сценарии.

### Измерение размеров

```tsx
const Component: Component = () => {
  let ref!: HTMLDivElement;
  const [size, setSize] = createSignal({ width: 0, height: 0 });
  
  onMount(() => {
    setSize({ width: ref.offsetWidth, height: ref.offsetHeight });
  });
  
  return <div ref={ref}>Размер: {size().width} x {size().height}</div>;
};
```

### ResizeObserver — следить за изменениями размера

```tsx
const Component: Component = () => {
  let ref!: HTMLDivElement;
  const [width, setWidth] = createSignal(0);
  
  onMount(() => {
    const observer = new ResizeObserver((entries) => {
      const entry = entries[0];
      setWidth(entry.contentRect.width);
    });
    
    observer.observe(ref);
    onCleanup(() => observer.disconnect());
  });
  
  return <div ref={ref}>Ширина: {width()}px</div>;
};
```

### MutationObserver — следить за изменениями DOM

```tsx
let ref!: HTMLDivElement;

onMount(() => {
  const observer = new MutationObserver((mutations) => {
    for (const m of mutations) {
      console.log("Изменение:", m.type, m.target);
    }
  });
  
  observer.observe(ref, {
    childList: true,    // добавление/удаление детей
    subtree: true,       // и вложенных
    attributes: true,    // атрибуты
    characterData: true, // текст
  });
  
  onCleanup(() => observer.disconnect());
});
```

### IntersectionObserver — видимость элемента

Использовали в примере infinite scroll. Другие применения:

```tsx
// Lazy loading изображений
let imgRef!: HTMLImageElement;
const [src, setSrc] = createSignal<string | undefined>();

onMount(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      if (entries[0].isIntersecting) {
        setSrc(imgRef.dataset.src);
        observer.disconnect();
      }
    },
    { rootMargin: "100px" }
  );
  
  observer.observe(imgRef);
  onCleanup(() => observer.disconnect());
});

<img ref={imgRef} data-src="/large-image.jpg" src={src()} />
```

### Scroll и положение

```tsx
let ref!: HTMLDivElement;

const scrollToElement = () => {
  ref.scrollIntoView({ behavior: "smooth", block: "start" });
};

// Получить положение в viewport
const getPosition = () => {
  const rect = ref.getBoundingClientRect();
  return { top: rect.top, left: rect.left };
};

// Скролл к началу
const scrollToTop = () => {
  ref.scrollTo({ top: 0, behavior: "smooth" });
};
```

### Фокус-менеджмент

```tsx
const FocusManager: Component = () => {
  let firstRef!: HTMLInputElement;
  let secondRef!: HTMLInputElement;
  
  onMount(() => firstRef.focus());
  
  return (
    <>
      <input
        ref={firstRef}
        onKeyDown={(e) => {
          if (e.key === "Enter") {
            e.preventDefault();
            secondRef.focus();
          }
        }}
      />
      <input ref={secondRef} />
    </>
  );
};
```

---

## 65. События окна и документа

В SolidJS события на конкретных элементах работают через JSX (`onClick`, `onInput`). Глобальные события — через `addEventListener` в `onMount` + `onCleanup`.

### Window events

```tsx
const useWindowScroll = () => {
  const [scrollY, setScrollY] = createSignal(0);
  
  onMount(() => {
    const handler = () => setScrollY(window.scrollY);
    window.addEventListener("scroll", handler, { passive: true });
    onCleanup(() => window.removeEventListener("scroll", handler));
  });
  
  return scrollY;
};

const Component: Component = () => {
  const scrollY = useWindowScroll();
  return <div>Прокрутка: {scrollY()}px</div>;
};
```

### Размер окна

```tsx
const useWindowSize = () => {
  const [size, setSize] = createSignal({
    width: window.innerWidth,
    height: window.innerHeight,
  });
  
  onMount(() => {
    const handler = () => setSize({
      width: window.innerWidth,
      height: window.innerHeight,
    });
    window.addEventListener("resize", handler);
    onCleanup(() => window.removeEventListener("resize", handler));
  });
  
  return size;
};
```

### Клавиатурные шорткаты

```tsx
const useKeyboard = (key: string, handler: () => void, options?: { ctrl?: boolean }) => {
  onMount(() => {
    const fn = (e: KeyboardEvent) => {
      if (e.key === key && (!options?.ctrl || e.ctrlKey || e.metaKey)) {
        e.preventDefault();
        handler();
      }
    };
    document.addEventListener("keydown", fn);
    onCleanup(() => document.removeEventListener("keydown", fn));
  });
};

// Использование
useKeyboard("k", () => openSearch(), { ctrl: true }); // Ctrl+K
useKeyboard("Escape", () => closeModal());
```

### Click outside

Часто нужно — клик за пределами элемента (закрыть dropdown, popup):

```tsx
const useClickOutside = (ref: () => HTMLElement | undefined, handler: () => void) => {
  onMount(() => {
    const fn = (e: MouseEvent) => {
      const el = ref();
      if (el && !el.contains(e.target as Node)) {
        handler();
      }
    };
    document.addEventListener("mousedown", fn);
    onCleanup(() => document.removeEventListener("mousedown", fn));
  });
};

const Dropdown: Component = () => {
  let ref!: HTMLDivElement;
  const [open, setOpen] = createSignal(false);
  
  useClickOutside(() => ref, () => setOpen(false));
  
  return (
    <div ref={ref}>
      <button onClick={() => setOpen(!open())}>Меню</button>
      <Show when={open()}>
        <div class="dropdown-menu">...</div>
      </Show>
    </div>
  );
};
```

### Visibility API

Знать когда вкладка не активна:

```tsx
const useDocumentVisibility = () => {
  const [visible, setVisible] = createSignal(!document.hidden);
  
  onMount(() => {
    const handler = () => setVisible(!document.hidden);
    document.addEventListener("visibilitychange", handler);
    onCleanup(() => document.removeEventListener("visibilitychange", handler));
  });
  
  return visible;
};

// Пауза в видеоплеере когда вкладка скрыта
createEffect(() => {
  if (!isVisible()) {
    videoRef.pause();
  }
});
```

---

## 66. Анимации через CSS и Web Animations API

### CSS анимации через классы

Самый простой и производительный способ:

```tsx
const [isOpen, setIsOpen] = createSignal(false);

<div
  class="transition-all duration-300"
  classList={{
    "opacity-0 -translate-y-2": !isOpen(),
    "opacity-100 translate-y-0": isOpen(),
  }}
>
  Контент
</div>
```

### CSS Transitions при появлении/исчезновении

Проблема — `<Show>` сразу убирает элемент из DOM, transition не успевает. Решение — Solid Transition Group:

```bash
pnpm add solid-transition-group
```

```tsx
import { Transition } from "solid-transition-group";

<Transition
  name="fade"
  onEnter={(el, done) => {
    const a = el.animate(
      [{ opacity: 0 }, { opacity: 1 }],
      { duration: 300, easing: "ease-out" }
    );
    a.finished.then(done);
  }}
  onExit={(el, done) => {
    const a = el.animate(
      [{ opacity: 1 }, { opacity: 0 }],
      { duration: 200 }
    );
    a.finished.then(done);
  }}
>
  <Show when={isVisible()}>
    <div>Анимируемый контент</div>
  </Show>
</Transition>
```

### Web Animations API напрямую

```tsx
let ref!: HTMLDivElement;

const animate = () => {
  ref.animate(
    [
      { transform: "translateX(0px)" },
      { transform: "translateX(100px)" },
      { transform: "translateX(0px)" },
    ],
    {
      duration: 1000,
      easing: "ease-in-out",
      iterations: 1,
    }
  );
};

return (
  <div>
    <div ref={ref} class="w-20 h-20 bg-blue-500" />
    <button onClick={animate}>Анимация</button>
  </div>
);
```

### requestAnimationFrame для непрерывных анимаций

```tsx
const [angle, setAngle] = createSignal(0);

onMount(() => {
  let frameId: number;
  let lastTime = performance.now();
  
  const tick = (time: number) => {
    const delta = time - lastTime;
    lastTime = time;
    setAngle((a) => (a + delta * 0.05) % 360);
    frameId = requestAnimationFrame(tick);
  };
  
  frameId = requestAnimationFrame(tick);
  onCleanup(() => cancelAnimationFrame(frameId));
});

<div style={{ transform: `rotate(${angle()}deg)` }} class="w-20 h-20 bg-blue-500" />
```

---

## 67. Интеграция с Canvas

Canvas — низкоуровневый API для 2D графики. SolidJS реактивность отлично с ним работает.

```tsx
const PaintCanvas: Component = () => {
  let canvasRef!: HTMLCanvasElement;
  const [color, setColor] = createSignal("#3b82f6");
  const [size, setSize] = createSignal(5);
  let isDrawing = false;
  let lastPos = { x: 0, y: 0 };
  
  onMount(() => {
    const ctx = canvasRef.getContext("2d")!;
    
    canvasRef.width = 800;
    canvasRef.height = 600;
    ctx.fillStyle = "white";
    ctx.fillRect(0, 0, canvasRef.width, canvasRef.height);
    
    const getPos = (e: MouseEvent) => {
      const rect = canvasRef.getBoundingClientRect();
      return {
        x: e.clientX - rect.left,
        y: e.clientY - rect.top,
      };
    };
    
    const handleMouseDown = (e: MouseEvent) => {
      isDrawing = true;
      lastPos = getPos(e);
    };
    
    const handleMouseMove = (e: MouseEvent) => {
      if (!isDrawing) return;
      const pos = getPos(e);
      ctx.strokeStyle = color();
      ctx.lineWidth = size();
      ctx.lineCap = "round";
      ctx.beginPath();
      ctx.moveTo(lastPos.x, lastPos.y);
      ctx.lineTo(pos.x, pos.y);
      ctx.stroke();
      lastPos = pos;
    };
    
    const handleMouseUp = () => {
      isDrawing = false;
    };
    
    canvasRef.addEventListener("mousedown", handleMouseDown);
    canvasRef.addEventListener("mousemove", handleMouseMove);
    canvasRef.addEventListener("mouseup", handleMouseUp);
    canvasRef.addEventListener("mouseleave", handleMouseUp);
    
    onCleanup(() => {
      canvasRef.removeEventListener("mousedown", handleMouseDown);
      canvasRef.removeEventListener("mousemove", handleMouseMove);
      canvasRef.removeEventListener("mouseup", handleMouseUp);
      canvasRef.removeEventListener("mouseleave", handleMouseUp);
    });
  });
  
  const clear = () => {
    const ctx = canvasRef.getContext("2d")!;
    ctx.fillStyle = "white";
    ctx.fillRect(0, 0, canvasRef.width, canvasRef.height);
  };
  
  return (
    <div>
      <div class="flex gap-2 mb-2">
        <input type="color" value={color()} onInput={(e) => setColor(e.currentTarget.value)} />
        <input
          type="range"
          min="1"
          max="50"
          value={size()}
          onInput={(e) => setSize(Number(e.currentTarget.value))}
        />
        <button onClick={clear} class="px-3 py-1 bg-red-500 text-white rounded">
          Очистить
        </button>
      </div>
      <canvas ref={canvasRef} class="border" />
    </div>
  );
};
```

### Canvas + реактивная отрисовка

Если нужно перерисовывать при изменении данных:

```tsx
const Chart: Component<{ data: number[] }> = (props) => {
  let canvasRef!: HTMLCanvasElement;
  
  createEffect(() => {
    const ctx = canvasRef.getContext("2d")!;
    const data = props.data; // реактивная зависимость
    
    // Очищаем
    ctx.clearRect(0, 0, canvasRef.width, canvasRef.height);
    
    // Рисуем
    const max = Math.max(...data);
    const barWidth = canvasRef.width / data.length;
    
    ctx.fillStyle = "#3b82f6";
    data.forEach((value, i) => {
      const height = (value / max) * canvasRef.height;
      ctx.fillRect(i * barWidth, canvasRef.height - height, barWidth - 2, height);
    });
  });
  
  return <canvas ref={canvasRef} width={400} height={200} />;
};
```

`createEffect` пересоздаст рисунок при изменении `props.data`.

---

## 68. Интеграция с не-Solid библиотеками

Многие библиотеки манипулируют DOM напрямую (Chart.js, Three.js, GSAP, Leaflet). SolidJS отлично с ними работает.

### Chart.js

```bash
pnpm add chart.js
```

```tsx
import Chart from "chart.js/auto";
import { Component, onMount, onCleanup, createEffect } from "solid-js";

interface ChartProps {
  data: { labels: string[]; values: number[] };
}

const LineChart: Component<ChartProps> = (props) => {
  let canvasRef!: HTMLCanvasElement;
  let chart: Chart | null = null;
  
  onMount(() => {
    chart = new Chart(canvasRef, {
      type: "line",
      data: {
        labels: props.data.labels,
        datasets: [{ label: "Данные", data: props.data.values, borderColor: "#3b82f6" }],
      },
    });
    
    onCleanup(() => chart?.destroy());
  });
  
  // Обновлять график при изменении данных
  createEffect(() => {
    if (!chart) return;
    chart.data.labels = props.data.labels;
    chart.data.datasets[0].data = props.data.values;
    chart.update();
  });
  
  return <canvas ref={canvasRef} />;
};
```

### Three.js

```tsx
import * as THREE from "three";

const Scene: Component = () => {
  let containerRef!: HTMLDivElement;
  
  onMount(() => {
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(75, 1, 0.1, 1000);
    const renderer = new THREE.WebGLRenderer({ antialias: true });
    renderer.setSize(400, 400);
    containerRef.appendChild(renderer.domElement);
    
    const geometry = new THREE.BoxGeometry();
    const material = new THREE.MeshBasicMaterial({ color: 0x3b82f6 });
    const cube = new THREE.Mesh(geometry, material);
    scene.add(cube);
    camera.position.z = 5;
    
    let frameId: number;
    const animate = () => {
      cube.rotation.x += 0.01;
      cube.rotation.y += 0.01;
      renderer.render(scene, camera);
      frameId = requestAnimationFrame(animate);
    };
    animate();
    
    onCleanup(() => {
      cancelAnimationFrame(frameId);
      renderer.dispose();
      geometry.dispose();
      material.dispose();
      containerRef.removeChild(renderer.domElement);
    });
  });
  
  return <div ref={containerRef} />;
};
```

### Leaflet (карты)

```tsx
import L from "leaflet";

interface MapProps {
  center: [number, number];
  zoom: number;
  markers?: { position: [number, number]; popup: string }[];
}

const Map: Component<MapProps> = (props) => {
  let mapRef!: HTMLDivElement;
  let map: L.Map | null = null;
  let markerLayer: L.LayerGroup | null = null;
  
  onMount(() => {
    map = L.map(mapRef).setView(props.center, props.zoom);
    L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png").addTo(map);
    markerLayer = L.layerGroup().addTo(map);
    
    onCleanup(() => map?.remove());
  });
  
  // Реакция на изменение маркеров
  createEffect(() => {
    if (!map || !markerLayer) return;
    markerLayer.clearLayers();
    
    for (const m of props.markers ?? []) {
      L.marker(m.position).bindPopup(m.popup).addTo(markerLayer);
    }
  });
  
  // Реакция на изменение центра
  createEffect(() => {
    map?.setView(props.center, props.zoom);
  });
  
  return <div ref={mapRef} class="w-full h-96" />;
};
```

### Общий паттерн интеграции

1. **`onMount`** — инициализация библиотеки, создание объектов
2. **`createEffect`** — обновление при изменении props
3. **`onCleanup`** — освобождение ресурсов (destroy, remove, dispose)

---

## 69. 🛠 Практика: drag-and-drop без библиотек

В разделе 42 был Kanban через HTML5 Drag API. Здесь — drag через mouse events, дающий больше контроля.

```tsx
import { Component, createSignal, onCleanup, For } from "solid-js";
import { createStore, produce } from "solid-js/store";

interface Item {
  id: string;
  text: string;
}

interface DragState {
  items: Item[];
  draggedIndex: number | null;
  draggedY: number;
  dragOffset: number;
  hoveredIndex: number | null;
}

const ITEM_HEIGHT = 60;

const SortableList: Component = () => {
  const [state, setState] = createStore<DragState>({
    items: Array.from({ length: 8 }, (_, i) => ({
      id: String(i),
      text: `Элемент ${i + 1}`,
    })),
    draggedIndex: null,
    draggedY: 0,
    dragOffset: 0,
    hoveredIndex: null,
  });
  
  let listRef!: HTMLUListElement;
  
  const startDrag = (e: MouseEvent, index: number) => {
    e.preventDefault();
    const target = e.currentTarget as HTMLLIElement;
    const rect = target.getBoundingClientRect();
    
    setState({
      draggedIndex: index,
      draggedY: e.clientY,
      dragOffset: e.clientY - rect.top,
      hoveredIndex: index,
    });
    
    const handleMove = (e: MouseEvent) => {
      const listRect = listRef.getBoundingClientRect();
      const relativeY = e.clientY - listRect.top - state.dragOffset;
      const hoveredIdx = Math.max(
        0,
        Math.min(
          state.items.length - 1,
          Math.floor((e.clientY - listRect.top) / ITEM_HEIGHT)
        )
      );
      
      setState({
        draggedY: relativeY,
        hoveredIndex: hoveredIdx,
      });
    };
    
    const handleUp = () => {
      // Применяем перестановку
      if (state.draggedIndex !== null && state.hoveredIndex !== null) {
        const from = state.draggedIndex;
        const to = state.hoveredIndex;
        if (from !== to) {
          setState(
            produce((s) => {
              const [moved] = s.items.splice(from, 1);
              s.items.splice(to, 0, moved);
            })
          );
        }
      }
      
      setState({
        draggedIndex: null,
        hoveredIndex: null,
        draggedY: 0,
        dragOffset: 0,
      });
      
      document.removeEventListener("mousemove", handleMove);
      document.removeEventListener("mouseup", handleUp);
    };
    
    document.addEventListener("mousemove", handleMove);
    document.addEventListener("mouseup", handleUp);
    
    onCleanup(() => {
      document.removeEventListener("mousemove", handleMove);
      document.removeEventListener("mouseup", handleUp);
    });
  };
  
  // Получить трансформацию для элемента
  const getTransform = (index: number): string => {
    const dragged = state.draggedIndex;
    const hovered = state.hoveredIndex;
    
    if (dragged === null || hovered === null) return "translateY(0)";
    if (index === dragged) return ""; // у dragged своя логика
    
    // Если dragged движется вниз, элементы между dragged и hovered смещаются вверх
    if (dragged < hovered && index > dragged && index <= hovered) {
      return `translateY(-${ITEM_HEIGHT}px)`;
    }
    // Если dragged движется вверх, элементы между hovered и dragged смещаются вниз
    if (dragged > hovered && index < dragged && index >= hovered) {
      return `translateY(${ITEM_HEIGHT}px)`;
    }
    return "translateY(0)";
  };
  
  return (
    <div class="max-w-md mx-auto p-4">
      <h2 class="text-lg font-bold mb-3">Перетаскивай элементы:</h2>
      <ul
        ref={listRef}
        class="relative"
        style={{ height: `${state.items.length * ITEM_HEIGHT}px` }}
      >
        <For each={state.items}>
          {(item, index) => (
            <li
              onMouseDown={(e) => startDrag(e, index())}
              class={`absolute left-0 right-0 px-4 py-3 bg-white border rounded shadow-sm cursor-grab select-none ${
                state.draggedIndex === index()
                  ? "z-10 shadow-lg cursor-grabbing"
                  : "transition-transform duration-200"
              }`}
              style={
                state.draggedIndex === index()
                  ? {
                      top: `${state.draggedY}px`,
                      "z-index": 10,
                    }
                  : {
                      top: `${index() * ITEM_HEIGHT}px`,
                      transform: getTransform(index()),
                    }
              }
            >
              <span class="text-gray-400 mr-2">⋮⋮</span>
              {item.text}
            </li>
          )}
        </For>
      </ul>
    </div>
  );
};

export default SortableList;
```

### Что важно понять

1. **Mouse events на document, не на элементе** — пользователь может вывести мышь за пределы элемента, мы не теряем drag
2. **Absolute positioning + transform** — это даёт плавное движение остальных элементов
3. **`onCleanup`** — обязательно снимаем listeners если компонент размонтируется во время drag
4. **Хитрая логика `getTransform`** — рассчитываем сдвиг каждого элемента в зависимости от позиции dragged и hovered
5. **Без HTML5 Drag API** — больше контроля, кастомные эффекты, работает одинаково на любых элементах

В production такие штуки обычно берут готовые: `@thisbeyond/solid-dnd` или `solid-sortable`. Но понимать как это устроено — полезно.

---
---

# Часть XIII — TypeScript глубоко (ПЕРЕРАБОТАНО)

В Части II мы прошли основы. Здесь — продвинутые темы важные именно для SolidJS.

## 70. Дискриминированные unions для состояний

Это самый мощный паттерн в TS. Мы видели его в разделе 33 (UI states) и 60 (форма submit). Здесь — углублённый разбор.

### Проблема которую решает

Без дискриминированных unions UI-состояния представляют через несколько булевых флагов:

```tsx
// ❌ Плохо — невозможные комбинации возможны
const [isLoading, setIsLoading] = createSignal(false);
const [hasError, setHasError] = createSignal(false);
const [data, setData] = createSignal<User | null>(null);
const [errorMessage, setErrorMessage] = createSignal("");

// Возможные баги:
// isLoading=true + hasError=true?
// data!=null + hasError=true?
// errorMessage="" + hasError=true?
```

### Решение

```tsx
// ✅ Только валидные состояния
type FetchState<T> =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: T }
  | { status: "error"; error: string };

const [state, setState] = createSignal<FetchState<User>>({ status: "idle" });
```

### Сужение типа через свойство-дискриминатор

```tsx
const renderUser = (state: FetchState<User>) => {
  switch (state.status) {
    case "idle":
      return "Не начато";
    case "loading":
      return "Загрузка...";
    case "success":
      return state.data.name;  // ✅ TS знает что data есть
    case "error":
      return state.error;       // ✅ TS знает что error есть
  }
};
```

TS гарантирует на этапе компиляции что:
- `state.data` нельзя прочитать пока ты не проверил `status === "success"`
- Все случаи обработаны (если добавишь новый — TS выдаст ошибку про exhaustiveness)

### Exhaustiveness checking

Заставить компилятор проверить что все случаи обработаны:

```tsx
const exhaustive = (x: never): never => {
  throw new Error("Не должно произойти: " + JSON.stringify(x));
};

const render = (state: FetchState<User>) => {
  switch (state.status) {
    case "idle": return "Idle";
    case "loading": return "Loading";
    case "success": return state.data.name;
    case "error": return state.error;
    default:
      return exhaustive(state); // ❌ Ошибка компиляции если добавил новый статус и забыл здесь
  }
};
```

### Машины состояний

Дискриминированные unions особенно хороши для state machines:

```tsx
type AuthState =
  | { state: "unauthenticated" }
  | { state: "authenticating"; email: string }
  | { state: "authenticated"; user: User; token: string }
  | { state: "error"; previousState: AuthState; reason: string };

// Переходы только между валидными состояниями
const login = async (email: string, password: string, current: AuthState) => {
  if (current.state !== "unauthenticated") return;
  
  setAuth({ state: "authenticating", email });
  
  try {
    const { user, token } = await authApi.login(email, password);
    setAuth({ state: "authenticated", user, token });
  } catch (err) {
    setAuth({
      state: "error",
      previousState: current,
      reason: (err as Error).message,
    });
  }
};
```

### Reducer паттерн с union actions

```tsx
type CartAction =
  | { type: "add"; item: Product }
  | { type: "remove"; id: number }
  | { type: "updateQuantity"; id: number; quantity: number }
  | { type: "clear" };

interface CartState {
  items: { product: Product; quantity: number }[];
}

const reduce = (state: CartState, action: CartAction): CartState => {
  switch (action.type) {
    case "add":
      return { items: [...state.items, { product: action.item, quantity: 1 }] };
    case "remove":
      return { items: state.items.filter((i) => i.product.id !== action.id) };
    case "updateQuantity":
      return {
        items: state.items.map((i) =>
          i.product.id === action.id ? { ...i, quantity: action.quantity } : i
        ),
      };
    case "clear":
      return { items: [] };
  }
};
```

---

## 71. Типизация props.children как функции

В SolidJS компоненты управления потоком (`<Show>`, `<For>`, `<Index>`) используют children как функции:

```tsx
<Show when={user()}>
  {(user) => <p>{user().name}</p>}  // children — функция
</Show>

<For each={items()}>
  {(item, index) => <div>{item.name}</div>}  // children — функция
</For>
```

Как написать свой компонент с таким API?

### FlowComponent

```tsx
import { FlowComponent } from "solid-js";

interface MyComponentProps<T> {
  items: T[];
}

const MyComponent = <T,>(
  props: MyComponentProps<T> & { children: (item: T, index: number) => JSX.Element }
) => {
  return (
    <div>
      <For each={props.items}>
        {(item, idx) => props.children(item, idx())}
      </For>
    </div>
  );
};

// Использование
<MyComponent items={users()}>
  {(user, i) => <UserCard user={user} index={i} />}
</MyComponent>
```

### С реактивным аргументом (как у Show)

```tsx
interface MyShowProps<T> {
  when: T | null | undefined | false;
  children: JSX.Element | ((value: Accessor<T>) => JSX.Element);
}

const MyShow = <T,>(props: MyShowProps<T>) => {
  return (
    <Show when={props.when}>
      {typeof props.children === "function"
        ? (props.children as Function)(() => props.when)
        : props.children}
    </Show>
  );
};
```

### Render prop паттерн

```tsx
interface ToggleProps {
  defaultOpen?: boolean;
  children: (state: {
    open: Accessor<boolean>;
    toggle: () => void;
    setOpen: (v: boolean) => void;
  }) => JSX.Element;
}

const Toggle: Component<ToggleProps> = (props) => {
  const [open, setOpen] = createSignal(props.defaultOpen ?? false);
  const toggle = () => setOpen(!open());
  
  return <>{props.children({ open, toggle, setOpen })}</>;
};

// Использование
<Toggle defaultOpen>
  {({ open, toggle }) => (
    <>
      <button onClick={toggle}>{open() ? "Свернуть" : "Развернуть"}</button>
      <Show when={open()}>
        <div>Контент</div>
      </Show>
    </>
  )}
</Toggle>
```

---

## 72. Generic components — все способы

Generic компоненты — компоненты которые работают с разными типами данных.

### Способ 1: arrow function с trailing comma

```tsx
const Select = <T,>(props: {
  options: T[];
  value: T;
  onChange: (value: T) => void;
  getLabel: (item: T) => string;
}) => {
  return (
    <select
      onChange={(e) => {
        const idx = Number(e.currentTarget.value);
        props.onChange(props.options[idx]);
      }}
    >
      <For each={props.options}>
        {(option, i) => (
          <option value={i()} selected={option === props.value}>
            {props.getLabel(option)}
          </option>
        )}
      </For>
    </select>
  );
};
```

Запятая в `<T,>` нужна потому что без неё JSX парсер думает что это начало тега `<T>`.

### Способ 2: function declaration

```tsx
function Select<T>(props: {
  options: T[];
  value: T;
  onChange: (value: T) => void;
  getLabel: (item: T) => string;
}) {
  return <select>...</select>;
}
```

Менее распространено в SolidJS, но работает.

### Способ 3: T extends unknown (если не хочешь запятую)

```tsx
const Select = <T extends unknown>(props: { /* ... */ }) => {
  return <select>...</select>;
};
```

### Использование

```tsx
interface User {
  id: number;
  name: string;
}

<Select<User>
  options={users()}
  value={selectedUser()}
  onChange={setSelectedUser}
  getLabel={(u) => u.name}
/>

// Или без явного указания типа — выводится из options
<Select
  options={[1, 2, 3]}
  value={selectedNumber()}
  onChange={setSelectedNumber}
  getLabel={(n) => String(n)}
/>
```

### С ограничениями

```tsx
interface HasId {
  id: number | string;
}

const List = <T extends HasId>(props: {
  items: T[];
  renderItem: (item: T) => JSX.Element;
}) => {
  return (
    <For each={props.items}>
      {(item) => <div data-id={item.id}>{props.renderItem(item)}</div>}
    </For>
  );
};
```

---

## 73. Типизация custom directives

Custom directives — это `use:directiveName` атрибуты. Чтобы TS знал о них, нужно расширить namespace JSX:

```tsx
// src/directives.ts
import { Accessor } from "solid-js";

// Сама директива
export const clickOutside = (
  el: HTMLElement,
  accessor: Accessor<() => void>
) => {
  const handler = (e: MouseEvent) => {
    if (!el.contains(e.target as Node)) {
      accessor()();
    }
  };
  document.addEventListener("click", handler);
  // SolidJS автоматически снимет при размонтировании
};

// Расширяем JSX
declare module "solid-js" {
  namespace JSX {
    interface Directives {
      clickOutside: () => void;
    }
  }
}
```

```tsx
// Использование
import { clickOutside } from "./directives";
clickOutside; // ← важно: импорт должен быть использован, иначе bundler уберёт

const Dropdown: Component = () => {
  const [open, setOpen] = createSignal(false);
  
  return (
    <div use:clickOutside={() => setOpen(false)}>
      ...
    </div>
  );
};
```

### Зачем `clickOutside;` после импорта

SolidJS компилятор обрабатывает `use:` директивы через идентификатор в скоупе. Без явного использования импорта tree-shaking удалит его.

### Директива с typed аргументом

```tsx
interface AutoFocusOptions {
  delay?: number;
  select?: boolean;
}

export const autoFocus = (
  el: HTMLInputElement,
  accessor: Accessor<AutoFocusOptions | boolean>
) => {
  const opts = accessor();
  const config = typeof opts === "boolean" ? { delay: 0 } : opts;
  
  setTimeout(() => {
    el.focus();
    if (typeof opts !== "boolean" && opts.select) {
      el.select();
    }
  }, config.delay ?? 0);
};

declare module "solid-js" {
  namespace JSX {
    interface Directives {
      autoFocus: AutoFocusOptions | boolean;
    }
  }
}

// Использование
<input use:autoFocus={true} />
<input use:autoFocus={{ delay: 100, select: true }} />
```

### Ограничение по типу элемента

```tsx
declare module "solid-js" {
  namespace JSX {
    interface DirectiveFunctions {
      autoFocus: typeof autoFocus;
      // autoFocus работает только на HTMLInputElement
    }
  }
}
```

---

## 74. satisfies оператор для props

`satisfies` (TS 4.9+) полезен для типобезопасных конфигов:

```tsx
type ButtonVariant = "primary" | "secondary" | "danger";

// Без satisfies — мы либо теряем типы, либо ругаемся на присвоение
const variantClasses: Record<ButtonVariant, string> = {
  primary: "bg-blue-500 text-white",
  secondary: "bg-gray-200 text-gray-800",
  danger: "bg-red-500 text-white",
};

variantClasses.primary; // string — но мы знаем что это конкретная строка
```

С `satisfies`:

```tsx
const variantClasses = {
  primary: "bg-blue-500 text-white",
  secondary: "bg-gray-200 text-gray-800",
  danger: "bg-red-500 text-white",
} satisfies Record<ButtonVariant, string>;

// Тип проверен, но значения точные
variantClasses.primary; // "bg-blue-500 text-white" (literal)

// Опечатки ловятся:
const wrong = {
  primary: "...",
  secondary: "...",
  dangerr: "...", // ❌ Ошибка — лишний ключ
} satisfies Record<ButtonVariant, string>;
```

### Применение в компонентах

```tsx
const sizes = {
  sm: { padding: "px-2 py-1", text: "text-sm" },
  md: { padding: "px-3 py-2", text: "text-base" },
  lg: { padding: "px-4 py-3", text: "text-lg" },
} satisfies Record<string, { padding: string; text: string }>;

type Size = keyof typeof sizes;

const Button: Component<{ size: Size }> = (props) => {
  return (
    <button class={`${sizes[props.size].padding} ${sizes[props.size].text}`}>
      ...
    </button>
  );
};
```

### Конфигурация роутов

```tsx
const routes = {
  home: { path: "/", title: "Главная" },
  profile: { path: "/profile", title: "Профиль", auth: true },
  settings: { path: "/settings", title: "Настройки", auth: true },
} satisfies Record<string, { path: string; title: string; auth?: boolean }>;

// Точные пути сохранены:
routes.home.path; // тип "/"

type RouteKey = keyof typeof routes; // "home" | "profile" | "settings"
```

---

## 75. JSX типы и event handlers

### Базовые JSX типы

```tsx
import { JSX } from "solid-js";

// Тип JSX элемента
const element: JSX.Element = <div>Hello</div>;

// HTML атрибуты для элемента
type DivProps = JSX.HTMLAttributes<HTMLDivElement>;
type ButtonProps = JSX.ButtonHTMLAttributes<HTMLButtonElement>;
type InputProps = JSX.InputHTMLAttributes<HTMLInputElement>;
```

### Event handlers — типизация

В SolidJS все event handlers имеют типизированный `currentTarget`:

```tsx
// Готовые типы для handlers
const handleInput: JSX.EventHandler<HTMLInputElement, InputEvent> = (e) => {
  // e.currentTarget — HTMLInputElement, типизирован правильно
  console.log(e.currentTarget.value);
};

<input onInput={handleInput} />
```

### Inline handlers

```tsx
<input
  onInput={(e) => {
    e.currentTarget.value; // string, типизировано
  }}
/>

<button
  onClick={(e) => {
    e.currentTarget; // HTMLButtonElement
    e.target;        // EventTarget (более общий тип)
  }}
/>
```

### Все event handler типы

```tsx
import { JSX } from "solid-js";

JSX.EventHandler<HTMLInputElement, InputEvent>
JSX.ChangeEventHandler<HTMLInputElement, Event>
JSX.InputEventHandler<HTMLInputElement, InputEvent>
JSX.FocusEventHandler<HTMLInputElement, FocusEvent>
JSX.MouseEventHandler<HTMLButtonElement, MouseEvent>
JSX.KeyboardEventHandler<HTMLInputElement, KeyboardEvent>
JSX.SubmitEventHandler<HTMLFormElement, SubmitEvent>
```

### Расширение JSX типов

Например, для типизации `data-*` атрибутов:

```tsx
declare module "solid-js" {
  namespace JSX {
    interface HTMLAttributes<T> {
      "data-testid"?: string;
      "data-id"?: string | number;
    }
  }
}
```

---

## 76. Полиморфные компоненты (as prop)

Паттерн из Radix/Kobalte — позволяет указать какой HTML тег рендерить:

```tsx
import { JSX, ValidComponent, splitProps } from "solid-js";
import { Dynamic } from "solid-js/web";

type PolymorphicProps<T extends ValidComponent> = {
  as?: T;
  children?: JSX.Element;
} & Omit<JSX.HTMLAttributes<HTMLElement>, "children">;

const Button = <T extends ValidComponent = "button">(
  props: PolymorphicProps<T>
) => {
  const [local, others] = splitProps(props, ["as", "children"]);
  
  return (
    <Dynamic
      component={local.as ?? "button"}
      class="px-4 py-2 bg-blue-500 text-white rounded"
      {...others}
    >
      {local.children}
    </Dynamic>
  );
};

// Использование
<Button>По умолчанию это button</Button>
<Button as="a" href="/page">Это ссылка</Button>
<Button as="div" onClick={() => {}}>Это div</Button>
```

Полная типизация полиморфных компонентов — сложная задача. В Kobalte (см. раздел 113) это сделано хорошо — можешь подсмотреть подход.

### Простой вариант через type guard

```tsx
type ButtonProps = {
  variant?: "primary" | "secondary";
} & (
  | ({ as?: "button" } & JSX.ButtonHTMLAttributes<HTMLButtonElement>)
  | ({ as: "a" } & JSX.AnchorHTMLAttributes<HTMLAnchorElement>)
);

const Button: Component<ButtonProps> = (props) => {
  if (props.as === "a") {
    return <a {...props} class="...">{props.children}</a>;
  }
  return <button {...props} class="...">{props.children}</button>;
};
```

---
---
---

# Часть XIV — Продвинутые темы

## 77. SSR — Server-Side Rendering

SSR — рендер компонентов на сервере, отправка готового HTML клиенту. Преимущества:
- SEO (поисковики видят контент)
- Быстрее First Contentful Paint
- Работает с отключённым JS

В SolidJS SSR делают через SolidStart. Часть XIX этому посвящена. Здесь — обзор как это работает под капотом.

### renderToString

```tsx
import { renderToString } from "solid-js/web";

const html = renderToString(() => <App />);
// HTML строка которую отправляем клиенту
```

### renderToStream

Для streaming SSR — отправка по частям:

```tsx
import { renderToStream } from "solid-js/web";

renderToStream(() => <App />).pipeTo(response.body);
```

### Suspense на сервере

Async компоненты внутри `<Suspense>` отправляются streaming-ом — клиент видит fallback пока данные грузятся, потом получает реальный контент.

---

## 78. Hydration

Hydration — процесс "оживления" SSR HTML на клиенте. SolidJS прикрепляет event listeners к существующему DOM без перерендера.

```tsx
import { hydrate } from "solid-js/web";

hydrate(() => <App />, document.getElementById("root")!);
```

В отличие от React, hydration в Solid очень быстрый — компилятор знает где event listeners, не нужно пересоздавать DOM.

---

## 79. createComputed

Похож на `createEffect`, но запускается **синхронно**, во время обновления.

```ts
function createComputed<T>(fn: (prev: T) => T, value?: T): void;
```

### Чем отличается

- `createEffect` — запускается **после** рендера (асинхронно)
- `createComputed` — запускается **во время** рендера (синхронно)

### Когда использовать

Редко. Подходит когда нужно изменить сигналы по цепочке до того как DOM обновится:

```tsx
const [a, setA] = createSignal(0);
const [b, setB] = createSignal(0);

createComputed(() => {
  setB(a() * 2);
});

// При setA(5) — b сразу станет 10, до того как effects запустятся
```

В большинстве случаев используй `createMemo`. `createComputed` для редких низкоуровневых задач.

---

## 80. createRoot / runWithOwner / getOwner

`createRoot` создаёт отдельный реактивный контекст вне компонента.

### Зачем

Все реактивные примитивы должны находиться внутри `createRoot` или компонента. Иначе:
- Утечки памяти (нет owner для cleanup)
- Warning "computations created outside createRoot"

### Использование

```tsx
import { createRoot, createSignal, createEffect } from "solid-js";

// Создаём отдельную реактивную область
const dispose = createRoot((dispose) => {
  const [count, setCount] = createSignal(0);
  
  createEffect(() => {
    console.log(count());
  });
  
  setCount(1); // эффект сработает
  
  return dispose;
});

// Когда не нужно — освобождаем ресурсы
dispose();
```

### runWithOwner — запустить код в существующем owner

```tsx
import { getOwner, runWithOwner } from "solid-js";

const Component: Component = () => {
  const owner = getOwner();
  
  const handleAsync = async () => {
    const data = await fetchData();
    
    // Создание сигналов в async коде — нужен owner
    runWithOwner(owner, () => {
      const [signal] = createSignal(data);
      createEffect(() => console.log(signal()));
    });
  };
};
```

### Типичный сценарий — глобальные сторы

```tsx
// stores/global.ts
import { createRoot, createSignal } from "solid-js";

export const globalStore = createRoot(() => {
  const [user, setUser] = createSignal<User | null>(null);
  const [theme, setTheme] = createSignal<"light" | "dark">("light");
  
  return { user, setUser, theme, setTheme };
});

// Использование где угодно
import { globalStore } from "./stores/global";

const Header: Component = () => {
  return <div>{globalStore.user()?.name}</div>;
};
```

---

## 81. Custom directives (use:)

Видели типизацию в разделе 73. Теперь — практические примеры директив.

### clickOutside

```tsx
export const clickOutside = (
  el: HTMLElement,
  accessor: () => () => void
) => {
  const handler = (e: MouseEvent) => {
    if (!el.contains(e.target as Node)) {
      accessor()();
    }
  };
  document.addEventListener("click", handler);
  // Очистка автоматическая через onCleanup
};

// Использование
<div use:clickOutside={() => setOpen(false)}>...</div>
```

### autoFocus

```tsx
export const autoFocus = (el: HTMLElement) => {
  setTimeout(() => el.focus(), 0);
};

<input use:autoFocus />
```

### intersectionObserver

```tsx
export const intersectionObserver = (
  el: HTMLElement,
  accessor: () => (entry: IntersectionObserverEntry) => void
) => {
  const observer = new IntersectionObserver((entries) => {
    for (const entry of entries) accessor()(entry);
  });
  observer.observe(el);
  // Cleanup автоматический
};

<div use:intersectionObserver={(entry) => {
  if (entry.isIntersecting) loadImage();
}}>
  Lazy content
</div>
```

### copyToClipboard

```tsx
export const copyOnClick = (el: HTMLElement, accessor: () => string) => {
  const handler = async () => {
    await navigator.clipboard.writeText(accessor());
    el.dispatchEvent(new CustomEvent("copied"));
  };
  el.addEventListener("click", handler);
};

<button
  use:copyOnClick={"copy this text"}
  oncopied={() => alert("Copied!")}
>
  Copy
</button>
```

### longPress

```tsx
interface LongPressOptions {
  duration?: number;
  onPress: () => void;
}

export const longPress = (
  el: HTMLElement,
  accessor: () => LongPressOptions
) => {
  let timer: number | undefined;
  
  const start = () => {
    const opts = accessor();
    timer = window.setTimeout(opts.onPress, opts.duration ?? 500);
  };
  
  const cancel = () => clearTimeout(timer);
  
  el.addEventListener("mousedown", start);
  el.addEventListener("touchstart", start);
  el.addEventListener("mouseup", cancel);
  el.addEventListener("touchend", cancel);
  el.addEventListener("mouseleave", cancel);
};
```

---

## 82. Custom primitives — библиотека

Когда хочешь переиспользовать реактивную логику между компонентами — создавай custom primitives. Аналог hooks из React, но без правил хуков.

### createLocalStorage

```tsx
import { createSignal, createEffect, Accessor } from "solid-js";

export const createLocalStorage = <T,>(
  key: string,
  initial: T
): [Accessor<T>, (value: T) => void] => {
  const [value, setValue] = createSignal<T>(
    JSON.parse(localStorage.getItem(key) ?? "null") ?? initial
  );
  
  createEffect(() => {
    localStorage.setItem(key, JSON.stringify(value()));
  });
  
  return [value, setValue];
};

// Использование
const [theme, setTheme] = createLocalStorage<"light" | "dark">("theme", "light");
```

### createDebounced

```tsx
export const createDebounced = <T,>(
  source: Accessor<T>,
  delay: number
): Accessor<T> => {
  const [debounced, setDebounced] = createSignal(source());
  
  createEffect(() => {
    const value = source();
    const timer = setTimeout(() => setDebounced(() => value), delay);
    onCleanup(() => clearTimeout(timer));
  });
  
  return debounced;
};

// Использование
const [search, setSearch] = createSignal("");
const debouncedSearch = createDebounced(search, 300);
```

### createWindowSize

```tsx
export const createWindowSize = () => {
  const [size, setSize] = createSignal({
    width: window.innerWidth,
    height: window.innerHeight,
  });
  
  onMount(() => {
    const handler = () => setSize({
      width: window.innerWidth,
      height: window.innerHeight,
    });
    window.addEventListener("resize", handler);
    onCleanup(() => window.removeEventListener("resize", handler));
  });
  
  return size;
};
```

### createIntersectionObserver

```tsx
export const createIntersectionObserver = (
  ref: () => HTMLElement | undefined,
  options?: IntersectionObserverInit
) => {
  const [isIntersecting, setIsIntersecting] = createSignal(false);
  
  createEffect(() => {
    const el = ref();
    if (!el) return;
    
    const observer = new IntersectionObserver(
      ([entry]) => setIsIntersecting(entry.isIntersecting),
      options
    );
    observer.observe(el);
    onCleanup(() => observer.disconnect());
  });
  
  return isIntersecting;
};
```

### createFetch

```tsx
import { createResource } from "solid-js";

export const createFetch = <T,>(url: () => string) => {
  return createResource(url, async (url) => {
    const response = await fetch(url);
    if (!response.ok) throw new Error(`HTTP ${response.status}`);
    return response.json() as Promise<T>;
  });
};

// Использование
const [posts] = createFetch<Post[]>(() => `/api/posts?page=${page()}`);
```

### Что готовое в экосистеме

Не пиши свои — используй `@solid-primitives/*`:
- `@solid-primitives/storage` — localStorage/sessionStorage
- `@solid-primitives/scheduled` — debounce/throttle
- `@solid-primitives/intersection-observer`
- `@solid-primitives/media` — matchMedia
- `@solid-primitives/keyboard`

См. раздел 114.

---
---

# Часть XV — Стилизация

## 83. UnoCSS подробно

UnoCSS — atomic CSS engine. Альтернатива Tailwind, быстрее, гибче.

### Установка

```bash
pnpm add -D unocss @unocss/preset-wind3
```

`vite.config.ts`:
```ts
import { defineConfig } from "vite";
import solidPlugin from "vite-plugin-solid";
import UnoCSS from "unocss/vite";
import { presetWind3 } from "@unocss/preset-wind3";

export default defineConfig({
  plugins: [
    solidPlugin(),
    UnoCSS({
      presets: [presetWind3()],
    }),
  ],
});
```

`src/index.tsx`:
```ts
import "virtual:uno.css";
```

### Базовый синтаксис (как Tailwind)

```tsx
<div class="flex items-center justify-between p-4 bg-blue-500 text-white rounded">
  ...
</div>
```

### Динамические классы — classList

`classList` — лучше чем тернарные операторы в `class`:

```tsx
<div
  classList={{
    "bg-blue-500": isActive(),
    "bg-gray-300": !isActive(),
    "opacity-50": isDisabled(),
  }}
>
```

### Шорткаты (короткие имена для частых наборов)

```ts
UnoCSS({
  shortcuts: {
    "btn": "px-4 py-2 rounded font-medium",
    "btn-primary": "btn bg-blue-500 text-white hover:bg-blue-600",
    "card": "bg-white rounded-lg shadow p-4",
  },
})
```

```tsx
<button class="btn-primary">Click</button>
```

### Attributify mode

Атрибутный синтаксис вместо длинного class:

```ts
import { presetAttributify } from "@unocss/preset-attributify";

UnoCSS({
  presets: [presetWind3(), presetAttributify()],
})
```

```tsx
<button
  bg="blue-500 hover:blue-600"
  text="white sm"
  p="x-4 y-2"
  rounded
>
  Click
</button>
```

### Иконки через preset-icons

```ts
import { presetIcons } from "@unocss/preset-icons";

UnoCSS({
  presets: [presetWind3(), presetIcons()],
})
```

```tsx
<i class="i-heroicons-user" />
<i class="i-mdi-home text-2xl text-blue-500" />
```

Доступно 100000+ иконок из Iconify.

---

## 84. CSS Modules

Изолированные стили. Каждый класс получает уникальное имя.

### Создание

```css
/* Button.module.css */
.button {
  padding: 8px 16px;
  background: blue;
  color: white;
}

.primary {
  background: green;
}
```

```tsx
import styles from "./Button.module.css";

const Button: Component = () => (
  <button class={`${styles.button} ${styles.primary}`}>Click</button>
);
```

### Когда использовать

- Если нужны сложные стили которые сложно сделать atomic классами
- Если работаешь в команде где не любят Tailwind
- Для библиотеки компонентов (изоляция)

В SolidJS обычно проще использовать UnoCSS — меньше файлов, проще организация.

---

## 85. style атрибут

Для динамических стилей где классы не подходят:

```tsx
const [x, setX] = createSignal(0);

<div
  style={{
    transform: `translateX(${x()}px)`,
    transition: "transform 0.3s",
  }}
>
  Двигается
</div>
```

### CSS Custom Properties

```tsx
<div style={{ "--my-color": color() }}>
  <p style={{ color: "var(--my-color)" }}>Текст</p>
</div>
```

---

## 86. classList

Удобный способ управлять классами реактивно:

```tsx
<button
  classList={{
    "btn": true,
    "btn-primary": variant() === "primary",
    "btn-secondary": variant() === "secondary",
    "disabled": disabled(),
  }}
>
```

В отличие от `class={...}` со строкой, `classList` оптимизирован — обновляет только изменившиеся классы.

---
---

# Часть XVI — Тестирование

## 87. Vitest + @solidjs/testing-library

### Установка

```bash
pnpm add -D vitest @solidjs/testing-library jsdom @testing-library/jest-dom
```

`vite.config.ts`:
```ts
export default defineConfig({
  plugins: [solidPlugin()],
  test: {
    environment: "jsdom",
    globals: true,
    setupFiles: ["./src/test-setup.ts"],
  },
});
```

`src/test-setup.ts`:
```ts
import "@testing-library/jest-dom/vitest";
```

`package.json`:
```json
{
  "scripts": {
    "test": "vitest",
    "test:run": "vitest run",
    "test:ui": "vitest --ui"
  }
}
```

### Первый тест

```tsx
// Counter.test.tsx
import { render, fireEvent } from "@solidjs/testing-library";
import { describe, it, expect } from "vitest";
import Counter from "./Counter";

describe("Counter", () => {
  it("показывает начальное значение", () => {
    const { getByText } = render(() => <Counter />);
    expect(getByText("Count: 0")).toBeInTheDocument();
  });
  
  it("увеличивается при клике", async () => {
    const { getByText, getByRole } = render(() => <Counter />);
    
    const button = getByRole("button", { name: /\+1/i });
    await fireEvent.click(button);
    
    expect(getByText("Count: 1")).toBeInTheDocument();
  });
});
```

### Тест с props

```tsx
import { Greeting } from "./Greeting";

it("показывает имя", () => {
  const { getByText } = render(() => <Greeting name="Jesus" />);
  expect(getByText("Привет, Jesus!")).toBeInTheDocument();
});
```

### Тест с user input

```tsx
it("обновляется при вводе", async () => {
  const { getByLabelText, getByText } = render(() => <SearchInput />);
  
  const input = getByLabelText(/search/i) as HTMLInputElement;
  await fireEvent.input(input, { target: { value: "test" } });
  
  expect(getByText("Вы ввели: test")).toBeInTheDocument();
});
```

---

## 88. Тестирование сигналов, стора, контекста

### Тест чистой реактивной логики

```tsx
import { createRoot, createSignal, createEffect } from "solid-js";
import { describe, it, expect, vi } from "vitest";

describe("реактивность", () => {
  it("сигнал обновляется", () => {
    createRoot((dispose) => {
      const [count, setCount] = createSignal(0);
      
      expect(count()).toBe(0);
      setCount(5);
      expect(count()).toBe(5);
      
      dispose();
    });
  });
  
  it("эффект запускается при изменении", () => {
    createRoot((dispose) => {
      const [count, setCount] = createSignal(0);
      const fn = vi.fn();
      
      createEffect(() => fn(count()));
      
      // Первый запуск
      expect(fn).toHaveBeenCalledWith(0);
      
      setCount(1);
      // Эффекты выполняются асинхронно — нужно подождать
      // Или использовать createRenderEffect для синхронного теста
      
      dispose();
    });
  });
});
```

### Тест компонента с контекстом

```tsx
import { AuthProvider } from "./context/AuthContext";

it("компонент с auth контекстом", () => {
  const { getByText } = render(() => (
    <AuthProvider>
      <Profile />
    </AuthProvider>
  ));
  
  expect(getByText(/гость/i)).toBeInTheDocument();
});
```

### Тест с роутером

```tsx
import { Router, Route } from "@solidjs/router";
import { MemoryRouter } from "@solidjs/router";

it("навигация работает", async () => {
  const { getByText, getByRole } = render(() => (
    <MemoryRouter>
      <Route path="/" component={Home} />
      <Route path="/about" component={About} />
    </MemoryRouter>
  ));
  
  await fireEvent.click(getByRole("link", { name: /about/i }));
  expect(getByText(/about page/i)).toBeInTheDocument();
});
```

---

## 89. Моки fetch и async

### Мок fetch с vi.fn

```tsx
import { vi } from "vitest";

beforeEach(() => {
  globalThis.fetch = vi.fn();
});

it("загружает пользователя", async () => {
  (globalThis.fetch as any).mockResolvedValue({
    ok: true,
    json: async () => ({ id: 1, name: "Jesus" }),
  });
  
  const { findByText } = render(() => <UserProfile id={1} />);
  
  expect(await findByText("Jesus")).toBeInTheDocument();
});
```

### MSW (Mock Service Worker)

Лучший способ мокать API — выглядит как настоящий сервер:

```bash
pnpm add -D msw
```

```tsx
// mocks/server.ts
import { setupServer } from "msw/node";
import { http, HttpResponse } from "msw";

export const handlers = [
  http.get("/api/users/:id", ({ params }) => {
    return HttpResponse.json({ id: params.id, name: "Jesus" });
  }),
];

export const server = setupServer(...handlers);
```

```ts
// test-setup.ts
import { server } from "./mocks/server";

beforeAll(() => server.listen());
afterEach(() => server.resetHandlers());
afterAll(() => server.close());
```

### Тестирование с createResource

```tsx
it("создаёт ресурс", async () => {
  const { findByText } = render(() => <UserList />);
  
  // findByText ждёт пока элемент появится (для async)
  expect(await findByText("Jesus")).toBeInTheDocument();
});
```

---

## 90. E2E через Playwright

```bash
pnpm create playwright
```

Это поставит конфиг и тесты.

### Базовый E2E тест

```ts
// tests/login.spec.ts
import { test, expect } from "@playwright/test";

test("логин работает", async ({ page }) => {
  await page.goto("/login");
  
  await page.getByLabel("Email").fill("test@example.com");
  await page.getByLabel("Пароль").fill("password123");
  await page.getByRole("button", { name: "Войти" }).click();
  
  await expect(page).toHaveURL("/dashboard");
  await expect(page.getByText("Добро пожаловать")).toBeVisible();
});
```

### Запуск

```bash
pnpm playwright test           # все тесты
pnpm playwright test --ui      # с UI
pnpm playwright test --debug   # дебаг
pnpm playwright codegen        # запись действий
```

### Когда писать E2E

- Критичные user flows (логин, оплата, регистрация)
- Cross-browser совместимость
- Финальная проверка перед deploy

E2E медленные — для покрытия логики лучше unit тесты на Vitest.

---
---

# Часть XVII — Debugging и Devtools (НОВАЯ)

## 91. Solid Devtools — установка и обзор

[Solid Devtools](https://github.com/thetarnav/solid-devtools) — расширение для Chrome которое показывает реактивный граф приложения.

### Установка

```bash
pnpm add -D solid-devtools
```

`vite.config.ts`:
```ts
import devtools from "solid-devtools/vite";

export default defineConfig({
  plugins: [
    devtools({
      autoname: true, // автоматические имена для сигналов
    }),
    solidPlugin(),
  ],
});
```

`src/index.tsx` — импорт в начале:
```ts
import "solid-devtools";
```

Установи [Chrome extension](https://chromewebstore.google.com/detail/solid-devtools/kmcfjchnmmaeeagadbhoofajiopoceel).

### Что показывает

В DevTools появится таб "Solid":
1. **Components** — дерево компонентов с props
2. **Owner tree** — иерархия владельцев
3. **Реактивные узлы** — сигналы, мемо, эффекты
4. **Графовые связи** — кто на что подписан

---

## 92. Чтение реактивного графа в devtools

### Components tab

Показывает дерево компонентов. Кликая по компоненту видишь:
- Props
- Сигналы внутри
- Computations (эффекты, мемо)
- Дочерние компоненты

### Просмотр сигналов

В правой панели каждый сигнал показывает:
- Имя (если задано в options)
- Текущее значение
- Кто на него подписан

### Граф зависимостей

Можно увидеть граф: какие computations зависят от каких сигналов. Полезно для:
- Понимания что обновляется при изменении сигнала
- Поиска лишних подписок
- Оптимизации реактивности

### Time-travel debugging

Devtools записывает изменения сигналов. Можно вернуться назад во времени и посмотреть прошлые значения.

---

## 93. Типичные проблемы реактивности

### Проблема 1: Эффект не срабатывает

**Признак:** Меняешь сигнал, но связанный эффект не реагирует.

**Возможные причины:**

1. **Забыл вызов**
```tsx
// ❌
createEffect(() => {
  console.log(count); // ссылка на функцию, не значение
});

// ✅
createEffect(() => {
  console.log(count()); // вызов создаёт подписку
});
```

2. **Деструктурировал props**
```tsx
// ❌
const MyComponent: Component<{ value: number }> = ({ value }) => {
  createEffect(() => console.log(value)); // value не реактивно
};

// ✅
const MyComponent: Component<{ value: number }> = (props) => {
  createEffect(() => console.log(props.value));
};
```

3. **Эффект вне tracking scope**
```tsx
// ❌
async function handleClick() {
  await fetch("/api");
  createEffect(() => count()); // создаётся вне owner!
}

// ✅
const owner = getOwner();
async function handleClick() {
  await fetch("/api");
  runWithOwner(owner, () => {
    createEffect(() => count());
  });
}
```

### Проблема 2: Эффект срабатывает слишком часто

**Признак:** Бесконечный цикл или эффект запускается на каждое обновление чего-то.

**Возможные причины:**

1. **Установка сигнала в эффекте который читает тот же сигнал**
```tsx
// ❌ Бесконечный цикл
createEffect(() => {
  setCount(count() + 1);
});
```

2. **Объекты сравниваются по ссылке**
```tsx
// ❌ Объект всегда новый — equals не помогает
const [user, setUser] = createSignal({ name: "Jesus" });
setUser({ name: "Jesus" }); // новый объект, эффект сработает

// ✅ Сравнение по полю
const [user, setUser] = createSignal({ name: "Jesus" }, {
  equals: (a, b) => a.name === b.name,
});
```

3. **Подписка на лишний сигнал**
```tsx
createEffect(() => {
  if (showName()) {
    fetch(`/api/user/${userId()}`); // подписка на userId всегда
  }
});

// Лучше — разделить
createEffect(() => {
  if (!showName()) return;
  const id = userId();
  fetch(`/api/user/${id}`);
});
```

### Проблема 3: Сигналы вне reactive scope

**Признак:** Warning в консоли: "computations created outside a `createRoot` or `render` will never be run".

**Причина:** Создал сигнал в обычной функции без обёртки `createRoot`.

```tsx
// ❌
function createCounter() {
  const [count, setCount] = createSignal(0);
  createEffect(() => console.log(count())); // создан вне owner
  return { count, setCount };
}

// ✅ Вызывать из компонента — там есть owner
const Component: Component = () => {
  const counter = createCounter(); // OK — owner есть
};

// ✅ Или создать свой owner
const counter = createRoot(() => createCounter());
```

### Проблема 4: Stale-замыкания в async коде

**Признак:** В async-функции читаешь старое значение сигнала.

```tsx
// ✅ В Solid это редко проблема (в отличие от React) — сигналы всегда актуальные
const [count, setCount] = createSignal(0);

const handleClick = async () => {
  setCount(5);
  await sleep(1000);
  console.log(count()); // 5 — всегда актуально
};
```

В Solid стейл замыкания нет благодаря тому что сигналы — функции.

---

## 94. Логирование сигналов и эффектов

### Через name option

```tsx
const [count, setCount] = createSignal(0, { name: "counter" });
const total = createMemo(() => count() * 10, undefined, { name: "total-memo" });
```

В devtools эти узлы будут с понятными именами.

### Через console.log с указанием контекста

```tsx
const useUserData = (userId: () => number) => {
  const [data] = createResource(userId, async (id) => {
    console.log(`[useUserData] fetching for id=${id}`);
    const result = await api.getUser(id);
    console.log(`[useUserData] received:`, result);
    return result;
  });
  
  createEffect(() => {
    console.log(`[useUserData] data changed:`, data());
  });
  
  return data;
};
```

### Дебаг эффекта с предыдущим значением

```tsx
createEffect((prev) => {
  const current = something();
  console.log(`changed from ${prev} to ${current}`);
  return current;
});
```

### Wrapper для группировки логов

```tsx
const debugSignal = <T,>(name: string, signal: Accessor<T>) => {
  createEffect((prev) => {
    const current = signal();
    if (prev !== current) {
      console.group(`📡 ${name}`);
      console.log("prev:", prev);
      console.log("new:", current);
      console.groupEnd();
    }
    return current;
  });
  return signal;
};

// Использование
const debouncedSearch = debugSignal("debounced search", deferredSearch);
```

---

## 95. Стектрейсы из реактивных вычислений

### Включить полные стектрейсы

В dev режиме SolidJS добавляет полезные стектрейсы автоматически. В production они минифицируются.

Проверь что в `vite.config.ts` нет блокировки:
```ts
export default defineConfig({
  plugins: [solidPlugin({ dev: true })],
  // ...
});
```

### Где смотреть

При ошибке в эффекте/мемо стек покажет:
1. Файл и строку где упало
2. Контекст: какой computation выполнялся
3. Цепочку source -> effect

### Warning "Computations created outside createRoot"

Самый частый. Означает: реактивный примитив создан вне owner. Точное место — в стектрейсе.

### Как искать утечки

В devtools:
1. Делаешь действие
2. Смотришь сколько новых owners создалось
3. Возвращаешь интерфейс к исходному состоянию
4. Смотришь сколько owners осталось

Если число растёт — где-то нет cleanup.

---
---

# Часть XVIII — Производительность (УГЛУБЛЕНО)

## 96. Профилирование через Devtools

### Chrome Performance tab

1. Открой DevTools → Performance
2. Нажми Record
3. Сделай действие в приложении
4. Stop

Что смотреть:
- **Frames** — должны быть зелёные. Красные = jank
- **Main thread** — что выполняется
- **Long tasks** (>50ms) — выделены красным

### Solid Devtools profiling

В Solid Devtools тоже есть профайлер:
1. Запиши действие
2. Увидишь сколько computations сработало
3. Время выполнения каждого

Это точнее чем Chrome performance — видишь именно реактивные обновления, не браузерные операции.

### Что мерить

```tsx
// Время выполнения
const start = performance.now();
expensiveComputation();
console.log(`Took ${performance.now() - start}ms`);

// Marker для chrome performance
performance.mark("filter-start");
const filtered = items().filter(/* ... */);
performance.mark("filter-end");
performance.measure("filter", "filter-start", "filter-end");
```

---

## 97. Анти-паттерны производительности

### Анти-паттерн 1: createSignal в JSX

```tsx
// ❌ КАТАСТРОФА — создаёт новый сигнал на каждый ререндер JSX
<For each={items()}>
  {(item) => {
    const [count, setCount] = createSignal(0); // ❌ внутри For — допустимо
    return <div>{count()}</div>;
  }}
</For>

// Но это:
<div>
  {(() => {
    const [x] = createSignal(0); // ❌ создаётся при каждом обновлении JSX
    return x();
  })()}
</div>
```

### Анти-паттерн 2: Избыточные мемо

```tsx
// ❌ Мемо для простой операции
const doubled = createMemo(() => count() * 2);
return <div>{doubled()}</div>;

// ✅ Просто
return <div>{count() * 2}</div>;
```

`createMemo` оправдан когда:
- Дорогое вычисление (сортировка большого массива)
- Результат используется несколько раз
- Нужен equals для производных эффектов

### Анти-паттерн 3: Большой массив в одном сигнале

```tsx
// ❌ При изменении одного элемента — обновится весь UI который читает items
const [items, setItems] = createSignal<Item[]>([...10000 items]);
setItems([...items(), newItem]); // создаётся новый массив

// ✅ Store даёт fine-grained обновления
const [items, setItems] = createStore<Item[]>([...10000 items]);
setItems(items.length, newItem); // обновляется только конкретное место
```

### Анти-паттерн 4: Index вместо For (или наоборот)

```tsx
// ❌ For для статичного списка по индексам
<For each={Array.from({ length: 100 })}>
  {(_, i) => <Cell index={i()} />}
</For>

// ✅ Index — индекс стабилен
<Index each={Array.from({ length: 100 })}>
  {(_, i) => <Cell index={i} />}
</Index>
```

Подробнее — раздел 120.

### Анти-паттерн 5: Сложные expressions в JSX

```tsx
// ❌ Пересчитывается каждый раз когда JSX обновляется
<div>
  {items().filter(x => x.active).sort((a, b) => a.priority - b.priority).map(...)}
</div>

// ✅ Через createMemo
const filteredSorted = createMemo(() =>
  items().filter(x => x.active).sort((a, b) => a.priority - b.priority)
);

<div>
  <For each={filteredSorted()}>{...}</For>
</div>
```

### Анти-паттерн 6: Подписка на много в одном эффекте

```tsx
// ❌ Один эффект подписан на много — пересоздаётся часто
createEffect(() => {
  const data = {
    user: user(),
    posts: posts(),
    settings: settings(),
    theme: theme(),
  };
  saveAll(data);
});

// ✅ Разделить по интересам
createEffect(() => saveUser(user()));
createEffect(() => savePosts(posts()));
createEffect(() => saveSettings(settings()));
```

---

## 98. Виртуализация списков

Когда список из 1000+ элементов — рендерить всё неоптимально. Виртуализация рендерит только видимые.

```bash
pnpm add @tanstack/solid-virtual
```

```tsx
import { createVirtualizer } from "@tanstack/solid-virtual";

const VirtualList: Component<{ items: Item[] }> = (props) => {
  let parentRef!: HTMLDivElement;
  
  const virtualizer = createVirtualizer({
    count: props.items.length,
    getScrollElement: () => parentRef,
    estimateSize: () => 50,  // высота одного элемента
    overscan: 5,             // сколько дополнительно рендерить
  });
  
  return (
    <div ref={parentRef} style={{ height: "400px", overflow: "auto" }}>
      <div
        style={{
          height: `${virtualizer.getTotalSize()}px`,
          position: "relative",
        }}
      >
        <For each={virtualizer.getVirtualItems()}>
          {(virtualRow) => (
            <div
              style={{
                position: "absolute",
                top: 0,
                left: 0,
                width: "100%",
                height: `${virtualRow.size}px`,
                transform: `translateY(${virtualRow.start}px)`,
              }}
            >
              {props.items[virtualRow.index].name}
            </div>
          )}
        </For>
      </div>
    </div>
  );
};
```

### Когда нужна виртуализация

- 100+ элементов с сложным содержимым → виртуализация
- 1000+ элементов любого вида → обязательна
- < 100 простых элементов → не нужна

---

## 99. Code splitting и lazy

Часть в разделе 27. Дополнительно:

### Route-based splitting

```tsx
import { Router, Route } from "@solidjs/router";
import { lazy } from "solid-js";

const Home = lazy(() => import("./pages/Home"));
const Profile = lazy(() => import("./pages/Profile"));
const Settings = lazy(() => import("./pages/Settings"));
const Admin = lazy(() => import("./pages/Admin"));

const App = () => (
  <Router>
    <Route path="/" component={Home} />
    <Route path="/profile" component={Profile} />
    <Route path="/settings" component={Settings} />
    <Route path="/admin" component={Admin} />
  </Router>
);
```

Каждая страница — отдельный бандл. Стартовый бандл маленький.

### Component-level splitting

```tsx
const HeavyChart = lazy(() => import("./components/HeavyChart"));

const Dashboard: Component = () => {
  const [showChart, setShowChart] = createSignal(false);
  
  return (
    <>
      <button onClick={() => setShowChart(true)}>Показать график</button>
      <Show when={showChart()}>
        <Suspense fallback={<Spinner />}>
          <HeavyChart />
        </Suspense>
      </Show>
    </>
  );
};
```

### Manual chunks в Vite

```ts
// vite.config.ts
export default defineConfig({
  build: {
    rollupOptions: {
      output: {
        manualChunks: {
          "vendor": ["solid-js", "@solidjs/router"],
          "charts": ["chart.js", "d3"],
        },
      },
    },
  },
});
```

Это даёт контроль над тем как код делится на чанки.

---

## 100. Когда createSelector действительно нужен

В разделе 14 видели API. Когда это даёт реальный выигрыш?

### Пример: список с выделением

**Без createSelector — 100 элементов:**
```tsx
const [selectedId, setSelectedId] = createSignal(1);

<For each={items()}>
  {(item) => (
    <div class={selectedId() === item.id ? "selected" : ""}>
      {item.name}
    </div>
  )}
</For>
```

Каждый элемент имеет реактивную подписку на `selectedId`. При его изменении ВСЕ 100 элементов проверяют условие.

**С createSelector:**
```tsx
const isSelected = createSelector(selectedId);

<For each={items()}>
  {(item) => (
    <div class={isSelected(item.id) ? "selected" : ""}>
      {item.name}
    </div>
  )}
</For>
```

`createSelector` создаёт keyed подписки. При изменении `selectedId` с 1 на 5 — обновляются только два элемента (старый и новый).

### Бенчмарк

- 1000 элементов, без `createSelector`: ~50мс на каждое изменение selectedId
- 1000 элементов, с `createSelector`: ~1мс на каждое изменение

Разница в 50x. Но для 10 элементов — не заметно, не стоит усложнять.

### Когда стоит использовать

- Список 50+ элементов
- Только один или мало элементов в "выделенном" состоянии
- Изменение выделенного элемента происходит часто

### Когда не стоит

- Маленькие списки
- Состояние не "выделен/не выделен" а сложнее (несколько свойств)
- Несколько активных одновременно (тогда лучше Set/Map в Store)

---
---
---

# Часть XIX — SolidStart (БОЛЬШАЯ ЧАСТЬ)

SolidStart — мета-фреймворк для SolidJS. Аналог Next.js / Remix / SvelteKit. Это то на чём пишут production приложения на Solid.

## 101. Что такое SolidStart

SolidStart даёт:
- **File-based routing** — структура папок = роуты
- **SSR/SSG/SPA** — выбираешь стратегию рендера
- **Server functions** — RPC, типизированные вызовы сервера из клиента
- **Actions** — отправка форм с прогрессивным enhancement
- **Streaming SSR** — server-side рендер по частям
- **Middleware** — глобальные обработчики запросов
- **API routes** — REST endpoints в той же кодовой базе
- **Адаптеры** — deploy в Vercel, Netlify, Cloudflare, Node

### Когда использовать

- Production веб-приложение → почти всегда SolidStart
- SEO важен → обязательно
- Сервер нужен для аутентификации / БД → удобно
- Простая SPA без сервера → можно и без SolidStart

### Когда НЕ использовать

- Чисто клиентский виджет (виджет на сайте, embed)
- Mobile через Capacitor/Tauri (вне браузера)
- Очень специфичные требования к deploy

---

## 102. Создание проекта и структура

### Создание

```bash
pnpm create solid
# Project type: SolidStart
# Template: basic / with-auth / with-tailwind / etc.
# TypeScript: yes
```

### Структура

```
my-app/
├── src/
│   ├── routes/              ← файловый роутинг
│   │   ├── index.tsx        → /
│   │   ├── about.tsx        → /about
│   │   ├── posts/
│   │   │   ├── index.tsx    → /posts
│   │   │   └── [id].tsx     → /posts/:id
│   │   └── api/             ← API endpoints
│   │       └── hello.ts     → /api/hello
│   ├── components/          ← общие компоненты
│   ├── lib/                 ← бизнес-логика, утилиты
│   ├── app.tsx              ← рут компонент (как _app в Next)
│   ├── entry-client.tsx     ← клиентская точка входа
│   ├── entry-server.tsx     ← серверная точка входа
│   └── global.d.ts          ← глобальные TS типы
├── public/                  ← статика
├── app.config.ts            ← конфиг приложения
├── package.json
└── tsconfig.json
```

### app.config.ts

```ts
import { defineConfig } from "@solidjs/start/config";

export default defineConfig({
  ssr: true,                  // SSR включён
  // ssr: false,              // SPA mode
  // ssr: "async",            // async SSR (streaming)
  
  vite: {
    plugins: [/* твои Vite плагины */],
  },
  
  server: {
    preset: "node-server",    // или "vercel", "netlify", "cloudflare"
  },
});
```

### Запуск

```bash
pnpm dev      # dev сервер
pnpm build    # production build
pnpm start    # запустить prod build
```

---

## 103. File-based routing

Каждый `.tsx` файл в `src/routes/` становится роутом.

### Базовые роуты

```
src/routes/
├── index.tsx          → /
├── about.tsx          → /about
├── contact.tsx        → /contact
```

### Вложенность через папки

```
src/routes/
├── users/
│   ├── index.tsx      → /users
│   ├── [id].tsx       → /users/:id
│   └── [id]/
│       ├── posts.tsx  → /users/:id/posts
│       └── edit.tsx   → /users/:id/edit
```

### Динамические сегменты

```tsx
// src/routes/posts/[id].tsx
import { useParams } from "@solidjs/router";

export default function PostPage() {
  const params = useParams<{ id: string }>();
  return <div>Пост ID: {params.id}</div>;
}
```

### Catch-all

```
src/routes/
├── docs/
│   └── [...slug].tsx  → /docs/anything/here/works
```

```tsx
// src/routes/docs/[...slug].tsx
import { useParams } from "@solidjs/router";

export default function DocPage() {
  const params = useParams();
  // params.slug = "anything/here/works"
  return <div>Документ: {params.slug}</div>;
}
```

### Route groups (не влияют на URL)

```
src/routes/
├── (marketing)/         ← скобки = группа, не в URL
│   ├── about.tsx        → /about
│   ├── pricing.tsx      → /pricing
│   └── _layout.tsx      ← общий layout для группы
├── (app)/
│   ├── dashboard.tsx    → /dashboard
│   └── _layout.tsx
```

---

## 104. Server functions ("use server")

Server functions — функции которые выполняются на сервере, но вызываются из клиента как обычные. Аналог tRPC, но проще.

### Базовый пример

```tsx
// src/lib/api.ts
"use server";

export async function getUser(id: number) {
  // Этот код выполняется ТОЛЬКО на сервере
  const user = await db.user.findUnique({ where: { id } });
  return user;
}
```

```tsx
// src/routes/profile.tsx
import { getUser } from "~/lib/api";

export default function Profile() {
  const handleClick = async () => {
    // Из клиента вызываем серверную функцию
    const user = await getUser(1);
    console.log(user);
  };
  
  return <button onClick={handleClick}>Load user</button>;
}
```

Под капотом:
- Клиент отправляет POST-запрос
- Сервер выполняет функцию
- Возвращает результат

### Преимущества

- **Типобезопасность** — TS видит сигнатуру функции
- **Можно использовать БД, секреты, файловую систему** на сервере
- **Никакого ручного создания API endpoints** для простых случаев

### Файлы с "use server" вверху

```tsx
// src/lib/api.ts
"use server"; // ВСЕ функции в файле — серверные

export async function getUser(id: number) { /* ... */ }
export async function createPost(data: PostData) { /* ... */ }
export async function deletePost(id: number) { /* ... */ }
```

### Inline "use server"

```tsx
export default function MyPage() {
  const loadUsers = async () => {
    "use server"; // только эта функция серверная
    return await db.user.findMany();
  };
}
```

### Безопасность

Параметры приходят с клиента — НИКОГДА не доверяй им:

```tsx
"use server";

import { getCurrentUser } from "~/lib/auth";

export async function deletePost(postId: number) {
  const user = await getCurrentUser();
  if (!user) throw new Error("Не авторизован");
  
  const post = await db.post.findUnique({ where: { id: postId } });
  if (post?.userId !== user.id) {
    throw new Error("Нет прав");
  }
  
  await db.post.delete({ where: { id: postId } });
}
```

---

## 105. Actions и формы с прогрессивным enhancement

Actions — server functions для форм, работают БЕЗ JS.

### Создание action

```tsx
import { action } from "@solidjs/router";

const createPost = action(async (formData: FormData) => {
  "use server";
  
  const title = formData.get("title") as string;
  const body = formData.get("body") as string;
  
  if (!title || !body) {
    throw new Error("Все поля обязательны");
  }
  
  const post = await db.post.create({ data: { title, body } });
  return post;
});
```

### Использование в форме

```tsx
import { useAction } from "@solidjs/router";

export default function NewPostPage() {
  const create = useAction(createPost);
  
  return (
    <form action={createPost} method="post">
      <input name="title" required />
      <textarea name="body" required />
      <button type="submit">Создать</button>
    </form>
  );
}
```

**Магия:** форма работает БЕЗ JavaScript. Если JS отключён — браузер отправит POST, сервер выполнит action, вернёт страницу.

С JS — действие отправляется через fetch без перезагрузки страницы.

### useSubmission — состояние отправки

```tsx
import { useSubmission } from "@solidjs/router";

export default function NewPostPage() {
  const submission = useSubmission(createPost);
  
  return (
    <form action={createPost} method="post">
      <input name="title" />
      <textarea name="body" />
      <button type="submit" disabled={submission.pending}>
        {submission.pending ? "Создание..." : "Создать"}
      </button>
      <Show when={submission.error}>
        <p class="text-red-500">{submission.error.message}</p>
      </Show>
    </form>
  );
}
```

### Программный вызов action

```tsx
const create = useAction(createPost);

const handleSubmit = async () => {
  const formData = new FormData();
  formData.set("title", title());
  formData.set("body", body());
  
  try {
    const post = await create(formData);
    console.log("Создан:", post);
  } catch (err) {
    console.error(err);
  }
};
```

### Action с возвратом для редиректа

```tsx
import { action, redirect } from "@solidjs/router";

const createPost = action(async (formData: FormData) => {
  "use server";
  const post = await db.post.create(/* ... */);
  throw redirect(`/posts/${post.id}`);
});
```

---

## 106. Загрузка данных: query, createAsync, preload

### query — для GET запросов

```tsx
import { query } from "@solidjs/router";

const getPost = query(async (id: number) => {
  "use server";
  return await db.post.findUnique({ where: { id } });
}, "getPost");  // имя для кэширования
```

### createAsync — реактивная асинхронная подписка

```tsx
import { createAsync } from "@solidjs/router";
import { useParams } from "@solidjs/router";

export default function PostPage() {
  const params = useParams<{ id: string }>();
  
  const post = createAsync(() => getPost(Number(params.id)));
  
  return (
    <Suspense fallback={<p>Загрузка...</p>}>
      <Show when={post()}>
        <h1>{post()!.title}</h1>
        <p>{post()!.body}</p>
      </Show>
    </Suspense>
  );
}
```

### preload — предзагрузка для роута

```tsx
// src/routes/posts/[id].tsx
import { RouteDefinition } from "@solidjs/router";

export const route = {
  preload({ params }) {
    void getPost(Number(params.id));  // запускаем загрузку
  },
} satisfies RouteDefinition;

export default function PostPage() {
  const params = useParams<{ id: string }>();
  const post = createAsync(() => getPost(Number(params.id)));
  // Данные уже грузятся к моменту монтирования
  // ...
}
```

С `preload` пользователь не видит fallback — данные приходят пока компонент монтируется.

### Кэширование

`query` автоматически кэширует. Если вызвать `getPost(1)` дважды подряд — второй вызов вернёт из кэша.

### Инвалидация после mutation

```tsx
import { revalidate } from "@solidjs/router";

const updatePost = action(async (formData: FormData) => {
  "use server";
  await db.post.update(/* ... */);
});

// После успешного обновления — перезагрузить кэш
const update = useAction(updatePost);
const handleSubmit = async (e: SubmitEvent) => {
  await update(new FormData(e.target as HTMLFormElement));
  revalidate(getPost.key);  // обновится в queries которые используют getPost
};
```

### Полный пример

```tsx
// src/lib/posts.ts
import { query, action } from "@solidjs/router";

export const getPosts = query(async () => {
  "use server";
  return await db.post.findMany({ orderBy: { createdAt: "desc" } });
}, "getPosts");

export const getPost = query(async (id: number) => {
  "use server";
  return await db.post.findUnique({ where: { id } });
}, "getPost");

export const createPost = action(async (formData: FormData) => {
  "use server";
  const post = await db.post.create({
    data: {
      title: formData.get("title") as string,
      body: formData.get("body") as string,
    },
  });
  return post;
});

// src/routes/posts/index.tsx
import { createAsync } from "@solidjs/router";
import { getPosts } from "~/lib/posts";

export const route = {
  preload: () => getPosts(),
};

export default function PostsPage() {
  const posts = createAsync(() => getPosts());
  
  return (
    <Suspense fallback={<p>Загрузка...</p>}>
      <For each={posts()}>
        {(post) => (
          <article>
            <h2><a href={`/posts/${post.id}`}>{post.title}</a></h2>
          </article>
        )}
      </For>
    </Suspense>
  );
}
```

---

## 107. Cookies и сессии

### Чтение cookies

```tsx
"use server";

import { getRequestEvent } from "solid-js/web";
import { getCookie } from "vinxi/http";

export async function getCurrentUser() {
  const event = getRequestEvent();
  if (!event) return null;
  
  const sessionId = getCookie(event.nativeEvent, "session");
  if (!sessionId) return null;
  
  return await db.session.findUnique({
    where: { id: sessionId },
    include: { user: true },
  });
}
```

### Установка cookies

```tsx
"use server";

import { setCookie } from "vinxi/http";

export async function login(email: string, password: string) {
  const user = await authenticateUser(email, password);
  if (!user) throw new Error("Invalid");
  
  const session = await db.session.create({
    data: { userId: user.id, expiresAt: addDays(new Date(), 30) },
  });
  
  const event = getRequestEvent()!;
  setCookie(event.nativeEvent, "session", session.id, {
    httpOnly: true,
    secure: true,
    sameSite: "lax",
    maxAge: 60 * 60 * 24 * 30, // 30 дней
  });
}
```

### Удаление cookie (logout)

```tsx
import { deleteCookie } from "vinxi/http";

export async function logout() {
  "use server";
  const event = getRequestEvent()!;
  deleteCookie(event.nativeEvent, "session");
}
```

### Готовые библиотеки сессий

- `@solid-mediakit/auth` — обёртка для auth.js
- `lucia-auth` — современная auth библиотека
- Самописное (полный контроль)

---

## 108. Middleware

Middleware — функции выполняемые до обработки запроса. Для auth, логирования, headers.

```ts
// src/middleware.ts
import { createMiddleware } from "@solidjs/start/middleware";

export default createMiddleware({
  onRequest: [
    async (event) => {
      // Логирование
      console.log(event.request.method, event.request.url);
    },
    async (event) => {
      // Auth check
      const path = new URL(event.request.url).pathname;
      if (path.startsWith("/admin")) {
        const user = await getCurrentUser();
        if (!user?.isAdmin) {
          return new Response("Forbidden", { status: 403 });
        }
      }
    },
  ],
  onBeforeResponse: [
    async (event) => {
      // Добавить headers
      // ...
    },
  ],
});
```

`app.config.ts`:
```ts
export default defineConfig({
  middleware: "./src/middleware.ts",
});
```

---

## 109. API routes

Создание REST endpoints в `src/routes/api/`:

```ts
// src/routes/api/users.ts
import { APIEvent } from "@solidjs/start/server";

export async function GET() {
  const users = await db.user.findMany();
  return new Response(JSON.stringify(users), {
    headers: { "Content-Type": "application/json" },
  });
}

export async function POST({ request }: APIEvent) {
  const body = await request.json();
  const user = await db.user.create({ data: body });
  return new Response(JSON.stringify(user), {
    status: 201,
    headers: { "Content-Type": "application/json" },
  });
}
```

```ts
// src/routes/api/users/[id].ts
export async function GET({ params }: APIEvent) {
  const user = await db.user.findUnique({
    where: { id: Number(params.id) },
  });
  if (!user) {
    return new Response("Not found", { status: 404 });
  }
  return new Response(JSON.stringify(user));
}

export async function PATCH({ params, request }: APIEvent) { /* ... */ }
export async function DELETE({ params }: APIEvent) { /* ... */ }
```

### Когда API routes vs server functions

| Случай | Использовать |
|---|---|
| Внутреннее API для своего фронта | server functions |
| Public REST API для внешних клиентов | API routes |
| Webhooks | API routes |
| WebSockets/SSE | API routes |
| Простые CRUD из своего UI | server functions |

---

## 110. SSR / SSG / SPA стратегии рендера

### SSR (Server-Side Rendering) — по умолчанию

```ts
// app.config.ts
export default defineConfig({
  ssr: true,
});
```

Каждый запрос рендерится на сервере. Хорошо для:
- Динамический контент (новости, e-commerce)
- Авторизованные страницы
- SEO с актуальными данными

### SSG (Static Site Generation)

Пре-рендер всех страниц при build:

```bash
pnpm build
# Если ssr: true и роуты статичные → автоматический pre-render
```

Хорошо для:
- Лендинги, маркетинговые страницы
- Блоги
- Документация

### SPA (Single Page Application)

```ts
export default defineConfig({
  ssr: false,
});
```

Только клиентский рендер. Минимальный сервер. Хорошо для:
- Дашборды с авторизацией (SEO не важен)
- Внутренние инструменты
- PWA

### Mixed — разные стратегии для разных роутов

В SolidStart можно указывать `ssr` для конкретных роутов через `route` экспорт. См. документацию для актуального синтаксиса.

---

## 111. Streaming и Suspense на сервере

`<Suspense>` на сервере работает как streaming:

```tsx
export default function Page() {
  return (
    <div>
      <h1>Главная</h1>
      <p>Этот контент рендерится сразу</p>
      
      <Suspense fallback={<p>Загрузка постов...</p>}>
        <PostsList /> {/* createResource внутри */}
      </Suspense>
      
      <Suspense fallback={<p>Загрузка рекомендаций...</p>}>
        <Recommendations />
      </Suspense>
    </div>
  );
}
```

### Как работает на сервере

1. Сервер сразу отправляет HTML с fallbacks
2. Браузер начинает рендер
3. Когда async данные готовы — сервер дописывает HTML
4. Клиент заменяет fallback реальным контентом

Это **streaming SSR** — пользователь видит контент по мере готовности, а не ждёт полный рендер.

### Диаграмма streaming SSR

```
  Browser                Network              Server / SolidStart
   ────                   ─────                 ─────────────────
                                                
                                                ┌──────────────────┐
   GET / ─────────────────────────────────────► │ Route matched    │
                                                │ Component starts │
                                                │ rendering        │
                                                └─────────┬────────┘
                                                          │
                                                ┌─────────▼────────┐
                                                │ Static parts     │
                                                │ rendered:        │
                                                │  <h1>Title</h1>  │
                                                │  <Suspense>      │
                                                │   fallback...    │
                                                │  </Suspense>     │
                                                └─────────┬────────┘
                                                          │
   ◄──── HTML chunk 1 ──── HTML chunk 1 ◄─────────────────┤
                                                          │
   ┌─────────────────────┐                                │
   │ User sees:          │                       ┌────────▼────────┐
   │  <h1>Title</h1>     │                       │ createResource  │
   │  <spinner/>         │                       │ awaiting...     │
   │  <spinner/>         │                       │   ├─ posts      │
   └─────────────────────┘                       │   └─ recs       │
                                                 └────────┬────────┘
                                                          │
                                          ┌───────────────┘
                                          │
                              posts done  ▼
                                                 ┌─────────────────┐
                                                 │ <script>        │
                                                 │  inject posts   │
                                                 │  HTML into DOM  │
                                                 │ </script>       │
                                                 └────────┬────────┘
   ◄──── HTML chunk 2 ──── HTML chunk 2 ◄─────────────────┤
                                                          │
   ┌─────────────────────┐                                │
   │ User sees:          │                                │
   │  <h1>Title</h1>     │                                │
   │  <PostList/>     ✓  │             recommendations ──┤
   │  <spinner/>         │              done              │
   └─────────────────────┘                                │
                                                 ┌────────▼────────┐
                                                 │ <script>        │
                                                 │  inject recs    │
                                                 │  HTML into DOM  │
                                                 │ </script>       │
                                                 └────────┬────────┘
   ◄──── HTML chunk 3 ──── HTML chunk 3 ◄─────────────────┤
                                                          │
   ┌─────────────────────┐                       ┌────────▼────────┐
   │ User sees:          │                       │ Stream closed   │
   │  <h1>Title</h1>     │                       │ Connection done │
   │  <PostList/>     ✓  │                       └─────────────────┘
   │  <Recs/>         ✓  │
   └─────────────────────┘
```

**Ключевые моменты:**
- Каждый `<Suspense>` — это точка где сервер может приостановить streaming и отправить готовое до этого момента
- Клиент НЕ знает что данные стримились — для него это обычный HTML, JS просто заменяет fallback content
- Если у тебя 3 параллельных `<Suspense>` границы и одна из них медленная — остальные не ждут

### Конфигурация

```ts
export default defineConfig({
  ssr: "async", // streaming SSR с Suspense
});
```

---

## 112. Deploy: Vercel, Netlify, Cloudflare, Node

Адаптеры конфигурируются в `app.config.ts`:

### Vercel

```ts
export default defineConfig({
  server: { preset: "vercel" },
});
```

Git push → автодеплой.

### Netlify

```ts
export default defineConfig({
  server: { preset: "netlify" },
});
```

### Cloudflare Workers

```ts
export default defineConfig({
  server: { preset: "cloudflare-pages" },
  // или
  // server: { preset: "cloudflare-workers" },
});
```

Edge runtime — очень быстро. Но есть ограничения (нет Node.js APIs, размер бандла).

### Node.js (свой сервер)

```ts
export default defineConfig({
  server: { preset: "node-server" },
});
```

```bash
pnpm build
node .output/server/index.mjs
```

### Static (только HTML)

```ts
export default defineConfig({
  server: { preset: "static" },
  ssr: true, // пре-рендер при build
});
```

Получается папка с HTML/JS/CSS, хостишь на любом CDN.

### Bun

```ts
export default defineConfig({
  server: { preset: "bun" },
});
```

### Docker

Стандартный Node deploy:
```dockerfile
FROM node:20-alpine
WORKDIR /app
COPY . .
RUN npm install && npm run build
EXPOSE 3000
CMD ["node", ".output/server/index.mjs"]
```

---
---
---

# Часть XX — Экосистема

## 113. Kobalte

Headless UI компоненты для SolidJS. Аналог Radix/Headless UI для React.

```bash
pnpm add @kobalte/core
```

### Что включено

- Dialog (модалки)
- Dropdown menu
- Combobox (autocomplete)
- Tabs
- Accordion
- Toast
- Toggle, Switch
- Slider
- DatePicker
- Tooltip, Popover
- и много других

### Пример — Dialog

```tsx
import { Dialog } from "@kobalte/core/dialog";

const App: Component = () => {
  return (
    <Dialog>
      <Dialog.Trigger class="bg-blue-500 text-white px-4 py-2 rounded">
        Открыть
      </Dialog.Trigger>
      <Dialog.Portal>
        <Dialog.Overlay class="fixed inset-0 bg-black/50" />
        <Dialog.Content class="fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 bg-white p-6 rounded">
          <Dialog.Title class="text-xl font-bold">Заголовок</Dialog.Title>
          <Dialog.Description>Описание</Dialog.Description>
          <Dialog.CloseButton>Закрыть</Dialog.CloseButton>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog>
  );
};
```

Kobalte даёт правильное поведение (focus management, ARIA, keyboard nav) — ты только стилизуешь.

### Когда использовать

- Любой production UI с серьёзными требованиями к accessibility
- Когда нужны сложные компоненты (combobox, datepicker)
- В сочетании с Tailwind/UnoCSS

---

## 114. Solid Primitives

Коллекция полезных primitives. Аналог `react-use`.

```bash
pnpm add @solid-primitives/storage
pnpm add @solid-primitives/scheduled
pnpm add @solid-primitives/intersection-observer
# и другие
```

### Самые полезные

- `@solid-primitives/storage` — localStorage/sessionStorage
- `@solid-primitives/scheduled` — debounce, throttle
- `@solid-primitives/intersection-observer`
- `@solid-primitives/media` — matchMedia, prefers-color-scheme
- `@solid-primitives/keyboard` — keyboard shortcuts
- `@solid-primitives/event-listener` — реактивные listeners
- `@solid-primitives/mouse` — позиция мыши
- `@solid-primitives/clipboard` — буфер обмена

### Пример

```tsx
import { makePersisted } from "@solid-primitives/storage";

const [theme, setTheme] = makePersisted(
  createSignal<"light" | "dark">("light"),
  { name: "theme" }
);
// Автоматически сохраняется в localStorage
```

```tsx
import { debounce } from "@solid-primitives/scheduled";

const [query, setQuery] = createSignal("");
const debouncedSearch = debounce((q: string) => search(q), 300);

createEffect(() => {
  debouncedSearch(query());
});
```

---

## 115. TanStack Query for Solid

Управление серверным состоянием. Аналог react-query для React.

```bash
pnpm add @tanstack/solid-query
```

### Setup

```tsx
import { QueryClient, QueryClientProvider } from "@tanstack/solid-query";

const queryClient = new QueryClient();

const App: Component = () => (
  <QueryClientProvider client={queryClient}>
    <YourApp />
  </QueryClientProvider>
);
```

### Использование

```tsx
import { createQuery } from "@tanstack/solid-query";

const UserProfile: Component<{ userId: number }> = (props) => {
  const query = createQuery(() => ({
    queryKey: ["user", props.userId],
    queryFn: () => fetch(`/api/users/${props.userId}`).then((r) => r.json()),
    staleTime: 1000 * 60 * 5,  // 5 минут
  }));
  
  return (
    <Switch>
      <Match when={query.isPending}>
        <p>Загрузка...</p>
      </Match>
      <Match when={query.isError}>
        <p>Ошибка: {query.error?.message}</p>
      </Match>
      <Match when={query.data}>
        <div>{query.data!.name}</div>
      </Match>
    </Switch>
  );
};
```

### Mutations

```tsx
import { createMutation } from "@tanstack/solid-query";

const Form: Component = () => {
  const queryClient = useQueryClient();
  
  const mutation = createMutation(() => ({
    mutationFn: (data: NewPost) =>
      fetch("/api/posts", { method: "POST", body: JSON.stringify(data) }),
    onSuccess: () => {
      queryClient.invalidateQueries({ queryKey: ["posts"] });
    },
  }));
  
  const handleSubmit = () => {
    mutation.mutate({ title: "Test", body: "..." });
  };
};
```

### Когда использовать

- Сложное серверное состояние (кеширование, invalidation, optimistic updates)
- Множество мест где нужны те же данные
- Pagination, infinite scroll
- Real-time data с интервальным polling

Для простых случаев — обычного `createResource` достаточно. Если используешь SolidStart — `query` + `createAsync` решают большинство задач.

---
---

# Часть XXI — Анти-паттерны (НОВАЯ)

## 116. Деструктуризация props

**Анти-паттерн:**

```tsx
const Button: Component<{ label: string; onClick: () => void }> = ({ label, onClick }) => {
  return <button onClick={onClick}>{label}</button>;
};
```

**Правильно:**

```tsx
const Button: Component<{ label: string; onClick: () => void }> = (props) => {
  return <button onClick={props.onClick}>{props.label}</button>;
};
```

### Почему деструктуризация ломает реактивность

`props` в SolidJS — это **прокси-объект**. Когда читаешь `props.label`, под капотом срабатывает getter, который создаёт реактивную подписку.

Когда ты деструктурируешь `{ label }` — getter вызывается ОДИН раз при монтировании компонента. Дальше переменная `label` навсегда хранит то значение которое было в момент монтирования. Изменения родителя ты не увидишь.

### Когда деструктуризация допустима

```tsx
// ✅ В render prop callbacks — это уже не props, это аргумент колбэка
<For each={items()}>
  {(item, index) => {
    // item — обычная переменная, не proxy
    const { name, age } = item; // OK
    return <div>{name}</div>;
  }}
</For>
```

```tsx
// ✅ Если ты УВЕРЕН что значение не будет меняться
const Component: Component<{ initialValue: number }> = (props) => {
  // initialValue по контракту не меняется после монтирования
  const initial = props.initialValue; // OK
  // ...
};
```

### Сложные случаи

```tsx
// ❌ Скрытая деструктуризация через rest
const Card: Component<CardProps> = ({ title, ...rest }) => {
  // title — не реактивен, rest — частично реактивен
  return <div {...rest}>{title}</div>;
};

// ✅ Через splitProps
const Card: Component<CardProps> = (props) => {
  const [local, others] = splitProps(props, ["title"]);
  return <div {...others}>{local.title}</div>;
};
```

---

## 117. Сигналы вне реактивного скоупа

**Анти-паттерн:**

```tsx
// Где-то на верхнем уровне модуля
const [globalCounter] = createSignal(0);

// Создан вне createRoot или компонента → warning + утечка
```

**Правильно:**

```tsx
// ✅ Глобальный сигнал — в createRoot
import { createRoot, createSignal } from "solid-js";

export const counter = createRoot(() => {
  const [value, setValue] = createSignal(0);
  return { value, setValue };
});

// Использование
counter.value();
counter.setValue(5);
```

```tsx
// ✅ Сигналы внутри компонента — там есть owner
const Component: Component = () => {
  const [value] = createSignal(0); // OK
  return <div />;
};
```

### Warning который ты увидишь

```
computations created outside a `createRoot` or `render` will never be run
```

### В async коде

```tsx
const Component: Component = () => {
  const handleClick = async () => {
    await sleep(1000);
    // ❌ После await owner потерян
    createEffect(() => { /* ... */ });
  };
};

// ✅ Сохранить owner и использовать runWithOwner
const Component: Component = () => {
  const owner = getOwner();
  
  const handleClick = async () => {
    await sleep(1000);
    runWithOwner(owner, () => {
      createEffect(() => { /* ... */ });
    });
  };
};
```

---

## 118. Эффекты вместо мемо

**Анти-паттерн:**

```tsx
const [first, setFirst] = createSignal("");
const [last, setLast] = createSignal("");
const [fullName, setFullName] = createSignal("");

createEffect(() => {
  setFullName(`${first()} ${last()}`);
});
```

**Правильно:**

```tsx
const fullName = createMemo(() => `${first()} ${last()}`);
```

### Почему мемо лучше эффекта для вычислений

1. **Меньше шагов** — одна функция вместо трёх
2. **Атомарно** — синхронное обновление, нет промежуточного состояния
3. **Кэширование** — пересчёт только при изменении зависимостей
4. **Equals из коробки** — не пересчитывается если значение не изменилось

### Правило

- Производное от сигналов **значение** → `createMemo`
- Side effect (DOM, fetch, console.log) → `createEffect`

---

## 119. Перебор с подписками

**Анти-паттерн:**

```tsx
createEffect(() => {
  const allData = {
    user: user(),
    posts: posts(),
    comments: comments(),
    likes: likes(),
    settings: settings(),
  };
  
  saveAll(allData); // вызывается при изменении ЛЮБОГО из 5 сигналов
});
```

**Правильно:**

```tsx
// Разделить по интересам
createEffect(() => saveUser(user()));
createEffect(() => savePosts(posts()));
createEffect(() => saveComments(comments()));
// ...
```

Или если действительно нужно всё вместе:

```tsx
// Объединить через store
const [state, setState] = createStore({ user: ..., posts: ..., /* ... */ });

createEffect(() => {
  saveAll(unwrap(state));
});
// Тоже подписка на всё, но через store можно делать batched updates
```

### Что мерить

В Solid Devtools посмотри частоту срабатывания эффекта. Если он срабатывает чаще чем тебе нужно — у тебя лишние подписки.

---

## 120. Index когда нужен For (и наоборот)

### Для динамичных списков — \<For\>

```tsx
const [todos, setTodos] = createSignal<Todo[]>([]);

// ✅ For — переставляются по value (id)
<For each={todos()}>
  {(todo) => <TodoItem todo={todo} />}
</For>
```

При добавлении/удалении/перестановке — DOM элементы переиспользуются. Компонент `TodoItem` для конкретного todo не пересоздаётся.

### Для статичных списков — \<Index\>

```tsx
const [chartData] = createSignal<number[]>([10, 20, 30, 40]);

// ✅ Index — индекс стабилен, меняются только значения
<Index each={chartData()}>
  {(value, i) => <Bar height={value()} />}
</Index>
```

### Что произойдёт если перепутать

**For для статичных данных (плохо):**
```tsx
<For each={[1, 2, 3]}>
  {(n) => <div>{n}</div>}
</For>

// Изменим на [3, 2, 1]
// → SolidJS пересоздаст DOM узлы (key изменился)
```

**Index для динамичных данных (плохо):**
```tsx
<Index each={todos()}>
  {(todo) => <TodoItem todo={todo()} />}
</Index>

// Удалим первый элемент
// → Index думает что у первой позиции просто изменился value
// → Компонент TodoItem #0 будет показывать данные TodoItem #1
// → Все TodoItem пересоздадутся (потеряют локальный state)
```

### Простое правило

- Массив будет переставляться/фильтроваться/добавляться → **`<For>`**
- Массив только меняет значения по фиксированным позициям → **`<Index>`**

В сомнениях используй `<For>`.

---

## 121. Прямая мутация store

**Анти-паттерн:**

```tsx
const [store] = createStore({ user: { name: "Jesus" } });

// ❌ Прямая мутация — реактивность не сработает
store.user.name = "Ivan"; 
// или
store.todos.push(newTodo);
```

**Правильно:**

```tsx
// ✅ Через setStore с путём
setStore("user", "name", "Ivan");

// ✅ Или через produce
setStore(produce((s) => {
  s.user.name = "Ivan";
  s.todos.push(newTodo);
}));
```

### Почему

Store работает через прокси. Чтобы заметить мутацию — нужно использовать setStore, который проходит через тот же прокси с информацией о трекинге.

### Исключение — createMutable

```tsx
import { createMutable } from "solid-js/store";

const state = createMutable({ count: 0 });
state.count++; // OK — createMutable специально для этого
```

Но createMutable редко используют. См. раздел 41.

---

## 122. Забытый onCleanup

**Анти-паттерн:**

```tsx
const Component: Component = () => {
  onMount(() => {
    const id = setInterval(() => console.log("tick"), 1000);
    // ❌ Нет onCleanup — интервал продолжит работать после размонтирования
  });
};
```

**Правильно:**

```tsx
const Component: Component = () => {
  onMount(() => {
    const id = setInterval(() => console.log("tick"), 1000);
    onCleanup(() => clearInterval(id));
  });
};
```

### Что обязательно нужно очищать

1. **setInterval / setTimeout** → clearInterval / clearTimeout
2. **addEventListener** → removeEventListener
3. **WebSocket** → close()
4. **EventSource** → close()
5. **fetch с AbortController** → abort()
6. **IntersectionObserver / ResizeObserver / MutationObserver** → disconnect()
7. **Подписки из библиотек** (RxJS, etc.) → unsubscribe()
8. **Анимации** → cancelAnimationFrame

### Симптомы утечек

- Приложение замедляется при долгом использовании
- В Chrome DevTools Memory растёт
- Дублирование событий (один и тот же event handler срабатывает несколько раз)

### Как найти

В DevTools Memory:
1. Take snapshot
2. Сделать действие которое создаёт компонент
3. Закрыть компонент
4. Take snapshot
5. Сравнить

Если в новом snapshot остались объекты которых не должно быть — утечка.

---
---
---

# Часть XXII — Практика и справочники

## 123. Финальный проект — блог с авторизацией

Полное приложение собирает всё что прошли: SolidStart с file-based routing, server functions, actions, createResource, Suspense, формы с валидацией, auth через cookies, БД через Prisma, UnoCSS.

### Структура проекта

```
blog/
├── prisma/
│   ├── schema.prisma
│   └── seed.ts
├── src/
│   ├── lib/
│   │   ├── db.ts
│   │   ├── auth.ts
│   │   ├── posts.ts
│   │   └── users.ts
│   ├── components/
│   │   ├── Header.tsx
│   │   ├── PostCard.tsx
│   │   └── ErrorMessage.tsx
│   ├── routes/
│   │   ├── index.tsx                  # лента постов
│   │   ├── login.tsx                  # форма логина
│   │   ├── register.tsx               # форма регистрации
│   │   ├── posts/
│   │   │   ├── [id].tsx               # просмотр поста
│   │   │   └── new.tsx                # создание поста
│   │   └── api/
│   │       └── posts/[id].ts          # REST endpoint
│   ├── app.tsx
│   ├── entry-client.tsx
│   ├── entry-server.tsx
│   └── middleware.ts                  # auth middleware
├── app.config.ts
└── package.json
```

### Prisma schema

```prisma
// prisma/schema.prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

model User {
  id        Int      @id @default(autoincrement())
  email     String   @unique
  name      String
  password  String
  posts     Post[]
  sessions  Session[]
  createdAt DateTime @default(now())
}

model Post {
  id        Int      @id @default(autoincrement())
  title     String
  body      String   @db.Text
  author    User     @relation(fields: [authorId], references: [id])
  authorId  Int
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}

model Session {
  id        String   @id @default(cuid())
  user      User     @relation(fields: [userId], references: [id], onDelete: Cascade)
  userId    Int
  expiresAt DateTime
}
```

### Auth helpers

```ts
// src/lib/auth.ts
"use server";

import { getRequestEvent } from "solid-js/web";
import { getCookie, setCookie, deleteCookie } from "vinxi/http";
import bcrypt from "bcrypt";
import { db } from "./db";

export async function getCurrentUser() {
  const event = getRequestEvent();
  if (!event) return null;
  
  const sessionId = getCookie(event.nativeEvent, "session");
  if (!sessionId) return null;
  
  const session = await db.session.findUnique({
    where: { id: sessionId },
    include: { user: true },
  });
  
  if (!session || session.expiresAt < new Date()) {
    return null;
  }
  
  return session.user;
}

export async function loginUser(email: string, password: string) {
  const user = await db.user.findUnique({ where: { email } });
  if (!user) throw new Error("Неверные данные");
  
  const valid = await bcrypt.compare(password, user.password);
  if (!valid) throw new Error("Неверные данные");
  
  const session = await db.session.create({
    data: {
      userId: user.id,
      expiresAt: new Date(Date.now() + 30 * 24 * 60 * 60 * 1000),
    },
  });
  
  const event = getRequestEvent()!;
  setCookie(event.nativeEvent, "session", session.id, {
    httpOnly: true,
    secure: process.env.NODE_ENV === "production",
    sameSite: "lax",
    maxAge: 30 * 24 * 60 * 60,
  });
}

export async function logoutUser() {
  const event = getRequestEvent();
  if (!event) return;
  
  const sessionId = getCookie(event.nativeEvent, "session");
  if (sessionId) {
    await db.session.delete({ where: { id: sessionId } }).catch(() => {});
  }
  deleteCookie(event.nativeEvent, "session");
}

export async function registerUser(email: string, name: string, password: string) {
  const existing = await db.user.findUnique({ where: { email } });
  if (existing) throw new Error("Email уже занят");
  
  const hashed = await bcrypt.hash(password, 10);
  await db.user.create({
    data: { email, name, password: hashed },
  });
}
```

### Главная страница

```tsx
// src/routes/index.tsx
import { Title } from "@solidjs/meta";
import { createAsync, query } from "@solidjs/router";
import { For, Suspense, Show } from "solid-js";
import PostCard from "~/components/PostCard";
import { db } from "~/lib/db";
import { getCurrentUser } from "~/lib/auth";

const getPosts = query(async () => {
  "use server";
  return await db.post.findMany({
    orderBy: { createdAt: "desc" },
    include: { author: true },
    take: 20,
  });
}, "getPosts");

const getUser = query(async () => {
  "use server";
  return await getCurrentUser();
}, "getUser");

export const route = {
  preload: () => {
    void getPosts();
    void getUser();
  },
};

export default function HomePage() {
  const posts = createAsync(() => getPosts());
  const user = createAsync(() => getUser());
  
  return (
    <>
      <Title>Блог</Title>
      <div class="max-w-2xl mx-auto p-4">
        <Suspense fallback={<p>Загрузка...</p>}>
          <Show when={user()}>
            <a
              href="/posts/new"
              class="inline-block mb-4 bg-blue-500 text-white px-4 py-2 rounded"
            >
              + Новый пост
            </a>
          </Show>
          
          <For each={posts()}>
            {(post) => <PostCard post={post} />}
          </For>
        </Suspense>
      </div>
    </>
  );
}
```

### Логин страница

```tsx
// src/routes/login.tsx
import { action, redirect, useSubmission } from "@solidjs/router";
import { loginUser } from "~/lib/auth";
import { Show } from "solid-js";

const login = action(async (formData: FormData) => {
  "use server";
  const email = formData.get("email") as string;
  const password = formData.get("password") as string;
  
  try {
    await loginUser(email, password);
  } catch (err) {
    return { error: (err as Error).message };
  }
  
  throw redirect("/");
});

export default function LoginPage() {
  const submission = useSubmission(login);
  
  return (
    <div class="max-w-md mx-auto p-8">
      <h1 class="text-2xl font-bold mb-6">Вход</h1>
      
      <form action={login} method="post" class="space-y-4">
        <input
          name="email"
          type="email"
          required
          placeholder="Email"
          class="w-full border rounded px-3 py-2"
        />
        <input
          name="password"
          type="password"
          required
          placeholder="Пароль"
          class="w-full border rounded px-3 py-2"
        />
        
        <Show when={submission.result?.error}>
          <p class="text-red-500 text-sm">{submission.result!.error}</p>
        </Show>
        
        <button
          type="submit"
          disabled={submission.pending}
          class="w-full bg-blue-500 text-white py-2 rounded disabled:opacity-50"
        >
          {submission.pending ? "Вход..." : "Войти"}
        </button>
        
        <p class="text-sm text-center">
          Нет аккаунта? <a href="/register" class="text-blue-500">Регистрация</a>
        </p>
      </form>
    </div>
  );
}
```

### Создание поста

```tsx
// src/routes/posts/new.tsx
import { action, redirect } from "@solidjs/router";
import { db } from "~/lib/db";
import { getCurrentUser } from "~/lib/auth";

const createPost = action(async (formData: FormData) => {
  "use server";
  const user = await getCurrentUser();
  if (!user) throw redirect("/login");
  
  const title = (formData.get("title") as string).trim();
  const body = (formData.get("body") as string).trim();
  
  if (!title || !body) return { error: "Все поля обязательны" };
  
  const post = await db.post.create({
    data: { title, body, authorId: user.id },
  });
  
  throw redirect(`/posts/${post.id}`);
});

export default function NewPostPage() {
  return (
    <div class="max-w-2xl mx-auto p-4">
      <h1 class="text-2xl font-bold mb-4">Новый пост</h1>
      <form action={createPost} method="post" class="space-y-4">
        <input
          name="title"
          required
          placeholder="Заголовок"
          class="w-full border rounded px-3 py-2"
        />
        <textarea
          name="body"
          required
          rows={10}
          placeholder="Содержимое..."
          class="w-full border rounded px-3 py-2"
        />
        <button
          type="submit"
          class="bg-blue-500 text-white px-6 py-2 rounded"
        >
          Опубликовать
        </button>
      </form>
    </div>
  );
}
```

### Просмотр поста

```tsx
// src/routes/posts/[id].tsx
import { createAsync, query, useParams } from "@solidjs/router";
import { Suspense, Show } from "solid-js";
import { db } from "~/lib/db";

const getPost = query(async (id: number) => {
  "use server";
  return await db.post.findUnique({
    where: { id },
    include: { author: true },
  });
}, "getPost");

export const route = {
  preload: ({ params }) => {
    void getPost(Number(params.id));
  },
};

export default function PostPage() {
  const params = useParams<{ id: string }>();
  const post = createAsync(() => getPost(Number(params.id)));
  
  return (
    <Suspense fallback={<p>Загрузка...</p>}>
      <Show when={post()} fallback={<p>Пост не найден</p>}>
        {(post) => (
          <article class="max-w-2xl mx-auto p-4">
            <h1 class="text-3xl font-bold mb-2">{post().title}</h1>
            <p class="text-gray-500 mb-4">
              Автор: {post().author.name} •{" "}
              {new Date(post().createdAt).toLocaleDateString()}
            </p>
            <div class="prose">{post().body}</div>
          </article>
        )}
      </Show>
    </Suspense>
  );
}
```

Полный код проекта — около 700-1000 строк. Здесь даны ключевые файлы; остальное собирается по шаблону. Это можно использовать как стартер для своих проектов.

---

## 124. Структура проекта в продакшене

### Хорошая структура для среднего проекта

```
src/
├── routes/                  ← роуты (file-based)
│   ├── (marketing)/         ← группа без префикса в URL
│   │   ├── index.tsx
│   │   ├── about.tsx
│   │   └── pricing.tsx
│   ├── (app)/               ← авторизованная зона
│   │   ├── dashboard.tsx
│   │   └── settings.tsx
│   ├── login.tsx
│   └── api/
├── components/
│   ├── ui/                  ← переиспользуемые UI (Button, Input, Card)
│   ├── layouts/             ← лэйауты
│   └── features/            ← бизнес-компоненты (PostCard, UserAvatar)
├── lib/
│   ├── db.ts                ← клиент БД
│   ├── auth.ts              ← auth helpers
│   ├── api/                 ← API клиент (если есть внешнее API)
│   └── utils/               ← утилиты
├── context/                 ← Context провайдеры (Auth, Theme)
├── primitives/              ← custom primitives (createDebounced, etc.)
├── types/                   ← shared TypeScript типы
└── styles/                  ← глобальные стили
```

### Принципы

1. **routes — только роуты** (page компоненты)
2. **components — без бизнес-логики**, переиспользуемые
3. **lib — серверная логика** (с "use server" где надо)
4. **Бизнес-логика отдельно от UI**

### Naming conventions

- Компоненты — PascalCase (`UserCard.tsx`)
- Утилиты — camelCase (`formatDate.ts`)
- Хуки/primitives — `createXxx.ts`
- Типы — отдельно (`types/user.ts`)

### Alias импортов

В `tsconfig.json`:
```json
{
  "compilerOptions": {
    "paths": {
      "~/*": ["./src/*"]
    }
  }
}
```

В `app.config.ts` (для Vite):
```ts
export default defineConfig({
  vite: {
    resolve: {
      alias: { "~": "/src" },
    },
  },
});
```

Использование: `import { db } from "~/lib/db"` вместо `import { db } from "../../../lib/db"`.

---

## 125. Полная шпаргалка API

### Реактивность

```tsx
// Сигналы
const [value, setValue] = createSignal(initial);
const [value, setValue] = createSignal(initial, { equals: false });

// Мемо
const computed = createMemo(() => value() * 2);

// Эффекты
createEffect(() => { /* side effect */ });
createRenderEffect(() => { /* during render */ });
createComputed(() => { /* synchronous */ });
createDeferred(source, { timeoutMs: 250 });
createReaction(() => { /* one-time */ });
createSelector(value);

// Утилиты
untrack(() => value());                  // read without subscribing
batch(() => { setA(1); setB(2); });      // group updates
on(source, fn, { defer: true });         // explicit deps
```

### Lifecycle

```tsx
onMount(() => { /* after mount */ });
onCleanup(() => { /* before unmount */ });
onError((err) => { /* errors in reactive */ });
```

### Stores

```tsx
const [store, setStore] = createStore(initial);

// Updates
setStore("path", "to", "field", value);
setStore("array", (i) => i > 0, "field", value); // by predicate
setStore("array", {}, "field", value);            // all
setStore(produce((s) => { /* mutate */ }));
setStore(reconcile(newData, { key: "id" }));

const plain = unwrap(store);

// createMutable
const state = createMutable(initial);
state.foo = "bar"; // direct mutation works
```

### Control flow

```tsx
<Show when={cond} fallback={<Fallback />}>
  {(value) => <Content value={value()} />}
</Show>

<For each={items()}>
  {(item, index) => <Item item={item} />}
</For>

<Index each={items()}>
  {(item, index) => <Item item={item()} />}
</Index>

<Switch fallback={<Default />}>
  <Match when={cond1}>...</Match>
  <Match when={cond2}>...</Match>
</Switch>

<ErrorBoundary fallback={(err, reset) => <Error />}>
  ...
</ErrorBoundary>

<Suspense fallback={<Loader />}>
  ...
</Suspense>

<Dynamic component={Component} {...props} />
<Portal mount={el}>...</Portal>
```

### Resources

```tsx
const [data, { mutate, refetch }] = createResource(fetcher);
const [data] = createResource(source, fetcher);

data();           // T | undefined
data.loading;     // boolean
data.error;       // any
data.state;       // "unresolved" | "pending" | "ready" | "refreshing" | "errored"
```

### Props

```tsx
import { mergeProps, splitProps } from "solid-js";

const props = mergeProps({ defaultProp: "value" }, rawProps);
const [local, others] = splitProps(props, ["myProp"]);
```

### Children

```tsx
import { children } from "solid-js";
const resolved = children(() => props.children);
```

### Context

```tsx
const Ctx = createContext<Value>();
<Ctx.Provider value={...}>...</Ctx.Provider>
const value = useContext(Ctx);
```

### Router (@solidjs/router)

```tsx
import { Router, Route, A, useParams, useNavigate, useLocation, useSearchParams } from "@solidjs/router";

<Router>
  <Route path="/" component={Home} />
  <Route path="/users/:id" component={UserPage} />
</Router>

const params = useParams<{ id: string }>();
const navigate = useNavigate();
const location = useLocation();
const [params, setParams] = useSearchParams();

<A href="/about" activeClass="text-blue-500">About</A>
```

### SolidStart

```tsx
import { query, action, createAsync, useAction, useSubmission, redirect } from "@solidjs/router";

const getData = query(async () => { "use server"; return data; }, "key");
const myAction = action(async (formData) => { "use server"; /* ... */ });

const data = createAsync(() => getData());
const submission = useSubmission(myAction);
```

---

## 126. UnoCSS шпаргалка

### Layout

```
flex / grid / block / inline-block / hidden
flex-row / flex-col / flex-wrap
items-center / items-start / items-end
justify-center / justify-between / justify-around
gap-{0|1|2|3|4|6|8}
```

### Sizing

```
w-{0|4|8|...|full|screen}
h-{0|4|8|...|full|screen}
min-w-{0|full|max} / max-w-{xs|sm|md|lg|xl|2xl}
min-h-{0|screen} / max-h-{full|screen}
```

### Spacing

```
p-{0|1|2|3|4|6|8}              padding all
px-{n} / py-{n}                 padding horizontal/vertical
pt-{n} / pr-{n} / pb-{n} / pl-{n}

m-{n} / mx-{n} / my-{n} / mt-{n} ...

space-x-{n} / space-y-{n}       spacing between children
```

### Colors

```
text-{red|blue|green|gray|...}-{50|100|200|...|900}
bg-{color}-{shade}
border-{color}-{shade}
```

### Typography

```
text-{xs|sm|base|lg|xl|2xl|3xl}
font-{light|normal|medium|semibold|bold}
italic / underline / line-through
text-{left|center|right|justify}
leading-{none|tight|normal|loose}
```

### Borders & Radius

```
border / border-{2|4} / border-t / border-x ...
border-{color}-{shade}
rounded / rounded-{sm|md|lg|xl|full}
```

### Effects

```
shadow / shadow-{sm|md|lg|xl|2xl}
opacity-{0|25|50|75|100}
hover:bg-blue-600 / focus:ring-2 / active:scale-95
transition / transition-all / duration-{150|200|300|500}
```

### Position

```
relative / absolute / fixed / sticky
top-{n} / right-{n} / bottom-{n} / left-{n}
inset-0  (top/right/bottom/left: 0)
z-{0|10|20|30|40|50}
```

### Display logic

```
hidden md:block          mobile hidden, ≥768px visible
flex md:grid             mobile flex, ≥768px grid
text-sm md:text-base lg:text-lg     responsive font
```

### Responsive prefixes

```
sm:  ≥640px
md:  ≥768px
lg:  ≥1024px
xl:  ≥1280px
2xl: ≥1536px
```

### State variants

```
hover: focus: active: disabled: visited:
group-hover: peer-focus:
dark: light:    (если есть dark mode)
first: last: odd: even:
```

### Полезные комбинации

```
mx-auto              центрирование блока по горизонтали
my-auto              центрирование по вертикали (внутри flex)

flex items-center justify-center    центр по обеим осям

grid place-items-center             то же через grid

space-y-4                           вертикальные отступы между детьми

backdrop-blur-sm                    размытие фона (для модалок)
```

---

## 127. Частые ошибки и решения

### Ошибка: эффект не реагирует на сигнал

**Признак:** сигнал меняется, эффект не запускается

**Чек-лист:**
1. Сигнал вызывается со скобками? `count()`, не `count`
2. Props не деструктурируются? `props.value`, не `{ value }`
3. Эффект внутри owner? (в компоненте или createRoot)
4. После await не потерян owner? (см. runWithOwner)

### Ошибка: "computations created outside createRoot will never be run"

**Причина:** реактивный примитив создан вне owner.

**Решение:** обернуть в `createRoot` или вызывать только внутри компонента.

```tsx
// ❌
const [count] = createSignal(0); // на верхнем уровне модуля

// ✅
const { count } = createRoot(() => {
  const [count] = createSignal(0);
  return { count };
});
```

### Ошибка: бесконечный цикл

**Причина:** сигнал устанавливается в эффекте который его читает.

```tsx
// ❌
createEffect(() => {
  setCount(count() + 1);
});
```

**Решение:** для производных значений — `createMemo`. Для обновления другого сигнала — добавь условие или `untrack`.

### Ошибка: For рендерит компоненты заново при изменении массива

**Причина:** массив пересоздаётся с теми же значениями но другими ссылками.

```tsx
// ❌ Новые объекты, key=value сравнение не работает
setItems(items().map((i) => ({ ...i, updated: true })));
```

**Решение:** использовать store для inplace обновлений, или передавать стабильные ссылки.

### Ошибка: Suspense не показывает fallback

**Причина:** ресурс уже загружен (например, был preloaded).

**Решение:** проверь `data.state` или `data.loading` напрямую если нужен detailed контроль.

### Ошибка: формы не работают на сервере (SolidStart)

**Признак:** Action работает с JS, без JS — белая страница / 404.

**Чек-лист:**
1. Форма имеет `action={myAction}` и `method="post"`?
2. Action возвращает данные или редирект (не undefined)?
3. SSR включён в `app.config.ts`?

### Ошибка: TypeScript не видит реактивный тип

```tsx
// ❌ TS думает что user — User, не Accessor<User>
const { user } = useAuth();
user.name; // ошибка типа

// ✅
const { user } = useAuth();
user().name; // OK — user это Accessor
```

### Ошибка: store обновление не вызывает реактивность

**Причина:** прямая мутация без setStore.

```tsx
// ❌
store.user.name = "Ivan";

// ✅
setStore("user", "name", "Ivan");
```

### Ошибка: ref undefined в onMount

**Причина:** компонент условно отрендерен через `<Show>`.

```tsx
// ❌
let ref!: HTMLDivElement;
onMount(() => ref.focus()); // undefined если Show когда-то была false

// ✅ — эффект, не onMount
let ref!: HTMLDivElement;
createEffect(() => {
  if (visible()) {
    queueMicrotask(() => ref?.focus());
  }
});
```

### Ошибка: Hot Module Reload рушит state

**Причина:** Vite в dev режиме перегружает модули, иногда теряет реактивный контекст.

**Решение:** обычно перезапуск dev сервера. Если регулярно — проверь не создаёшь ли сигналы на верхнем уровне модулей (см. ошибку #2).

---

## 128. Глоссарий специфичных терминов

**Signal** — реактивная переменная. Тапл `[get, set]` из `createSignal`.

**Accessor** — функция-геттер сигнала. Вызов создаёт подписку в реактивном контексте.

**Setter** — функция-сеттер сигнала. Принимает значение или функцию `(prev) => next`.

**Computation** — узел реактивного графа, который читает сигналы. Memo, Effect, RenderEffect — это computations.

**Owner** — узел дерева владения. Когда owner размонтируется, его дочерние computations и cleanup'ы запускаются.

**Tracking scope** — область кода в которой обращение к сигналам создаёт подписки (внутри `createEffect`, `createMemo`, JSX).

**untrack** — выход из tracking scope; чтение сигнала без создания подписки.

**Store** — реактивный прокси-объект для сложных данных (объекты, массивы). Поддерживает path-based обновления.

**produce** — хелпер для "мутирующего" стиля обновления store.

**reconcile** — алгоритм для смены большого блока данных store с сохранением идентичности неизменившихся элементов.

**Resource** — async реактивный примитив. `createResource` создаёт ресурс с состояниями loading/error/ready.

**Suspense** — граница в дереве которая показывает fallback пока дочерние ресурсы грузятся.

**Transition** — обновления помеченные как "не срочные" через `useTransition`/`startTransition`.

**Hydration** — процесс активации SSR-сгенерированного HTML на клиенте.

**Server function** — функция помеченная `"use server"`, выполняется на сервере, вызывается с клиента как обычная.

**Action** — server function для форм. Работает с `<form action={...}>`, поддерживает прогрессивное enhancement.

**Query** — кэшируемая server function для GET-операций. Используется с `createAsync`.

**Directive (use:)** — функция расширяющая поведение элемента через `use:name={accessor}` синтаксис.

**JSX tracking scope** — JSX автоматически создаёт tracking scope. Поэтому `<div>{signal()}</div>` реактивно.

**Equals** — функция сравнения значений сигнала. По умолчанию `===`. Можно отключить (`equals: false`) или задать кастомную.

---

## 129. Полезные ссылки

### Официальная документация
- **SolidJS docs** — https://docs.solidjs.com
- **SolidStart docs** — https://docs.solidjs.com/solid-start
- **Router docs** — https://docs.solidjs.com/solid-router

### GitHub
- **Solid core** — https://github.com/solidjs/solid
- **SolidStart** — https://github.com/solidjs/solid-start
- **Solid Router** — https://github.com/solidjs/solid-router
- **Solid Primitives** — https://github.com/solidjs-community/solid-primitives

### Учебные ресурсы
- **Solid Playground** — https://playground.solidjs.com
- **Solid Tutorial** — https://www.solidjs.com/tutorial
- **Reactivity Demo** — https://playground.solidjs.com (загляни в "Reactive Graph" примеры)

### Экосистема
- **Kobalte (UI компоненты)** — https://kobalte.dev
- **@modular-forms/solid** — https://modularforms.dev
- **TanStack Solid Query** — https://tanstack.com/query/latest/docs/solid/overview
- **@tanstack/solid-virtual** — https://tanstack.com/virtual
- **@thisbeyond/solid-dnd** — https://thisbeyond.github.io/solid-dnd/

### Devtools и debugging
- **Solid Devtools** — https://github.com/thetarnav/solid-devtools
- **Chrome Extension** — https://chromewebstore.google.com/detail/solid-devtools/kmcfjchnmmaeeagadbhoofajiopoceel

### Сообщество
- **Discord** — https://discord.com/invite/solidjs
- **Reddit r/solidjs** — https://reddit.com/r/solidjs
- **Twitter / X** — Ryan Carniato (@RyanCarniato), Solid Account (@solid_js)

### Блоги и статьи Райана Carniato
- **Dev.to профиль** — https://dev.to/ryansolid
- "A Hands-on Introduction to Fine-Grained Reactivity" — must-read
- "Building a Reactive Library from Scratch"
- "SolidStart: The Shape of Frameworks to Come"

### Бенчмарки
- **js-framework-benchmark** — https://krausest.github.io/js-framework-benchmark/

### Видео
- YouTube канал Ryan Carniato — стримы про разработку Solid и SolidStart
- Solid Hack — игровой джем с проектами на Solid

---

# Заключение

Книга написана как одновременно учебник и справочник.

**Если ты только начинаешь** — иди по порядку. Часть I-III даёт фундамент, IV-IX — основной API. К концу Части XI ты сможешь писать рабочие приложения.

**Если ты опытный разработчик** — используй оглавление, перепрыгивай к нужным разделам. Особенно полезны:
- Часть X (реактивный граф под капотом)
- Часть XIII (TypeScript глубоко) 
- Часть XIX (SolidStart — полностью)
- Часть XXI (анти-паттерны)

**Если работаешь над проектом** — держи справочник под рукой:
- Раздел 125 — полный API
- Раздел 126 — UnoCSS
- Раздел 127 — типичные ошибки
- Раздел 129 — ссылки

SolidJS — компактный фреймворк с ясной ментальной моделью. Когда ты понял реактивность, остальное складывается само.

Удачи в коде!

---

*Конец книги*
---
---

# Часть XXIII — Дополнительные практические примеры

Эта часть добавлена как дополнение. Здесь 4 production-grade примера которые показывают комбинирование разных техник из основной части книги. Каждый пример самодостаточен — можно копировать в свой проект.

- 130. [🛠 Toast система через Context](#130--toast-система-через-context)
- 131. [🛠 Тёмная тема с тремя состояниями](#131--тёмная-тема-с-тремя-состояниями)
- 132. [🛠 Data table с URL-синхронизацией](#132--data-table-с-url-синхронизацией)
- 133. [🛠 Файловый загрузчик с прогрессом и preview](#133--файловый-загрузчик-с-прогрессом-и-preview)

---

## 130. 🛠 Toast система через Context

Toast уведомления — стандартный компонент любого приложения. Этот пример комбинирует: Context, Portal, store с массивом, анимации через CSS, авто-исчезновение, ARIA для accessibility.

### Toast Provider и Hook

```tsx
// src/context/ToastContext.tsx
import {
  Component,
  createContext,
  useContext,
  ParentProps,
  For,
  Show,
  onCleanup,
} from "solid-js";
import { createStore, produce } from "solid-js/store";
import { Portal } from "solid-js/web";

type ToastType = "success" | "error" | "info" | "warning";

interface Toast {
  id: string;
  type: ToastType;
  message: string;
  title?: string;
  duration: number;        // ms, 0 = не исчезать автоматически
  dismissable: boolean;
}

interface ToastContextValue {
  toasts: () => Toast[];
  show: (toast: Omit<Toast, "id" | "duration" | "dismissable"> & {
    duration?: number;
    dismissable?: boolean;
  }) => string;
  success: (message: string, title?: string) => string;
  error: (message: string, title?: string) => string;
  info: (message: string, title?: string) => string;
  warning: (message: string, title?: string) => string;
  dismiss: (id: string) => void;
  dismissAll: () => void;
}

const ToastContext = createContext<ToastContextValue>();

const MAX_TOASTS = 5;
const DEFAULT_DURATION = 4000;

export const ToastProvider: Component<ParentProps> = (props) => {
  const [state, setState] = createStore<{ toasts: Toast[] }>({ toasts: [] });
  const timers = new Map<string, number>();

  const dismiss = (id: string) => {
    const timer = timers.get(id);
    if (timer) {
      clearTimeout(timer);
      timers.delete(id);
    }
    setState("toasts", (prev) => prev.filter((t) => t.id !== id));
  };

  const dismissAll = () => {
    for (const timer of timers.values()) clearTimeout(timer);
    timers.clear();
    setState("toasts", []);
  };

  const show: ToastContextValue["show"] = (toast) => {
    const id = crypto.randomUUID();
    const newToast: Toast = {
      id,
      type: toast.type,
      message: toast.message,
      title: toast.title,
      duration: toast.duration ?? DEFAULT_DURATION,
      dismissable: toast.dismissable ?? true,
    };

    setState(
      produce((s) => {
        s.toasts.unshift(newToast);
        // Ограничение количества
        if (s.toasts.length > MAX_TOASTS) {
          const removed = s.toasts.splice(MAX_TOASTS);
          for (const t of removed) {
            const timer = timers.get(t.id);
            if (timer) {
              clearTimeout(timer);
              timers.delete(t.id);
            }
          }
        }
      })
    );

    if (newToast.duration > 0) {
      const timer = window.setTimeout(() => dismiss(id), newToast.duration);
      timers.set(id, timer);
    }

    return id;
  };

  // Очистка всех таймеров при размонтировании
  onCleanup(() => {
    for (const timer of timers.values()) clearTimeout(timer);
    timers.clear();
  });

  const value: ToastContextValue = {
    toasts: () => state.toasts,
    show,
    success: (message, title) => show({ type: "success", message, title }),
    error: (message, title) => show({ type: "error", message, title, duration: 6000 }),
    info: (message, title) => show({ type: "info", message, title }),
    warning: (message, title) => show({ type: "warning", message, title }),
    dismiss,
    dismissAll,
  };

  return (
    <ToastContext.Provider value={value}>
      {props.children}
      <ToastContainer />
    </ToastContext.Provider>
  );
};

export const useToast = () => {
  const ctx = useContext(ToastContext);
  if (!ctx) {
    throw new Error("useToast должен использоваться внутри ToastProvider");
  }
  return ctx;
};

// Контейнер с тостами
const TOAST_STYLES: Record<ToastType, { bg: string; icon: string; border: string }> = {
  success: { bg: "bg-green-50", border: "border-green-500", icon: "✓" },
  error:   { bg: "bg-red-50",   border: "border-red-500",   icon: "✕" },
  info:    { bg: "bg-blue-50",  border: "border-blue-500",  icon: "ℹ" },
  warning: { bg: "bg-yellow-50",border: "border-yellow-500",icon: "⚠" },
};

const ToastContainer: Component = () => {
  const { toasts, dismiss } = useToast();

  return (
    <Portal>
      <div
        class="fixed top-4 right-4 z-50 flex flex-col gap-2 max-w-sm w-full pointer-events-none"
        role="region"
        aria-label="Уведомления"
        aria-live="polite"
      >
        <For each={toasts()}>
          {(toast) => {
            const style = TOAST_STYLES[toast.type];
            return (
              <div
                role="alert"
                class={`${style.bg} ${style.border} border-l-4 rounded shadow-lg p-4 pointer-events-auto animate-slide-in flex gap-3`}
              >
                <div class={`text-xl font-bold ${style.border.replace("border", "text")}`}>
                  {style.icon}
                </div>
                <div class="flex-1 min-w-0">
                  <Show when={toast.title}>
                    <div class="font-semibold mb-1">{toast.title}</div>
                  </Show>
                  <div class="text-sm text-gray-700">{toast.message}</div>
                </div>
                <Show when={toast.dismissable}>
                  <button
                    onClick={() => dismiss(toast.id)}
                    class="text-gray-400 hover:text-gray-600 text-lg leading-none"
                    aria-label="Закрыть уведомление"
                  >
                    ×
                  </button>
                </Show>
              </div>
            );
          }}
        </For>
      </div>
    </Portal>
  );
};
```

### CSS для анимации (UnoCSS shortcut)

В `app.config.ts` (UnoCSS конфиг) добавь:
```ts
UnoCSS({
  rules: [
    ["animate-slide-in", {
      animation: "slide-in 0.2s ease-out",
    }],
  ],
  preflights: [{
    getCSS: () => `
      @keyframes slide-in {
        from { transform: translateX(100%); opacity: 0; }
        to { transform: translateX(0); opacity: 1; }
      }
    `,
  }],
})
```

### Использование

```tsx
// App.tsx
import { ToastProvider } from "./context/ToastContext";

const App: Component = () => (
  <ToastProvider>
    <MainContent />
  </ToastProvider>
);

// В любом компоненте
const SaveButton: Component = () => {
  const toast = useToast();

  const handleSave = async () => {
    try {
      await api.save();
      toast.success("Данные сохранены", "Успех");
    } catch (err) {
      toast.error((err as Error).message, "Ошибка сохранения");
    }
  };

  return (
    <button onClick={handleSave}>
      Сохранить
    </button>
  );
};

// Подтверждение с действием — duration: 0 чтобы не исчезал
const handleDelete = async () => {
  const id = toast.show({
    type: "warning",
    title: "Удалить элемент?",
    message: "Нажмите ✕ чтобы отменить",
    duration: 0,
  });
  
  // Через 5 секунд — выполняем
  setTimeout(async () => {
    toast.dismiss(id);
    await api.delete();
    toast.success("Удалено");
  }, 5000);
};
```

### Что важно понять

1. **Provider + Hook паттерн** — стандартный для контекста (раздел 44)
2. **`Map<id, timer>` снаружи store** — таймеры не должны быть в реактивном store (это побочные ресурсы)
3. **`unshift` в produce** — новые toasts сверху списка
4. **Ограничение MAX_TOASTS** — не даём списку расти бесконечно, очищаем таймеры удаляемых
5. **`onCleanup` в Provider** — очистка всех таймеров если Provider размонтируется
6. **`Portal` + `aria-live="polite"`** — рендер вне основного дерева, screen reader читает изменения
7. **`pointer-events-none` на контейнере, `pointer-events-auto` на toast** — позволяет кликать сквозь пустое пространство между тостами

В production вместо самописного toast часто берут `solid-toast` или `@kobalte/core/toast`. Но самописный даёт полный контроль над поведением.

---

## 131. 🛠 Тёмная тема с тремя состояниями

Современные приложения поддерживают три состояния темы: light, dark, system (следует за OS настройкой). Этот пример: custom primitive + Context + localStorage + `prefers-color-scheme`.

### Custom primitive

```tsx
// src/primitives/createTheme.ts
import { createSignal, createEffect, onMount, onCleanup, Accessor } from "solid-js";

type ThemeMode = "light" | "dark" | "system";
type ResolvedTheme = "light" | "dark";

interface ThemeApi {
  mode: Accessor<ThemeMode>;          // что пользователь выбрал
  resolved: Accessor<ResolvedTheme>;  // что реально применено (system → light/dark)
  setMode: (mode: ThemeMode) => void;
  toggle: () => void;                 // cycle: light → dark → system → light
  isDark: Accessor<boolean>;
}

const STORAGE_KEY = "theme";

export const createTheme = (): ThemeApi => {
  // Читаем из localStorage с проверкой что значение валидное
  const readStored = (): ThemeMode => {
    const stored = localStorage.getItem(STORAGE_KEY);
    if (stored === "light" || stored === "dark" || stored === "system") {
      return stored;
    }
    return "system";
  };

  const [mode, setMode] = createSignal<ThemeMode>(readStored());
  const [systemPrefers, setSystemPrefers] = createSignal<ResolvedTheme>("light");

  // Слушаем prefers-color-scheme
  onMount(() => {
    const mq = window.matchMedia("(prefers-color-scheme: dark)");
    setSystemPrefers(mq.matches ? "dark" : "light");

    const handler = (e: MediaQueryListEvent) => {
      setSystemPrefers(e.matches ? "dark" : "light");
    };
    mq.addEventListener("change", handler);
    onCleanup(() => mq.removeEventListener("change", handler));
  });

  // Резолвим итоговую тему
  const resolved = (): ResolvedTheme => {
    const m = mode();
    if (m === "system") return systemPrefers();
    return m;
  };

  // Применяем класс к <html> и сохраняем в localStorage
  createEffect(() => {
    const theme = resolved();
    const html = document.documentElement;
    
    html.classList.remove("light", "dark");
    html.classList.add(theme);
    html.dataset.theme = theme;
    
    // Для нативных элементов (scrollbar, autofill)
    html.style.colorScheme = theme;

    localStorage.setItem(STORAGE_KEY, mode());
  });

  const toggle = () => {
    const cycle: Record<ThemeMode, ThemeMode> = {
      light: "dark",
      dark: "system",
      system: "light",
    };
    setMode(cycle[mode()]);
  };

  return {
    mode,
    resolved,
    setMode,
    toggle,
    isDark: () => resolved() === "dark",
  };
};
```

### Контекст для всего приложения

```tsx
// src/context/ThemeContext.tsx
import { createContext, useContext, ParentComponent } from "solid-js";
import { createTheme } from "~/primitives/createTheme";

type ThemeApi = ReturnType<typeof createTheme>;

const ThemeContext = createContext<ThemeApi>();

export const ThemeProvider: ParentComponent = (props) => {
  const theme = createTheme();
  return (
    <ThemeContext.Provider value={theme}>
      {props.children}
    </ThemeContext.Provider>
  );
};

export const useTheme = () => {
  const ctx = useContext(ThemeContext);
  if (!ctx) {
    throw new Error("useTheme должен использоваться внутри ThemeProvider");
  }
  return ctx;
};
```

### Кнопка переключения

```tsx
// src/components/ThemeToggle.tsx
import { Component, Show } from "solid-js";
import { useTheme } from "~/context/ThemeContext";

const ThemeToggle: Component = () => {
  const { mode, resolved, setMode, toggle } = useTheme();

  const icon = () => {
    if (mode() === "system") return "🖥️";
    if (resolved() === "dark") return "🌙";
    return "☀️";
  };

  const label = () => {
    if (mode() === "system") return `Системная (${resolved() === "dark" ? "тёмная" : "светлая"})`;
    if (mode() === "dark") return "Тёмная";
    return "Светлая";
  };

  return (
    <div class="relative inline-block">
      <button
        onClick={toggle}
        class="px-3 py-2 rounded border border-gray-300 dark:border-gray-700 bg-white dark:bg-gray-800"
        aria-label={`Тема: ${label()}. Нажми чтобы переключить.`}
      >
        <span class="mr-2">{icon()}</span>
        <span class="text-sm">{label()}</span>
      </button>
    </div>
  );
};

// Расширенная версия — dropdown с выбором всех трёх
export const ThemeSwitcher: Component = () => {
  const { mode, setMode } = useTheme();

  const options: { value: "light" | "dark" | "system"; icon: string; label: string }[] = [
    { value: "light", icon: "☀️", label: "Светлая" },
    { value: "dark", icon: "🌙", label: "Тёмная" },
    { value: "system", icon: "🖥️", label: "Системная" },
  ];

  return (
    <div class="flex gap-1 p-1 bg-gray-100 dark:bg-gray-800 rounded">
      {options.map((opt) => (
        <button
          onClick={() => setMode(opt.value)}
          class={`px-3 py-1 rounded text-sm transition-colors ${
            mode() === opt.value
              ? "bg-white dark:bg-gray-700 shadow"
              : "hover:bg-gray-200 dark:hover:bg-gray-700"
          }`}
          aria-pressed={mode() === opt.value}
          title={opt.label}
        >
          <span class="mr-1">{opt.icon}</span>
          {opt.label}
        </button>
      ))}
    </div>
  );
};

export default ThemeToggle;
```

### Стили для тёмной темы (UnoCSS)

В большинстве случаев работает префикс `dark:`:

```tsx
<div class="bg-white text-gray-900 dark:bg-gray-900 dark:text-gray-100">
  Контент адаптируется автоматически
</div>
```

Для UnoCSS включи dark mode в конфиге:
```ts
UnoCSS({
  presets: [
    presetWind3({
      dark: "class",  // активирует через class="dark" на <html>
    }),
  ],
})
```

### Использование

```tsx
// App.tsx
import { ThemeProvider } from "./context/ThemeContext";
import ThemeToggle from "./components/ThemeToggle";

const App: Component = () => (
  <ThemeProvider>
    <header class="bg-white dark:bg-gray-900 border-b dark:border-gray-700 p-4">
      <div class="flex justify-between items-center">
        <h1 class="text-gray-900 dark:text-white">Моё приложение</h1>
        <ThemeToggle />
      </div>
    </header>
    <main class="bg-gray-50 dark:bg-gray-800 min-h-screen text-gray-900 dark:text-gray-100">
      {/* контент */}
    </main>
  </ThemeProvider>
);
```

### FOUC (Flash of Unstyled Content) — важное!

При SSR/первой загрузке HTML отрендерится со светлой темой, потом JS переключит на тёмную — будет видна вспышка. Решение — inline script в HTML до подключения JS:

```html
<!-- index.html, в <head> -->
<script>
  (function() {
    var theme = localStorage.getItem("theme") || "system";
    var dark = theme === "dark" || 
      (theme === "system" && window.matchMedia("(prefers-color-scheme: dark)").matches);
    document.documentElement.classList.add(dark ? "dark" : "light");
    document.documentElement.style.colorScheme = dark ? "dark" : "light";
  })();
</script>
```

### Что важно понять

1. **Три состояния, не два** — `system` важен для UX. Многие сайты этого не делают и зря.
2. **Разделение mode и resolved** — пользователь хочет "system", но мы применяем реальный light/dark
3. **`color-scheme` CSS свойство** — влияет на нативные элементы (скроллбар, форма autofill, заголовок окна)
4. **`matchMedia` listener для prefers-color-scheme** — пользователь может переключить OS тему пока приложение открыто
5. **FOUC через inline script** — без него на медленных устройствах видна вспышка
6. **`localStorage.setItem` в effect** — автоматическая синхронизация при изменении

В production можно взять `@solid-primitives/media` который уже даёт `usePrefersDark()` и обработку.

---

## 132. 🛠 Data table с URL-синхронизацией

Таблица данных с сортировкой, фильтрацией, поиском и пагинацией — где всё состояние живёт в URL. Это значит: можно поделиться ссылкой, обновление страницы сохраняет состояние, кнопка "назад" работает естественно.

```tsx
// src/routes/users.tsx
import { Component, For, Show, createMemo, Suspense } from "solid-js";
import { createAsync, useSearchParams, query } from "@solidjs/router";

interface User {
  id: number;
  name: string;
  email: string;
  role: "admin" | "editor" | "viewer";
  status: "active" | "inactive";
  createdAt: string;
}

type SortField = "name" | "email" | "createdAt";
type SortDir = "asc" | "desc";

// Имитация загрузки данных (в реальности — server function)
const getUsers = query(async (): Promise<User[]> => {
  // "use server";
  // return await db.user.findMany();
  
  // Для примера — мок-данные
  return Array.from({ length: 47 }, (_, i) => ({
    id: i + 1,
    name: `Пользователь ${i + 1}`,
    email: `user${i + 1}@example.com`,
    role: (["admin", "editor", "viewer"] as const)[i % 3],
    status: (i % 4 === 0 ? "inactive" : "active") as const,
    createdAt: new Date(2024, 0, 1 + i).toISOString(),
  }));
}, "getUsers");

const ITEMS_PER_PAGE = 10;

const UsersTable: Component = () => {
  // ВСЁ состояние в URL
  const [params, setParams] = useSearchParams<{
    q?: string;
    role?: string;
    status?: string;
    sort?: SortField;
    dir?: SortDir;
    page?: string;
  }>();

  const users = createAsync(() => getUsers());

  // Извлечение параметров с дефолтами
  const search = () => params.q ?? "";
  const roleFilter = () => params.role ?? "";
  const statusFilter = () => params.status ?? "";
  const sortField = () => (params.sort as SortField) ?? "name";
  const sortDir = () => (params.dir as SortDir) ?? "asc";
  const currentPage = () => Number(params.page ?? 1);

  // Фильтрация + сортировка
  const filteredSorted = createMemo(() => {
    const all = users() ?? [];
    const q = search().toLowerCase();
    
    let result = all.filter((u) => {
      if (q && !u.name.toLowerCase().includes(q) && !u.email.toLowerCase().includes(q)) {
        return false;
      }
      if (roleFilter() && u.role !== roleFilter()) return false;
      if (statusFilter() && u.status !== statusFilter()) return false;
      return true;
    });

    const dir = sortDir() === "asc" ? 1 : -1;
    const field = sortField();
    result = [...result].sort((a, b) => {
      const av = a[field];
      const bv = b[field];
      if (av < bv) return -1 * dir;
      if (av > bv) return 1 * dir;
      return 0;
    });

    return result;
  });

  // Пагинация
  const totalPages = createMemo(() =>
    Math.max(1, Math.ceil(filteredSorted().length / ITEMS_PER_PAGE))
  );
  
  const pageItems = createMemo(() => {
    const start = (currentPage() - 1) * ITEMS_PER_PAGE;
    return filteredSorted().slice(start, start + ITEMS_PER_PAGE);
  });

  // Обработчики
  const handleSort = (field: SortField) => {
    if (sortField() === field) {
      // toggle направление
      setParams({ dir: sortDir() === "asc" ? "desc" : "asc", page: "1" });
    } else {
      setParams({ sort: field, dir: "asc", page: "1" });
    }
  };

  const handleSearch = (q: string) => {
    setParams({ q: q || undefined, page: "1" });
  };

  const handleFilter = (key: "role" | "status", value: string) => {
    setParams({ [key]: value || undefined, page: "1" });
  };

  const handlePage = (p: number) => {
    setParams({ page: String(p) });
  };

  const clearFilters = () => {
    setParams({ q: undefined, role: undefined, status: undefined, page: "1" });
  };

  const sortIcon = (field: SortField) => {
    if (sortField() !== field) return "⇅";
    return sortDir() === "asc" ? "▲" : "▼";
  };

  return (
    <div class="max-w-6xl mx-auto p-4">
      <h1 class="text-2xl font-bold mb-4">Пользователи</h1>

      {/* Фильтры */}
      <div class="flex flex-wrap gap-2 mb-4">
        <input
          type="text"
          value={search()}
          onInput={(e) => handleSearch(e.currentTarget.value)}
          placeholder="Поиск по имени или email..."
          class="border rounded px-3 py-2 flex-1 min-w-[200px]"
        />
        <select
          value={roleFilter()}
          onChange={(e) => handleFilter("role", e.currentTarget.value)}
          class="border rounded px-3 py-2"
        >
          <option value="">Все роли</option>
          <option value="admin">Admin</option>
          <option value="editor">Editor</option>
          <option value="viewer">Viewer</option>
        </select>
        <select
          value={statusFilter()}
          onChange={(e) => handleFilter("status", e.currentTarget.value)}
          class="border rounded px-3 py-2"
        >
          <option value="">Все статусы</option>
          <option value="active">Active</option>
          <option value="inactive">Inactive</option>
        </select>
        <Show when={search() || roleFilter() || statusFilter()}>
          <button
            onClick={clearFilters}
            class="px-3 py-2 text-blue-500 hover:underline"
          >
            Сбросить
          </button>
        </Show>
      </div>

      <Suspense fallback={<p>Загрузка...</p>}>
        <div class="text-sm text-gray-600 mb-2">
          Найдено: {filteredSorted().length} из {users()?.length ?? 0}
        </div>

        {/* Таблица */}
        <div class="overflow-x-auto border rounded">
          <table class="w-full">
            <thead class="bg-gray-50">
              <tr>
                <th
                  class="text-left px-4 py-3 cursor-pointer select-none hover:bg-gray-100"
                  onClick={() => handleSort("name")}
                >
                  Имя <span class="text-gray-400 ml-1">{sortIcon("name")}</span>
                </th>
                <th
                  class="text-left px-4 py-3 cursor-pointer select-none hover:bg-gray-100"
                  onClick={() => handleSort("email")}
                >
                  Email <span class="text-gray-400 ml-1">{sortIcon("email")}</span>
                </th>
                <th class="text-left px-4 py-3">Роль</th>
                <th class="text-left px-4 py-3">Статус</th>
                <th
                  class="text-left px-4 py-3 cursor-pointer select-none hover:bg-gray-100"
                  onClick={() => handleSort("createdAt")}
                >
                  Создан <span class="text-gray-400 ml-1">{sortIcon("createdAt")}</span>
                </th>
              </tr>
            </thead>
            <tbody>
              <Show
                when={pageItems().length > 0}
                fallback={
                  <tr>
                    <td colspan="5" class="text-center text-gray-500 py-8">
                      Ничего не найдено
                    </td>
                  </tr>
                }
              >
                <For each={pageItems()}>
                  {(user) => (
                    <tr class="border-t hover:bg-gray-50">
                      <td class="px-4 py-2">{user.name}</td>
                      <td class="px-4 py-2 text-gray-600">{user.email}</td>
                      <td class="px-4 py-2">
                        <span class={`text-xs px-2 py-1 rounded ${
                          user.role === "admin" ? "bg-red-100 text-red-700"
                          : user.role === "editor" ? "bg-blue-100 text-blue-700"
                          : "bg-gray-100 text-gray-700"
                        }`}>
                          {user.role}
                        </span>
                      </td>
                      <td class="px-4 py-2">
                        <span class={`inline-block w-2 h-2 rounded-full mr-2 ${
                          user.status === "active" ? "bg-green-500" : "bg-gray-400"
                        }`} />
                        {user.status}
                      </td>
                      <td class="px-4 py-2 text-gray-600 text-sm">
                        {new Date(user.createdAt).toLocaleDateString()}
                      </td>
                    </tr>
                  )}
                </For>
              </Show>
            </tbody>
          </table>
        </div>

        {/* Пагинация */}
        <Show when={totalPages() > 1}>
          <div class="flex items-center justify-between mt-4">
            <button
              onClick={() => handlePage(currentPage() - 1)}
              disabled={currentPage() === 1}
              class="px-3 py-1 border rounded disabled:opacity-50"
            >
              ← Назад
            </button>
            <div class="flex gap-1">
              <For each={Array.from({ length: totalPages() }, (_, i) => i + 1)}>
                {(p) => (
                  <button
                    onClick={() => handlePage(p)}
                    class={`w-8 h-8 rounded ${
                      currentPage() === p
                        ? "bg-blue-500 text-white"
                        : "hover:bg-gray-100"
                    }`}
                  >
                    {p}
                  </button>
                )}
              </For>
            </div>
            <button
              onClick={() => handlePage(currentPage() + 1)}
              disabled={currentPage() === totalPages()}
              class="px-3 py-1 border rounded disabled:opacity-50"
            >
              Вперёд →
            </button>
          </div>
        </Show>
      </Suspense>
    </div>
  );
};

export default UsersTable;
```

### Что важно понять

1. **Источник истины — URL** — никакого `createSignal` для фильтров. `useSearchParams` это `[Accessor, Setter]` под капотом
2. **`setParams({ value: undefined })` чистит ключ** — URL получается чистым (без `?role=` где значение пустое)
3. **Сброс страницы при фильтре** — `page: "1"` чтобы не остаться на странице 47 после фильтра
4. **`createMemo` для производных** — фильтрация и сортировка только при изменении источника
5. **Поделись ссылкой** — `?q=ivan&role=admin&sort=email&dir=desc&page=2` сохраняет полное состояние
6. **Кнопка назад** — браузер автоматически восстанавливает предыдущие фильтры

### Расширение для production

- **Debounce поиска** — добавить `createDeferred(search, { timeoutMs: 300 })` перед фильтрацией
- **Виртуализация при 1000+ строках** — `@tanstack/solid-virtual` (раздел 98)
- **Сортировка/фильтрация на сервере** — передавать параметры в server function через query
- **Multi-select фильтры** — `params.role = "admin,editor"`, split при чтении

---

## 133. 🛠 Файловый загрузчик с прогрессом и preview

Многофайловый загрузчик с drag-and-drop, preview изображений, прогрессом каждого файла, валидацией. Использует XMLHttpRequest для прогресса (fetch его не поддерживает), FileReader для preview, Store для управления очередью.

```tsx
import {
  Component,
  For,
  Show,
  createSignal,
  onCleanup,
} from "solid-js";
import { createStore, produce } from "solid-js/store";

type UploadStatus =
  | { type: "pending" }
  | { type: "uploading"; progress: number }
  | { type: "success"; url: string }
  | { type: "error"; message: string };

interface UploadItem {
  id: string;
  file: File;
  preview?: string;       // data URL для изображений
  status: UploadStatus;
  xhr?: XMLHttpRequest;   // для отмены
}

interface UploadConfig {
  url: string;
  maxSize: number;         // bytes
  acceptTypes: string[];   // MIME types
  maxFiles: number;
}

const DEFAULT_CONFIG: UploadConfig = {
  url: "/api/upload",
  maxSize: 5 * 1024 * 1024,           // 5 MB
  acceptTypes: ["image/jpeg", "image/png", "image/gif", "image/webp"],
  maxFiles: 10,
};

const FileUploader: Component<{ config?: Partial<UploadConfig> }> = (props) => {
  const config: UploadConfig = { ...DEFAULT_CONFIG, ...(props.config ?? {}) };

  const [state, setState] = createStore<{
    items: UploadItem[];
    isDragging: boolean;
  }>({ items: [], isDragging: false });

  // Очистка при размонтировании — отменяем активные загрузки
  onCleanup(() => {
    for (const item of state.items) {
      item.xhr?.abort();
    }
  });

  const validateFile = (file: File): string | null => {
    if (!config.acceptTypes.includes(file.type)) {
      return `Тип ${file.type} не поддерживается`;
    }
    if (file.size > config.maxSize) {
      return `Размер превышает ${(config.maxSize / 1024 / 1024).toFixed(1)} MB`;
    }
    return null;
  };

  const generatePreview = (file: File): Promise<string | undefined> => {
    if (!file.type.startsWith("image/")) return Promise.resolve(undefined);

    return new Promise((resolve) => {
      const reader = new FileReader();
      reader.onload = () => resolve(reader.result as string);
      reader.onerror = () => resolve(undefined);
      reader.readAsDataURL(file);
    });
  };

  const addFiles = async (files: FileList | File[]) => {
    const fileArr = Array.from(files);
    
    // Проверка лимита
    const available = config.maxFiles - state.items.length;
    if (available <= 0) {
      alert(`Максимум ${config.maxFiles} файлов`);
      return;
    }

    const toAdd = fileArr.slice(0, available);
    
    for (const file of toAdd) {
      const validation = validateFile(file);
      const id = crypto.randomUUID();

      const preview = await generatePreview(file);

      const item: UploadItem = {
        id,
        file,
        preview,
        status: validation
          ? { type: "error", message: validation }
          : { type: "pending" },
      };

      setState("items", (prev) => [...prev, item]);

      // Авто-старт загрузки если валидация прошла
      if (!validation) {
        uploadFile(id);
      }
    }
  };

  const uploadFile = (id: string) => {
    const item = state.items.find((i) => i.id === id);
    if (!item || item.status.type === "uploading") return;

    const xhr = new XMLHttpRequest();
    
    setState("items", (i) => i.id === id, produce((it) => {
      it.status = { type: "uploading", progress: 0 };
      it.xhr = xhr;
    }));

    // Прогресс
    xhr.upload.addEventListener("progress", (e) => {
      if (!e.lengthComputable) return;
      const progress = Math.round((e.loaded / e.total) * 100);
      
      setState("items", (i) => i.id === id, "status", (s) =>
        s.type === "uploading" ? { type: "uploading", progress } : s
      );
    });

    // Успех
    xhr.addEventListener("load", () => {
      if (xhr.status >= 200 && xhr.status < 300) {
        try {
          const response = JSON.parse(xhr.responseText);
          setState("items", (i) => i.id === id, produce((it) => {
            it.status = { type: "success", url: response.url };
            delete it.xhr;
          }));
        } catch {
          setState("items", (i) => i.id === id, produce((it) => {
            it.status = { type: "error", message: "Неверный ответ сервера" };
            delete it.xhr;
          }));
        }
      } else {
        setState("items", (i) => i.id === id, produce((it) => {
          it.status = { type: "error", message: `HTTP ${xhr.status}` };
          delete it.xhr;
        }));
      }
    });

    // Ошибка сети
    xhr.addEventListener("error", () => {
      setState("items", (i) => i.id === id, produce((it) => {
        it.status = { type: "error", message: "Ошибка сети" };
        delete it.xhr;
      }));
    });

    // Отмена
    xhr.addEventListener("abort", () => {
      setState("items", (i) => i.id === id, produce((it) => {
        it.status = { type: "pending" };
        delete it.xhr;
      }));
    });

    const formData = new FormData();
    formData.append("file", item.file);

    xhr.open("POST", config.url);
    xhr.send(formData);
  };

  const cancelUpload = (id: string) => {
    const item = state.items.find((i) => i.id === id);
    item?.xhr?.abort();
  };

  const removeItem = (id: string) => {
    const item = state.items.find((i) => i.id === id);
    if (item?.status.type === "uploading") {
      item.xhr?.abort();
    }
    setState("items", (prev) => prev.filter((i) => i.id !== id));
  };

  const retryUpload = (id: string) => {
    setState("items", (i) => i.id === id, "status", { type: "pending" });
    uploadFile(id);
  };

  // Drag handlers
  const handleDragOver = (e: DragEvent) => {
    e.preventDefault();
    setState("isDragging", true);
  };

  const handleDragLeave = (e: DragEvent) => {
    e.preventDefault();
    setState("isDragging", false);
  };

  const handleDrop = (e: DragEvent) => {
    e.preventDefault();
    setState("isDragging", false);
    if (e.dataTransfer?.files) {
      addFiles(e.dataTransfer.files);
    }
  };

  const totalProgress = () => {
    const uploading = state.items.filter((i) => i.status.type === "uploading");
    if (uploading.length === 0) return 100;
    const sum = uploading.reduce(
      (acc, i) => acc + (i.status.type === "uploading" ? i.status.progress : 0),
      0
    );
    return Math.round(sum / uploading.length);
  };

  const allDone = () => {
    if (state.items.length === 0) return false;
    return state.items.every(
      (i) => i.status.type === "success" || i.status.type === "error"
    );
  };

  return (
    <div class="max-w-2xl mx-auto p-4">
      <h2 class="text-xl font-bold mb-4">Загрузка файлов</h2>

      {/* Dropzone */}
      <div
        onDragOver={handleDragOver}
        onDragLeave={handleDragLeave}
        onDrop={handleDrop}
        class={`border-2 border-dashed rounded-lg p-8 text-center transition-colors ${
          state.isDragging
            ? "border-blue-500 bg-blue-50"
            : "border-gray-300 hover:border-gray-400"
        }`}
      >
        <input
          type="file"
          multiple
          accept={config.acceptTypes.join(",")}
          onChange={(e) => {
            if (e.currentTarget.files) addFiles(e.currentTarget.files);
            e.currentTarget.value = ""; // позволить выбрать те же файлы снова
          }}
          class="hidden"
          id="file-input"
        />
        <label
          for="file-input"
          class="cursor-pointer"
        >
          <div class="text-4xl mb-2">📁</div>
          <p class="text-gray-700">
            {state.isDragging
              ? "Отпусти чтобы загрузить"
              : "Перетащи файлы сюда или кликни"}
          </p>
          <p class="text-sm text-gray-500 mt-2">
            До {config.maxFiles} файлов, макс {(config.maxSize / 1024 / 1024).toFixed(1)} MB каждый
          </p>
        </label>
      </div>

      {/* Общий прогресс */}
      <Show when={state.items.some((i) => i.status.type === "uploading")}>
        <div class="mt-4">
          <div class="flex justify-between text-sm text-gray-600 mb-1">
            <span>Общий прогресс</span>
            <span>{totalProgress()}%</span>
          </div>
          <div class="w-full bg-gray-200 rounded h-2">
            <div
              class="bg-blue-500 h-2 rounded transition-all duration-300"
              style={{ width: `${totalProgress()}%` }}
            />
          </div>
        </div>
      </Show>

      {/* Список файлов */}
      <Show when={state.items.length > 0}>
        <div class="mt-6 space-y-2">
          <For each={state.items}>
            {(item) => (
              <div class="flex items-center gap-3 p-3 border rounded bg-white">
                {/* Preview или иконка */}
                <Show
                  when={item.preview}
                  fallback={
                    <div class="w-12 h-12 bg-gray-100 rounded flex items-center justify-center text-2xl">
                      📄
                    </div>
                  }
                >
                  <img
                    src={item.preview!}
                    alt={item.file.name}
                    class="w-12 h-12 object-cover rounded"
                  />
                </Show>

                {/* Info + прогресс */}
                <div class="flex-1 min-w-0">
                  <div class="flex justify-between items-baseline gap-2">
                    <p class="truncate font-medium text-sm">{item.file.name}</p>
                    <p class="text-xs text-gray-500 whitespace-nowrap">
                      {(item.file.size / 1024).toFixed(1)} KB
                    </p>
                  </div>

                  {/* Статус */}
                  <Show when={item.status.type === "uploading"}>
                    {(_) => {
                      const s = item.status;
                      if (s.type !== "uploading") return null;
                      return (
                        <div class="mt-1">
                          <div class="w-full bg-gray-200 rounded h-1">
                            <div
                              class="bg-blue-500 h-1 rounded transition-all"
                              style={{ width: `${s.progress}%` }}
                            />
                          </div>
                          <p class="text-xs text-gray-500 mt-1">
                            Загрузка {s.progress}%
                          </p>
                        </div>
                      );
                    }}
                  </Show>

                  <Show when={item.status.type === "success"}>
                    <p class="text-xs text-green-600 mt-1">✓ Загружено</p>
                  </Show>

                  <Show when={item.status.type === "error"}>
                    {(_) => {
                      const s = item.status;
                      if (s.type !== "error") return null;
                      return (
                        <p class="text-xs text-red-600 mt-1">✗ {s.message}</p>
                      );
                    }}
                  </Show>
                </div>

                {/* Кнопки действий */}
                <div class="flex gap-1">
                  <Show when={item.status.type === "uploading"}>
                    <button
                      onClick={() => cancelUpload(item.id)}
                      class="text-yellow-600 text-sm px-2"
                      title="Отменить загрузку"
                    >
                      ⏸
                    </button>
                  </Show>
                  <Show when={item.status.type === "error"}>
                    <button
                      onClick={() => retryUpload(item.id)}
                      class="text-blue-600 text-sm px-2"
                      title="Повторить"
                    >
                      ↻
                    </button>
                  </Show>
                  <button
                    onClick={() => removeItem(item.id)}
                    class="text-gray-400 hover:text-red-500 text-lg px-2"
                    title="Удалить"
                  >
                    ×
                  </button>
                </div>
              </div>
            )}
          </For>
        </div>

        <Show when={allDone()}>
          <div class="mt-4 p-3 bg-green-50 border border-green-200 rounded text-sm text-green-700">
            Все файлы обработаны. Успешно: {state.items.filter((i) => i.status.type === "success").length},
            ошибок: {state.items.filter((i) => i.status.type === "error").length}
          </div>
        </Show>
      </Show>
    </div>
  );
};

export default FileUploader;
```

### Что важно понять

1. **XMLHttpRequest вместо fetch** — `fetch` не даёт прогресс upload. XHR через `xhr.upload.addEventListener("progress", ...)` даёт. Это пока единственный способ в браузере
2. **`FileReader.readAsDataURL`** — создаёт base64 для preview изображений. Не подходит для больших файлов (хранится в памяти), для них — `URL.createObjectURL(file)` + `URL.revokeObjectURL` при удалении
3. **`xhr` в store** — храним ссылку чтобы можно было abort. После завершения удаляем (через `delete it.xhr` в produce)
4. **Дискриминированный union для status** — невозможно иметь `progress` без `uploading`, `url` без `success`. Type-safe (раздел 70)
5. **`e.currentTarget.value = ""`** после select — без этого второй раз тот же файл нельзя выбрать
6. **`accept` атрибут** — фильтрует диалог выбора, но не валидирует drag-and-drop. Поэтому валидация в JS обязательна
7. **`onCleanup` при unmount** — отменяем все активные загрузки. Без этого xhr продолжит работать и обновлять размонтированный store

### Расширения

- **Параллельный лимит** — сейчас все файлы стартуют сразу. Для много файлов лучше очередь с лимитом одновременных загрузок
- **Chunked upload** — для файлов >100MB разрезать на куски (resumable.js, tus.io)
- **Server-side валидация** — клиентскую можно обойти, на сервере обязательна
- **Compression** — для изображений можно сжать через `canvas.toBlob` перед отправкой

---

## Что освоено в этих 4 примерах

Каждый из примеров комбинирует множество техник:

| Пример | Контекст | Store | Анимации | Async | URL | Refs/DOM |
|---|---|---|---|---|---|---|
| Toast | ✅ | ✅ | ✅ | ⊘ | ⊘ | ⊘ |
| Тёмная тема | ✅ | ⊘ | ⊘ | ⊘ | ⊘ | ✅ |
| Data table | ⊘ | ⊘ | ⊘ | ✅ | ✅ | ⊘ |
| File uploader | ⊘ | ✅ | ✅ | ✅ | ⊘ | ✅ |

Плюс везде: дискриминированные unions, custom primitives, accessibility, очистка ресурсов через onCleanup.

Этих 4 примеров вместе с 7 основными даёт **11 production-grade проектов** к которым можно возвращаться как к референсу.

---

*Конец Части XXIII*

