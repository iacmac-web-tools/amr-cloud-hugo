# [AMRcloud](https://amrcloud.net/)

## После клонирования репозитория

Тема Academic не хранится в данном репозитории. Она хранится в виде связанного git-репозитория. Поэтому после git clone репозитория тема отсутствует. Чтобы ее скачать необходимо сделать

`git submodule update --init --recursive`

## Как работать

Запустить в режиме дебага

`hugo server`

Так как сайт хостится на Github, то чтобы опубликовать его в продакшен, перед коммитом его надо скомпилировать. Для этого

`hugo`

Скомпилированный сайт кладется в папку docs

Пример сайта [academic](https://themes.gohugo.io/theme/academic/) можно найти в папке `themes/academic/exampleSite`

## Как писать контент

Как делать публикации разных типов можно почитать [здесь](https://sourcethemes.com/academic/docs/managing-content/)

Как красиво писать markdown файлы, узнать используемые шорткаты и прочие фишки, можно почитать [здесь](https://sourcethemes.com/academic/docs/writing-markdown-latex/)

## Сокрытие контента

Полезно, чтобы оно сохранилось в репозитории, но еще не публиковалось на сайте. По умолчанию Hugo не компилирует страницы, если у них:

Hugo allows you to set draft, publishdate, and even expirydate in your content’s front matter. By default, Hugo will not publish:

1. В поле `publishdate` содержится будущая дата
2. В странице установлен флаг `draft: true` то есть она в режиме черновика
3. Поле `expirydate` содержится прошедшая дата.

Чтобы такие публикации были видны в режиме дебага, нужно запускать `hugo server`  с флагами

1. `--buildFuture`
2. `--buildDrafts`
3. `--buildExpired`


## Как обновить используемую версию темы

Смотрим текущую версию в `themes/academic/data/academic.toml`
Перескакивать через версию не рекомендуется, лучше идти итеративно.

1. Обновляем тему
    ```
    git submodule update --remote --merge
    cd themes/academic
    git checkout vX.X.X
    ```
2. Проверяем необходимые изменения для перехода на новую версию по [ссылке](https://sourcethemes.com/academic/updates/v4.6.0/)
3. Запускаем `hugo server`, проверяем что все работает.