bem-forum
=========

Форум, построенный на БЭМ-методологии, использующий github issues в качестве хранилища.

Форум можно использовать в 2 режимах:

* как отдельное приложение
* как плагин к приложению, построенному на express, c использованием BEMTREE и BEMHTML-шаблонов

### Установка

* Клонировать репозиторий: `git clone git@github.com:bem/bem-forum.git`
* Перейти в папку со скаченным проектом: `cd bem-forum`
* Установить зависимости и собрать бандлы `make`
* Запустить проект `npm start`

В браузере перейти по адресу: `http://localhost:3000`.

### Конфигурация

Конфигурация проекта описывается в следующих файлах:

* `configs/common/node.json` - общая конфигурация для всех окружений;
* `configs/development/node.json` - конфигурация для режима разработки;
* `configs/production/node.json` - конфигурация для production-режима.

#### Общая конфигурация

`configs/common/node.json` позволяет указать репозиторий, который будет
использоваться для хранения `issues`, например:

```
"forum": {
    "storage": {
        "user": "bem",
        "repo": "bem-talk"
    }
}
```

#### Конфигурация окружения

`configs/{environment}/node.json` позволяют указать параметры для Oauth
авторизации через Github:

```
"forum": {
    "oauth": {
        "localhost": {
            "clientId": "your client id",
            "secret": "your secret key",
            "redirectUrl": "http://localhost:3000"
        }
    }
}
```

Здесь предусмотрена возможность существования нескольких поддоменов для сайта,
например, для нескольких локалей:

```
"forum": {
    "oauth": {
        "localhost": {
            ...
        },
        "en.localhost": {
            ...
        },
        "ru.localhost": {
            ...
        }
    }
}
```

### Использование форума как плагина к существующему приложению

### TODO

* Кэширование данных для ускорения работы форума