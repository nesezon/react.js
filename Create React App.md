#### Создание нового проекта React.js
* Сначала должен быть установлен Node.js: https://nodejs.org/en/download/.
* Вместе с Node.js установится пакетный менеджер npm и утилита для запуска пакетов npx. Для проверки что все установлено корректно, выполните команды:<br>`node --version`<br>`npm --v`<br>`npx --v`
  Должны появиться их версии.
* Создать папку с именем нового проекта.
* Зайти в созданную папку и выполнить команду (должен быть включен интернет):<br>`npx create-react-app .`<br>Процесс создания приложения займет какое-то время. Будут установлены необходимые пакеты Node.js и создана начальная структура файлов.
* Проверим работу начальной версии проекта запустив его командой `npm start`. Должно открыться окно браузера с начальной страницей и логотипом React.js. Пока команда запущена можно править приложение и сразу видеть результат в браузере. Т.е. сейчас мы в режиме разработки.
* Основные папки - public и src.
* public содержит index.html и дополнительные ресурсы. Для начала работы удалим все из этой папки и создадим новый чистый index.html

```html
<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>React App</title>
  </head>
  <body>
    <noscript>Чтобы запустить это приложение включите JavaScript.</noscript>
    <div id="root">
      <!-- ЗДЕСЬ БУДЕТ НАШЕ JS ПРИЛОЖЕНИЕ -->
    </div>
  </body>
</html>
```

* В папке src оставим только файлы App.js и index.js
* App.js почистим, чтобы он стал выглядеть так:

```js
import React from 'react';

function App() {
  return (
    <div className="App"></div>
  );
}

export default App;
```

`<div className="App"></div>` - компонент<br>`import React from 'react';` - подключаем react. Это нужно делать во всех файлах где используется компонент.
* index.js почистим чтобы выглядел так:

```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <App />
);
```

* Теперь у нас есть минимальное приложение, использующее React.
