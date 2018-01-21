# alex_advices

## img

* заружать изображения размером с контейнер   

![фото](img/img1.png "фото")    

* для поддержки и чтобы картинка не искажалась в  ie картинки вставлять bg и потом в этот же элемент вставлять img, но img мы скрываем.



## ссылка   

* если логотип, то прописывать href='/' (ведет в корень и ищет там файл с index) 

## layout  

![фото](img/img2.png "фото")    
* html растягивается под viewport, а скролл появляется из за body а не html

## Верстка
  * Все текста оборачивать в span

## Работа с дизайнером  

* требовать шрифты

## Шрифты

* не зыбыть подключить символы кириллицы
* подключать запасные шрифты
* таблица font-weight   
![фото](img/img3.png "фото")
* подключать сглаживание шрифтов    
  -webkit-font-smoothing: antialiased;   
  -moz-osx-font-smoothing: grayscale;   

## Лендинг
* ставить min-height по макету(для каждого макета по ширинам laptop mobile tablet и т д ), чтобы если уменьштся viewport то секция сжиматься не будет при viewport меньше 650px    
* для того чтобы background не урезался во время уменьшения viewport можно для каждого разрешения вырезать свой отдельный background    


## SVG   
* Как отображается svg в браузере.
  1. создается холст размером с viewbox 
  2. на нем рисуется элемент (типо path circle и т.д.)
  3. весь viewbox растягивается по svg элементу (viewport)   
 
 ## Формы
* убираем реальную кнопку только через left:-9999px , потому что может появиться скрол по потоку если ставить обратное значение

## Pixel Perfect   
* для адаптивной верстки и вообще когда элемент плавает по старнице в зависимости от viewport, то подгоняем под PP только не плавающие элементы страницы.    
* если сайт резиновый то 1) подгоняем ширину viewport под макет(который в psd) 2) и под такой размер ставим проценты для измерений.

## Fiewfox    
* для flexitems ставить margin в px или в vh    

## IE11 IE10
* задавать явно св во flex для flexitems

## js
* правило четырех П 
  1. Подготовка
  2. Планировка
  3. Процесс написания кода
  4. Приведение к перфект  
* новый стандарт ES6+
  - писать код всегда в новом стандарте;  
  - использовать транскомпилятор для старых браузеров (babel)(es6fiddle);
  - использовать shim для релаизации новых возможностей в старых браузерах;
* правило написания кода
  - Создать все необходимые перменные
  - Проверить наличие элемента или не пустая ли перемнная над которой производим действие
* правило для callback функций и обработчиков
  - Eсли функцию завести в переменную, то он ее не будет заново создавать. А если в обработчике будет стоять анонимная, то браузер будет каждый раз ее создавать, а не брать из переменной.

## hover
* если при ховере выскакивает подсказка, и на нее человек дожен перейти, то необходимо эту подсказку положить в блок на который будет происходить hover. Иначе при выходе мыши за пределы объекта с ховером подсказка продатет. А если она будет внутри объекта с hover, то и сама подсказка тоже будет под действием hover и таким образом не будет скрываться, так как на ней тоже есть hover.
## transition
* не работает с display: none, тк дисплей нон нельзя представить в численном виде. т е можно, но только 1 и 0, без плавных переходов.
## preventDefault
* не ставить preventDefault на все события клавиатуры, т к это может угробит горячие клавиши в браузере.
## margin
* Основные принципы:  
  1. Отступы идут от предыдущего элемента к следующему.
  2. Отступ задается последнему возможному элементу в доме.
  3. Отступы нельзя задавать для независимых элементов ( БЭМ блок ).
  4. У последнего элемента группы, отступ обнуляется (всегда).
## Events 
* событие window.onload и bg картинки. событие следит за картикной если ее задать через js. т е если присвоить img.src в js, то событие onload не сработает пока картинка, которая была задана как img.src, не будет загруена на страницу. 
## Pug
* в самом начале файла pug можно сделать block varibles и запу=ихувать туда все переменные для разных страниц
## gulp
* сделать переменную path для основных папок src и dist
## IE
* img не реагирует на overflow: hidden, height отталкивает все элементы внизу  
## React
* Если вам нужно собрать всю информацию о множественных компонентах, или вам нужно чтобы два дочерних компонента взаимодействовали между собой, то переместите state на верх к родителю, чтобы state находился в родителе этих двух компонентов. Этот родитель может передавать этот state через props своим потомкам, таким образом все компоненты будет синхронизованны между собой и со своим общим родителем. (из документации React)
* Для того чтобы менять state родительского компонента из дочернего, нужно в родительском создать функцию, которую передать в дочерний, и вызвать ее там, чтобы изменить родительский state. Нельзя из дочернего конпонента изменить state родительского, потому что родительский state для дочернего дотупен только для чтения(видимо это связано с безопасностью).
* В react компонентах принято соглашение, что аттрибуты которые обрабатывают события нозывают с префикса on (onClick), а функции обработчики нызвают c префикса handle (handleClick).
