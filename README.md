# Коллекция природных артефактов
## Краткое описание (TLDR)
**В своем проекте я использовала:**
+ HTML, CSS
+ БЭМ
+ SCSS
+ Структура 7-1
+ Адаптивная верстка
+ Пиксель перфект
+ swiper.js
+ Атрибуты для доступности

## Введение
Проект "Коллекция природных артефактов" создан, чтобы люди, интересующиеся исследованиями
природы, могли поучавствовать в развитии данной сферы и помочь лаборатории.
Моя цель в разработке этого проекта заключается в том, чтобы пользователям веб-страницы было
приятно изучать свою любимую сферу и удобно проводить на ней время.

## Почему именно моя веб-страница?
Для выбора моего проекта есть довольно важная причина - в этом проекте я использовала современную разработку.
+ Адаптивная верстка. Моя страница отображается красиво как на компьютере, так и на планшете или телефоне
  + Версия **desktop**
  ![desktop](https://github.com/user-attachments/assets/2fca07be-3722-40c9-8ae0-c33afc7b911c)
  + Версия **mobile**
  ![mobile-320](https://github.com/user-attachments/assets/36d1bf29-88f9-4e8c-bbe0-1e62a1beef14)
+ PerfectPixel я использовала, чтобы сайт был в точности, как на макете
+ Для быстрой загрузки я отформатировала все изображения в формат `.webp`, а все svg-картинки хранятся в отдельном файле sprite.svg
+ В шапку сайта я добавила навигацию, с помощью которой можно удобно и быстро перемещаться по разделам
+ Благодаря состоянию кнопок и ссылок `:focus-visible` по данной веб-странице удобно перемещаться с помощью клавиатуры

## Как использовать веб-страницу?
В использовании страницы всё просто.
1. Откройте [страницу](https://alinalukyanova25.github.io/site5/)
2. Листайте вниз, чтобы изучить всю информацию о проекте
3. Если вы точно знаете, что идете на страницу с целью помочь проекту, кликните на "Контакты" и вас перенесет к разделу "Помочь проекту"
4. Вам нужно написать ваше имя и адрес электронной почты в полях ввода
5. Отправив эти данные, вскоре вы получите письмо на Email по поводу ваших дальнейших действий

## Чем проект может быть полезным для других разработчиков?
На просторах интернета не всегда легко найти какую-либо информацию и поэтому данные лайфхаки могут кому-то пригодиться (покрайней мере я бы хотела узнать это раньше)

**Как сделать так, что при `:hover` стрелка svg удлинялась**

```html
<a href="#" class="link">
Исследовать
  <svg class="link__image">
    <use href="img/sprite.svg#link"></use>
  </svg>
</a>
```

```css
link:hover svg {
   transform: scaleX(1.2);
   transform-origin: left;
  }
```

**Как в слайдере оформить пагинацию с типом `fraction`**

```html
<div class="gallery__controls">
    <div class="myslider-prev swiper-button-prev" aria-label="Назад">
        <svg>
            <use href="img/sprite.svg#prev"></use>
        </svg>
    </div>
    <div class="gallery__pagination swiper-pagination">
    </div>
    <div class="myslider-next swiper-button-next" aria-label="Вперед">
        <svg>
            <use href="img/sprite.svg#next"></use>
        </svg>
    </div>
</div>
```

```css
gallery__controls {
    display: flex;
    gap: 30px;
    justify-content: center;
    align-items: center;
    height: 32px;
}

gallery__pagination {
    width: max-content;
    font-size: 24px;
}

.swiper-pagination {
    position: static;
}

.swiper-button-prev, 
.swiper-button-next {
    position: static;
    margin: 0;
    fill: #899D9D;
}
```

```js
new Swiper('.gallery__slider', {
    navigation: {
        nextEl: '.myslider-next',
        prevEl: '.myslider-prev',
    },
  
    pagination: {
      el: '.swiper-pagination',
      type: 'fraction',
        renderFraction: function (currentClass, totalClass) {
            return '<span class="' + currentClass + '"></span>' +
            ' из ' +
            '<span class="' + totalClass + '"></span>';
            },
    },
})
```

**Как сделать меню, которое выходит за рамки `header` при адаптивной верстке**

```css
.header {
    position: relative;
}

.header__nav {
    position: absolute;
    display: flex;
    overflow: auto;
    scrollbar-width: none;
    left: 0;
    bottom: -40px;
    padding-left: 33px;
    padding-right: 32px;
}
```

**Свойство `width: max-content`**

Такое значение width я использовала для того, чтобы заданные стили при состояниях, таких как :focus, :hover и :active, не растягивались на всю ширину секции.

```css
.link {
    width: max-content;
}
```

## Полезные инструменты, которые я использовала в своем проекте

[Squoosh](https://squoosh.app/) - инструмент для сжатия изображений
<br>
[Swiper.js](https://swiperjs.com/) для создания слайдера на странице
<br>
[NVDA](https://nvda.ru/download) - инструмент для проверки страницы на доступность
[PerfectPixel](https://www.welldonecode.com/perfectpixel/)
