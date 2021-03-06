# Подлкючение двух калькуляторов одновременно

Подключение двух калькуляторов отличается тем, что для них есть общие файлы, которые дублировать не надо.


## Подключение стилей

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.2.4/components/icon.min.css"/>
<link rel="stylesheet" href="./dist/css/style.css">
<link rel="stylesheet" href="https://qostya.github.io/atomic-emmet/dist/style.css">
```

## Подключение скриптов

Внизу, до закрывающего тега `<body>` необходимо подключить следующие скрипты:

```html
<script charset="utf-8" src="./config.js"></script>
<script charset="utf-8" src="../common/vendors.min.js"></script>
<script charset="utf-8" src="./dist/js/app.min.js"></script>
```

## Разметка

Пример разметки для вывода калькулятора:

Вызывающая калькулятор иконка справа:

```html
<div class="c-calc-panel">
    <a href="#/pre" class="c-calc-panel__item js-show-choosing-calc">
        <div class="c-calc-panel__item-icon">
            <img src="./static/images/shield_protection_red.png" alt=""/>
        </div>
        <div class="c-calc-panel__item-title">
            ON'LINE ПОЛИС
        </div>
    </a>
</div>

```


```html
<div class="b-app-modal b-app-modal--is-hidden">
    <div class="b-app-modal__bg js-app-modal-close"></div>

    <div class="b-app-modal__content">
        <div class="js-choose--post">
            <div class="b-app-modal__head">
                <h2>ОСАГО на ваш автомобиль</h2>
                <div class="b-app-modal__close js-app-modal-close">
                    <span>Нет, спасибо</span>
                </div>
            </div>

            <div id="KaskoApp">
                <div class="b-app" ui-view ng-class="'b-app--' + currentBrandName"></div>
            </div>

            <div id="OsagoApp">
                <div class="b-app" ui-view ng-class="'b-app--' + currentBrandName"></div>
            </div>
        </div>

        <div class="js-choose--pre">
            <div class="b-app-modal__head">
                <div class="b-app-modal__close js-app-modal-close">
                    <span>Нет, спасибо</span>
                </div>

                <h2>Выберите тип расчета:</h2>
            </div>

            <div class="b-full-width-bg mt10 p20 pt20">
                <div class="ui grid stackable centered" style="padding: 20px 0;">
                    <div class="five wide column">
                        <button class="ui button fluid big blue fw400 js-calc-panel-item js-calc-panel-item--kasko"
                                type="button">
                            КАСКО
                        </button>
                    </div>

                    <div class="five wide column">
                        <button class="ui button fluid big red fw400 js-calc-panel-item js-calc-panel-item--osago"
                                type="button">
                            ОСАГО
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
```

Рабочий пример можно посмотреть здесь: `rolf/index.html`

[Назад][bede57fb]

  [bede57fb]: readme.md "Назад"
