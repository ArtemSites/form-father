# Form Father

[![npm version](https://img.shields.io/npm/v/form-father)](https://www.npmjs.com/package/form-father)
[![npm downloads](https://img.shields.io/npm/dm/form-father)](https://www.npmjs.com/package/form-father)

- [🇬🇧 English documentation](https://github.com/Poliklot/form-father/blob/master/docs/en/README.md)

**Form Father** — это библиотека для обработки форм на чистом JavaScript, обеспечивающая удобную валидацию и отправку
форм с использованием TypeScript.

## Установка

Установите библиотеку с помощью npm:

```bash
npm install form-father
```

## Использование

```javascript
import Form from 'form-father';

Form.setDefaultParams({
  showLoaderButton: false,
  scrollToFirstErroredInput: false,
  logging: true,
});

const formElement = document.querySelector('#myForm');
const options = {
	onSubmit: formInstance => {
		// Действия при отправке формы
	},
	onResponse: (responseBody, formInstance) => {
		// Действия при получении ответа от сервера
	},
	// Другие опции...
};

const form = new Form(formElement, options);
```

## Опции

- **onSubmit**: Функция обратного вызова, вызываемая при отправке формы.
- **onResponse**: Функция обратного вызова при получении ответа от сервера.
- **onResponseSuccess**: Функция вызывается при успешном ответе сервера (статус 200).
- **onResponseUnsuccess**: Функция вызывается при неуспешном ответе сервера (статус не 200).
- **showLoaderButton**: Показывать ли лоадер в кнопке отправки. По умолчанию `true`.
- **scrollToFirstErroredInput**: Прокручивать ли к первому полю с ошибкой. По умолчанию `true`.
- **customTypeError**: Кастомный тип ошибки.
- **loaderColor**: Цвет лоадера в кнопке отправки.
- **logging**: Нужно ли выводить данные в консоль. По умолчанию `false`.

## Методы

- **clearInputs()**: Очищает все поля ввода формы.
- **setDefaultParams(params)**: Метод setDefaultParams используется для установки значений по умолчанию для всех экземпляров формы. Эти параметры можно переопределить при инициализации конкретной формы.

## Хелперы

Библиотека предоставляет ряд вспомогательных функций:

- **serializeToFormData($element)**: Сериализует данные формы в объект `FormData`.
- **isEmailValid(value)**: Проверяет, является ли строка валидным адресом электронной почты.
- **isUrlValid(value)**: Проверяет, является ли строка валидным URL.
- **isPhoneValid(value)**: Проверяет, является ли строка валидным номером телефона.
- **closest($el, selector)**: Находит ближайший родительский элемент по заданному селектору.
- **blockScrollBody()**: Блокирует прокрутку страницы.
- **unblockScrollBody()**: Разблокирует прокрутку страницы.
- **parseCommonResponseProperties(responseBody)**: Обрабатывает общие свойства ответа сервера.

## Сборка и разработка

Для сборки проекта используется **Rollup**. Основные команды:

- **npm run build**: Сборка проекта.
- **npm run watch**: Сборка в режиме наблюдения.
- **npm run demos**: Запуск демо-версии с использованием Vite.

## Вклад

Будем рады вашим предложениям и улучшениям! Пожалуйста, создавайте
[issues](https://github.com/poliklot/form-father/issues) и отправляйте
[pull requests](https://github.com/poliklot/form-father/pulls).

## Лицензия

[MIT](LICENSE)

© 2024 Poliklot
