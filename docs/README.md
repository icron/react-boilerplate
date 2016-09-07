# Документация

## Содержание

- [Введение](general)
  - [**CLI Команды**](general/commands.md)
  - [Конфигурация инструментов](general/files.md)
  - [Конфигурация сервера](general/server-configs.md)
  - [Развертывание](general/deployment.md) *(в настощяее время только Heroku)*
  - [FAQ](general/faq.md)
  - [Подводные камни](general/gotchas.md)
  - [Remove](general/remove.md)
- [Тестирование](testing)
  - [Модульное тестирование](testing/unit-testing.md)
  - [Тестирование компонентов](testing/component-testing.md)
  - [Удаленное тестирование](testing/remote-testing.md)
- [CSS](css)
  - [PostCSS](css/postcss.md)
  - [CSS Modules](css/css-modules.md)
  - [sanitize.css](css/sanitize.md)
- [JS](js)
  - [Redux](js/redux.md)
  - [ImmutableJS](js/immutablejs.md)
  - [reselect](js/reselect.md)
  - [redux-saga](js/redux-saga.md)
  - [i18n](js/i18n.md)
  - [routing](js/routing.md)

## Обзор

### Быстрый старт

1. Для начала сделаем вид, что мы  хотим запустить простое _Repospective_ приложение
   в комплекте с этим проектом для демонстрации некоторых из своих лучших возможностей:   

    ```Shell
    npm run setup && npm start
    ```

1. Откройте [localhost:3000](http://localhost:3000) чтобы увидеть это в действии.

    - Add a Github username to see Redux and Redux Sagas in action: effortless
      async state updates and side effects are now yours :)
    - Отредактируйте файл `./app/containers/HomePage/index.js` так, чтобы текст 
      компонента `<Button>` был "Features!!!"... Hot Module Reloading на ваши изменения!
      сделает гладкую перезгарузку (без перезагрузки всей страницы).
    - Click your (newly emphatic) Features button to see React Router in action...
      Now you can share a direct link to that content privately over your LAN or
      globally addressable to any device, anywhere. Not bad for a locally-running
      Single Page App.

1. Настало время чтобы собрать свое собственное приложение: run

    ```shell
    npm run clean
    ```

    ...и используйте встроенные генераторы чтобы начать работать над вашим приложением.

### Разработка

Запустите `npm start` чтобы увидеть свое приложение по адресу `localhost:3000`

### Сборка и Деплой

1. Запустите `npm run build`, эта команда скомпилирует все необходимые файлы и
 поместит их в папку `build`.

2. Загурузите содержимое папки `build` в корневую директорию вашего веб-сервера.

### Структура

[`app/`](../../../tree/master/app) директория содерит весь код приложения, включая CSS,
JavaScript, HTML и тесты.

Остальные папки и файлы существуют только чтобы упростить разработку и не должны изменяться без надобности.

*(Если вы нашли ошибку в них, пожалуйста, сообщите [submit an issue](https://github.com/mxstbr/react-boilerplate/issues)!)*

### CSS

Каждый компонет импортирует (`import`) свои зависимости стилей из рядом расположенного `styles.css` файла стилей данного модуля.

Сборка на продакшине собирает (траспилирует) эти модули в специфичные для каждой страницы CSS файлы (
 (на основе которых компоненты испольлзуются), в то время как все общие стили 
автоматически собираются в "common" файл стилей.

В результате минималистичности, получается высокая производительность для ваших пользователей. 

Смотрите [CSS documentation](./css/README.md) для большей информации PostCSS
и CSS модулей.

### JS

We bundle all your clientside scripts and chunk them into several files using
code splitting where possible. We then automatically optimize your code when
building for production so you don't have to worry about that.

See the [JS documentation](./js/README.md) for more information about the
JavaScript side of things.

### SEO

We use [react-helmet](https://github.com/nfl/react-helmet) for managing document head tags. Examples on how to
write head tags can be found [here](https://github.com/nfl/react-helmet#examples).

### Testing

For a thorough explanation of the testing procedure, see the
[testing documentation](./testing/README.md)!

#### Performance testing

With the production server running (i.e. while `npm run start:production` is running in
another tab), enter `npm run pagespeed` to run Google PageSpeed Insights and
get a performance check right in your terminal!

#### Browser testing

`npm run start:tunnel` makes your locally-running app globally available on the web
via a temporary URL: great for testing on different devices, client demos, etc!

#### Unit testing

Unit tests live in `test/` directories right next to the components being tested
and are run with `npm run test`.
