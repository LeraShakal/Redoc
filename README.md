<div align="center">
  <img alt="Redoc logo" src="https://raw.githubusercontent.com/Redocly/redoc/main//docs/images/redoc.png" width="400px" />

# Инструмент для создания красивой документации API из OpenAPI

  [![npm](http://img.shields.io/npm/v/redoc.svg)](https://www.npmjs.com/package/redoc) [![License](https://img.shields.io/npm/l/redoc.svg)](https://github.com/Redocly/redoc/blob/main/LICENSE)

  [![bundle size](http://img.badgesize.io/https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js?compression=gzip&max=300000)](https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js) [![npm](https://img.shields.io/npm/dm/redoc.svg)](https://www.npmjs.com/package/redoc) [![jsDelivr status](https://data.jsdelivr.com/v1/package/npm/redoc/badge)](https://www.jsdelivr.com/package/npm/redoc)
</div>


## О Redoc

Redoc — это инструмент с открытым исходным кодом для создания документации на основе определений OpenAPI (ранее Swagger).

По умолчанию Redoc предлагает трехпанельную адаптивную компоновку:

- Левая панель содержит строку поиска и меню навигации.
- Центральная панель содержит документацию.
- Правая панель содержит примеры запросов и ответов.

![Redoc demo](https://raw.githubusercontent.com/Redocly/redoc/main/demo/redoc-demo.png)

## Демонстрация в реальном времени

Если вы хотите увидеть, как Redoc отображает ваше определение OpenAPI, вы можете попробовать это онлайн по адресу https://redocly.github.io/redoc/.

Версия API Swagger Petstore отображается по умолчанию. Чтобы протестировать ее с вашим собственным определением OpenAPI, введите URL для вашего определения и выберите **TRY IT**.

## Особенности перекодировки

- Адаптивный трехпанельный дизайн с синхронизацией меню/прокрутки
- Поддержка OpenAPI 3.1, OpenAPI 3.0 и Swagger 2.0
- Возможность интегрировать введение API в боковое меню
- Группировка высокого уровня в боковом меню с [`x-tagGroups`](https://redocly.com/docs/api-reference-docs/specification-extensions/x-tag-groups/) расширением спецификации
- [Простая интеграция с `create-react-app`](https://redocly.com/docs/redoc/quickstart/react/)
- Поддержка примеров кода (с расширением поставщика) <br>
  ![code samples in action](docs/images/code-samples-demo.gif)

## Использование

Redoc предоставляется как инструмент CLI (также распространяется как образ Docker), HTML-тег и компонент React.

### Создание документации из CLI

Если у вас установлен Node, вы можете быстро создать документацию, используя `npx`:

```bash
npx @redocly/cli build-docs openapi.yaml
```

TПо умолчанию инструмент выводит данные в файл с именем `redoc-static.html` который можно открыть в браузере.

> [Redocly CLI](https://github.com/Redocly/redocly-cli/) делает больше, чем просто документацию; ознакомьтесь с ним и добавьте линтинг, объединение и многое другое в свой рабочий процесс API.

### Добавьте HTML-элемент на страницу

Создайте HTML-страницу или отредактируйте существующую и добавьте в теги body следующее:

```html
    <redoc spec-url="http://petstore.swagger.io/v2/swagger.json"></redoc>
    <script src="https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js"> </script>
```

Откройте HTML-файл в браузере, и на странице отобразится документация по API.

Добавьте свой собственный `spec-url` к the `<redoc>` тегу; этот атрибут также может быть локальным файлом. Библиотеку JavaScript также можно установить локально с помощью `npm` и обслуживать с вашего собственного сервера, см. [документацию по развёртыванию HTML](https://redocly.com/docs/redoc/deployment/html/) для получения более подробной информации.

### Дополнительные варианты использования

Дополнительные параметры и подробную информацию по каждому варианту можно найти в [документации по развёртыванию](./docs/deployment/intro.md).


### Документация и ресурсы

- [Справочные документы](https://redocly.com/docs/api-reference-docs/getting-started/) 
- [Redoc](https://redocly.com/docs/redoc/) - подробная документация по этому проекту с открытым исходным кодом (также в папке `docs/`)
- [Интерфейс командной строки для объединения ваших документов в HTML-файл, готовый к публикации в Интернете](https://redocly.com/docs/cli/commands/build-docs/)
- Анализ API, объединение и многое другое с открытым исходным кодом  [Redocly CLI](https://redocly.com/docs/cli)

## Кейсы

Примеры организаций, использующих инструменты Redocly на практике:

- [Rebilly](https://api-reference.rebilly.com/)
- [Docker Engine](https://docs.docker.com/engine/api/v1.25/)
- [Zuora](https://www.zuora.com/developer/api-reference/)
- [Discourse](http://docs.discourse.org)
- [Commbox](https://www.commbox.io/api/)
- [APIs.guru](https://apis.guru/api-doc/)
- [BoxKnight](https://www.docs.boxknight.com/)
- [Quaderno API](https://developers.quaderno.io/api)

## Конфигурация

Redoc обладает широкими возможностями настройки, подробности см. в [документация по настройке](docs/config.md).

### Расширения спецификации OpenAPI
Redoc использует следующие [расширения спецификации](https://redocly.com/docs/api-reference-docs/spec-extensions/):

* [`x-logo`](docs/redoc-vendor-extensions.md#x-logo) - используется для указания логотипа API
* [`x-traitTag`](docs/redoc-vendor-extensions.md#x-traitTag) -  полезно для тегов, которые ссылаются на ненавигационные свойства, такие как пагинация, ограничения скорости и т.д.
* [`x-codeSamples`](docs/redoc-vendor-extensions.md#x-codeSamples) - указать примеры кодов операций
* [`x-badges`](docs/redoc-vendor-extensions.md#x-badges) - указать значки операций
* [`x-examples`](docs/redoc-vendor-extensions.md#x-examples) - указать пример JSON для запросов
* [`x-nullable`](docs/redoc-vendor-extensions.md#x-nullable) - пометить параметр схемы как допускающий значение NULL
* [`x-displayName`](docs/redoc-vendor-extensions.md#x-displayname) - указать понятные человеку названия для категорий меню
* [`x-tagGroups`](docs/redoc-vendor-extensions.md#x-tagGroups) - группировать теги по категориям в боковом меню
* [`x-servers`](docs/redoc-vendor-extensions.md#x-servers) - возможность указывать разные серверы для API (портировано из OpenAPI 3.0)
* [`x-ignoredHeaderParameters`](docs/redoc-vendor-extensions.md#x-ignoredHeaderParameters) - возможность указывать имена параметров заголовка, которые следует игнорировать
* [`x-additionalPropertiesName`](docs/redoc-vendor-extensions.md#x-additionalPropertiesName) - возможность указать описательное имя для дополнительных ключей свойств
* [`x-summary`](docs/redoc-vendor-extensions.md#x-summary) - для объекта Response используйте в качестве текста кнопки ответа описание, отображаемое под кнопкой
* [`x-extendedDiscriminator`](docs/redoc-vendor-extensions.md#x-extendedDiscriminator) - в схемах использует это для решения проблем конфликта имен со стандартным дискриминатором
* [`x-explicitMappingOnly`](docs/redoc-vendor-extensions.md#x-explicitMappingOnly) - в схемах отображать более описательное имя свойства в объектах с additionalProperties при просмотре списка свойств с объектом


## Development
см. [CONTRIBUTING.md](.github/CONTRIBUTING.md)
