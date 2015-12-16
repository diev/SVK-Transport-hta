### ![goup.png](http://html-applications.bitbucket.org/images/goup.png) [Return to HTML Application page](http://html-applications.bitbucket.org) ###
---
## ![svk.png](http://html-applications.bitbucket.org/images/svk.png)  [SVK Transport](http://html-applications.bitbucket.org/svk-transport/readme.html) ##
Прием и отправка платежной XML информации, бинарных информационных и файлов статистики по HTTP протоколу в систему СВК Банка России. Смотрите также проект [PTK-PSD Browser](https://bitbucket.org/html-applications/ptkpsd-browser) для их просмотра.

![Рабочее окно приложения](screen.png "Рабочее окно приложения")

Данное HTA-приложение осуществляет прием и отправку платежной XML информации, бинарных информационных и файлов статистики по HTTP протоколу.
В отличии от ресурсоёмких аналогов (Эталонная реализация, УТА, SVKGate, Файловый адаптер СВК, и др.) выглядит крошечной и шустрой утилитой, тем не менее обладающей достаточно развитым функционалом.

### Основные возможности программы

* Простой и интуитивно понятный интерфейс;
* Полностью автоматический режим (включая дозвон) с настраиваемыми временными интервалами (достаточно положить файлы в соответствующие каталоги для отправки и забрать ответы из приемных каталогов);
* Все пользовательские настройки вынесены в текстовый INI-файл, снабженный подробнейшими комментариями;
* Подробное логирование. Удобочитаемые текстовые логи;
* Работа по настраиваемому гибкому расписанию;
* Обход известных ошибок серверов РЦИ;
* Возможность работы с telnet аутентификацией и с раздельной web-аутентификацией;

### Замечания к использованию

* До первого запуска программы внимательно изучите и отредактируйте *SVKTrans.ini*.
* Для отправки информационных сообщений требуется MSXML версии 4.0 или выше. Программа при старте проверяет его наличие, выдавая предупреждение при его отсутствии. Загрузить MSXML 6.1 можно с сайта [Microsoft](http://www.microsoft.com/downloads/details.aspx?FamilyID=d21c292c-368b-4ce1-9dab-3e9827b70604&displayLang=ru).
* Никаких ухищрений для защиты от дебильных антивирей не предпринималось, поэтому если пользуетесь одним из них, заносите программу в список исключений.
* Запускать следует *SVKTrans.hta*, снимать зависший - *mshta.exe* (В Windows 10 - *Microsoft(R) HTML приложение (32 бита)*).
* В Windows 7+ (проверено и в Windows 10) встроенная регистрация прилагаемых DLL может выдать ошибку с кодом 0x80004005. Это срабатывает защита Windows. Требуется пойти в "Пуск" -> "Все программы" -> "Стандартные", правой кнопкой мыши кликнуть на "Командная строка" -> "Запуск от имени администратора" (runas в этом не поможет!) и проделать регистрацию вручную:

```
#!cmd
cd \svktrans
regsvr32 socket.dll
regsvr32 xbuffer.dll

```

### Загрузка

* [Дистрибутив](https://bitbucket.org/html-applications/svk-transport/downloads)
* [Исходный код](https://bitbucket.org/html-applications/svk-transport/src)

### Благодарности

Огромное СПАСИБО участникам форума на [BANKIR.RU](http://dom.bankir.ru/showthread.php?t=75256&goto=newpost): *Посторонним В* (за поддержку), *KrLL* и *badik* (за некоторые решения) и, конечно, *vk* (за вытаскивание из тупиковой ситуации).  
Выражаю признательность всем кто принимает участие в тестировании программы. Она стала лучше в основном благодаря вашим предложениям.

### Лицензионное соглашение

Приложение распространяется по лицензии [GPL](http://ru.wikipedia.org/wiki/GPL).  
Вы можете использовать его совершенно свободно без всяких ограничений.

Данные для обратной связи находятся в коде заголовка HTA приложения.