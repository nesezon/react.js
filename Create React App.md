## Создание нового проекта React.js
* Сначала проверяем установлен ли Node.js. Выполните команду:<br />`node --version`<br>Должен появиться номер версии.
* Если команда "node" не обнаружена, необходимо установить Node.js: https://nodejs.org/en/download/.<br />Вместе с Node.js автоматически установятся npm и npx.
* Затем нужно проверить наличие установленного Git (требуется для установки некоторых зависимостей)<br />`git --version`<br>Должен появиться номер версии.
* Если команда "git" не обнаружена, необходимо установить Git:<br />https://git-scm.com/download/.
* После установки Node.js или Git закройте и заново откройте окно командной строки.<br />Если какая-то из команд `node --version` или `git --version` все еще не работает, перезагрузите компьютер.
* Если Git у вас еще не настроен и вы хотите чтобы в проекте автоматически создался локальный репозиторий, введите свои регистрационные данные:<br />`git config --global user.name <имя пользователя>`<br />`git config --global user.email <адрес электронной почты>`<br />Проверить какие у вас name и email можно так:<br />`git config --get user.name`<br />`git config --get user.email`
* Выполните команду (должен быть включен интернет):<br>`npx create-react-app <имя_проекта>`<br />При первой установке согласитесь на установку пакета "create-react-app" (нажмите "y" и ввод)<br />Процесс создания приложения займет какое-то время. В каталоге <имя_проекта> будут установлены необходимые пакеты Node.js и создана начальная структура файлов.
* В некоторых случаях может появиться ошибка `unable to get local issuer certificate` (например при использовании корпоративного интернета).<br />Тогда помогает отключение строгой проверки ssl:<br />`npm config set strict-ssl=false`
* После успешного создания проекта нужно перейти в созданную папку (`cd <имя_проекта>`)
* Проверим работу начальной версии проекта запустив его командой `npm start`. Должно открыться окно браузера с начальной страницей и логотипом React.js. Если окно открылось в Internet Explorer, страница работать не будет. Перейдите на более современный браузер.
* Пока команда запущена можно править приложение и сразу видеть результат в браузере, т.е. сейчас мы в режиме разработки.
* Основные папки - public и src.
* public содержит index.html и дополнительные ресурсы.<br>Для начала работы удалим все из этой папки и создадим новый чистый **index.html**

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
* **App.js** почистим, чтобы он стал выглядеть так:

```jsx
function App() {
  return (
    <div className="App" />
  );
}

export default App;
```

`<div className="App" />` - компонент

* **index.js** почистим чтобы выглядел так:

```jsx
import * as ReactDOMClient from 'react-dom/client';
import App from './App';

const container = document.getElementById('root');
const root = ReactDOMClient.createRoot(container);

root.render(
  <App />
);
```

* Теперь у нас есть минимальное приложение, использующее React.
