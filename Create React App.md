## Создание нового проекта React.js
* Сначала должен быть установлен Node.js: https://nodejs.org/en/download/.
* Вместе с Node.js установится пакетный менеджер npm и утилита для запуска пакетов npx. Для проверки что все установлено корректно, выполните команды:<br>`node --version`<br>`npm --v`<br>`npx --v`<br>Должны появиться их версии.
* Выполнить команду (должен быть включен интернет):<br>`npx create-react-app <имя_проекта>`<br>Процесс создания приложения займет какое-то время. В каталоге <имя_проекта> будут установлены необходимые пакеты Node.js и создана начальная структура файлов. 
* Для дальнейшей работы нужно перейти в созданную папку (`cd <имя_проекта>`)
* Проверим работу начальной версии проекта запустив его командой `npm start`. Должно открыться окно браузера с начальной страницей и логотипом React.js. Пока команда запущена можно править приложение и сразу видеть результат в браузере. Т.е. сейчас мы в режиме разработки.
* Основные папки - public и src.
* public содержит index.html и дополнительные ресурсы.<br>Для начала работы удалим все из этой папки и создадим новый чистый index.html

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

```jsx
import * as React from 'react';

function App() {
  return (
    <div className="App"></div>
  );
}

export default App;
```

`<div className="App"></div>` - компонент<br>`import * as React from 'react';` - подключаем react. Это нужно делать во всех файлах где используются компоненты.
* index.js почистим чтобы выглядел так:

```jsx
import * as React from 'react';
import * as ReactDOMClient from 'react-dom/client';
import App from './App';

const container = document.getElementById('root');
const root = ReactDOMClient.createRoot(container);

root.render(
  <App />
);
```

* Теперь у нас есть минимальное приложение, использующее React.
