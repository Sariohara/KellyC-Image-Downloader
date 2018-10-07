# KellyCFavourites
Store you personal favourite publications localy

 <br>
# RU <br>

Расширение для каталогизации, быстрого сохранения понравившихся публикаций. Есть возможность экспорта уже имеющихся в профиле избранных публикаций и опционально дальнейшая их синхронизация.

Поддерживаются все фендомы и основные страницы сайта joyreactor.cc, old.reactor.cc

Функционал

- Сохранение публикаций и комментариев в локальное хранилище
- Раздел на сайте с альтернативным каталогом сохраненных публикаций (данные хранятся в локальном хранилище браузера в переключаемых профилях)

- Возможность выгрузки избранных публикаций из основного раздела сайта в файл (данные будут сохранены в файл-список, который в дальнейшем можно загрузить в профиль избранного и выполнять дальнейшую сортировку \ скачивание изображений и т.д.) 
- Быстрое сохранение оригиналов изображений из публикации по кнопке (кнопка вынесена в блок соц.сетей)
- Возможность скачать все избранные публикации из локального хранилища (настройки формата имен сохраняемых файлов, фильтрация по категориям)

Управление профилями данных :

Можно хранить избранные публикации в нескольких хранилищах - профилях. Профили можно переключать \ сохранять \ удалять \ переносить в другой браузер \ пк. (импорт \ экспорт выполняется из json файла профиля, который можно скачать или загрузить в настройках расширения)
 
Профили актуальны при импорте данных нескольких пользователей. Можно переключаться между профилями с разными коллекциями избранного в любой момент времени.

Замечания :

При импорте данных время между итерациями скачивания страниц избранного от 2-30 (паузы) секунд. В общем случае время выгрузки равно 2-3 сек. * кол-во страниц. 

Расширения не использует какие-либо дополнительные сторонние библиотеки \ не лезет на левые ресурсы. Только расширение функционала конкретного сайта.

# Сборка расширения из исходных файлов

Для сборки расширения достаточно выполнить файл <b>merge.bat</b> либо собрать в один файл нижеперечисленные файлы в соответствующем порядке любым доступным способом.
После сборки расширение можно добавить в режиме разработчика в любой браузер поддерживающий chrome API <br>

Список поддерживаемых браузеров: <br>

FireFox, Opera, Chrome, Edge (с существеными ограничениями, на 23.09.18 отсутсвуют методы скачивания файлов)<br>
<br>

>	\widget\kellyTooltip.js (виджет вывода подсказок и всплывающих окон)<br>
>	\widget\kellyTileGrid.js (виджет тайловой сетки изображений)<br>
>	\widget\kellyImageView.js (виджет вывода изображений)<br>
>	\lib\kellyLoc.js (вывод локализованых строк)<br>
>	\lib\kellyStorageManager.js (контроллер управления локальными данными)<br>
>	\lib\kellyThreadWork.js (контроллер потоковой загрузки данных)<br>
>	\lib\kellyGrabber.js (контроллер пакетной выгрузки элементов избранного)<br>
>	\lib\kellyTools.js	(набор дополнительных методов используемых всеми библиотеками из каталога lib)<br>
>	\lib\kellyFavItems.js (файл окружения расширения)<br>
>	\env\profiles\joyreactor.js (файл профиля домена)<br>
>	\init.js (инициализация клиентской части)<br>
<br>

Объединить в файл khelper.user.js<br><br>

> \lib\kellyTools.js (набор дополнительных методов используемых всеми библиотеками из каталога lib<br>
> \lib\kellyDispetcher.js (шлюз для обработки любых методов требующих участия Browser API)<br>
> \init.bg.js (инициализация фонового процесса)<br>
<br>

Объединить в файл khelper.bg.js<br><br>

файлы с префиксом init, папки lib, widget нужны только при сборке и в итоговом архиве расширения не требуются

Для включения режима отладки задать переменную debug = 1 в файле merge.bat и пересобрать проект (либо включить задать в настройках расширения  Настройки -> Остальное)