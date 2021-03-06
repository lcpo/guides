# Требования к оформлению HTML

### Отступы и длина строки

* Длина строки не должна превышать **110 символов**.

* В качестве отступов используем **4 пробела**.

* Не должно быть лишних пустых строк, если это не обусловлено лучше читаемостью:

    ``` html
    <!-- Плохо -->
    <p>Абзац текст</p>


    <p>Ещё один</p>
    <ul>
        <li>Cats</li>

        <li>Not cats</li>
    </ul>

    <!-- Хорошо -->
    <p>Абзац текст</p>
    <p>Ещё один</p>
    <ul>
        <li>Cats</li>
        <li>Not cats</li>
    </ul>
    ```

* Не должно быть лишних пробелов:

    ``` html
    <!-- Плохо -->
    <ul>
        <li> Cats </li>
        <li> <strong>Not cats</strong></li>
    </ul>
    <abbr  title = "Health Points">HP</abbr>


    <!-- Хорошо -->
    <ul>
        <li>Cats</li>
        <li><strong>Not cats</strong></li>
    </ul>
    <abbr title="Health Points">HP</abbr>
    ```

* Необходимо соблюдать правила вложенности согласно примерам:

    ``` html
    <div>Здесь мало текста, он влезает в 110 символов, не переносим</div>
    <div>
        А здесь уже более длинный текст, не влезает в 110 символов, переносим его
        на новую строку внутри элемента и делаем отступ в 4 пробела.
    </div>
    <div>
        <div>
            Вложенные элементы (кроме текстовых) переносим внутрь родительского
            элемента на новую строку и делаем отступ в 4 пробела.
        </div>
        Ещё немного текста
        <div>Ещё один элемент</div>
    </div>
    <div>
        <div>
            Текстовые <em>элементы ведут себя как текст, каким бы длинным не было
            их содержимое</em>, такие дела.
        </div>
    </div>
    ```

### Именование тегов и атрибутов

* Пишем теги строчными буквами:

    ``` html
    <!-- Плохо -->
    <TITLE>Яндекс.Блог</tItLe>

    <!-- Хорошо -->
    <title>Яндекс.Блог</title>

    ```

* Void elements (одиночные) теги не закрываем, normal elements (парные) **закрываем всегда**:

    ``` html
    <!-- Плохо -->
    <img src="cats.jpeg" />
    <meta charset="utf-8"/>
    <ul>
        <li>Cats
        <li>Not cats
    </ul>

    <!-- Хорошо -->
    <img src="cats.jpeg">
    <meta charset="utf-8">

    <ul>
        <li>Cats</li>
        <li>Not cats</li>
    </ul>
    ```

* Пишем атрибуты строчными буквами:

    ``` html
    <!-- Плохо -->
    <abbr TITLE="Hell Points">HP</abbr>

    <!-- Хорошо -->
    <abbr title="Health Points">HP</abbr>
    ```  

* Одиночные атрибуты пишем без значений, а остальные со значениями **в двойных кавычках**:

    ``` html
    <!-- Плохо -->
    <input type=button disabled>
    <input type="button" disabled="">
    <input type="button" disabled="disabled">
    <input type='button' disabled>

    <!-- Хорошо -->
    <input type="button" disabled>
    ```  

* Зарезервированные значения атрибутов пишем строчными буквами:

    ``` html
    <!-- Плохо -->
    <input type="BUTTON">

    <!-- Хорошо -->
    <input type="button">
    ```

### Обязательные элементы и атрибуты

* Всегда указываем:

    - `<!DOCTYPE html>`
    - `<html lang="ru">`
    - `<head>`
    - `<body>`
    - `<title>`
    - `<meta charset="utf-8">`
    <br>
    <br>

    ``` html
    <!-- Хорошо -->
    <!DOCTYPE html>
    <html lang="ru">
        <head>
            <meta charset="utf-8">
            <title>Яндекс.Блог</title>
        </head>
        <body>

        </body>
    </html>
    ```

* У изображений всегда указываем атрибут `alt=""`:

### Запрещённые элементы и атрибуты

* Устаревшие элементы: `<center>`, `<font>`, `<marquee>` и другие
* Элементы визуальной разметки: `<b>`, `<u>`, `<i>`, `<s>` и другие
* Устаревшие атрибуты: `border` для таблиц, `type` для списков,
  `align` для выравнивания и другие

### Экранирование символов

* В тексте элементов всегда заменяем символы `<` и `>` на `&lt;` и `&gt;`

    ``` html
    <!-- Плохо -->
    <div>Текст с <угловыми> скобками</div>

    <!-- Хорошо -->
    <div>Текст с &lt;угловыми&gt; скобками</div>
    ```
