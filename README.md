# Сборка Front-end проекта  
**stylus + спрайты + авторелоад с шарингом**


#### Краткое описание сборщика

Структура в собранном виде выглядит так:

```
    build/
    --- css/
        --- style.min.css
    --- img/
        --- content/
        --- desing/
        --- sprite/
    --- js/
        --- vendor/
        --- scripts.js
    --- index.html
```

Возможность инклюдить файлы, удобно для построения файловой структуры проекта, пример `//= footer.html`  
Для компиляции стилей используется [Stylus](http://learnboost.github.io/stylus/), также в стилях прописываются [Sourcemap](https://www.npmjs.com/package/gulp-sourcemaps/), при желании можно выносить в отдельный файл.  
Генерация спрайтов и файла _sprite.styl_ с переменными, которые применяются в миксине, вызов миксина:

```sh
.selector {
    sprite($var) //вместо $var вставляем переменные из файла sprite.styl 
}
```

получаем:  
```sh
.selector {
    background-image:url(../img/sprite/sprite.png)
}
```


### Установка

Сначала должен быть установлен [node.js](https://nodejs.org/)

Открываем консоль и пишем:  
`npm install -g gulp` - глобальная установка gulp на машину.

Скачиваем данный репозиторий, заходим в папку и пишем:  
`npm install` - установка зависимостей прописаных в файле _package.json_

`gulp` - запуск. Все таски собраны в один таск _default_, который запускается этой командой по умолчанию.


После запуска автоматически откроется локальная страничка с проектом. Так же можно расшарить проект, для этого из консоли нужно скопировать **https** адрес, который был выдан в момент запуска. Он генерируестя каждый раз при запуске команды gulp.

В корне появится папки **node_modules** и **build**, все, можно работать.