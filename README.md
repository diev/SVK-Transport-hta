# ![svktrans.png](docs/images/svktrans.png) [SVK Transport](http://diev.github.io/SVK-Transport-hta)

[![Build status](https://ci.appveyor.com/api/projects/status/1mvedcg27p6n7aj0?svg=true)](https://ci.appveyor.com/project/diev/svk-transport-hta)

Прием и отправка платежной XML информации, бинарных информационных и файлов 
статистики по HTTP протоколу в систему СВК Банка России.  

![Рабочее окно приложения](docs/images/screen.png)

Данное HTA-приложение осуществляет прием и отправку платежной XML информации, 
бинарных информационных и файлов статистики по HTTP протоколу.  
В отличии от ресурсоёмких аналогов (Эталонная реализация, УТА, SVKGate, 
Файловый адаптер СВК и др.) выглядит крошечной и шустрой утилитой, 
тем не менее обладающей достаточно развитым функционалом.

Смотрите также проекты 
[PTK-PSD Browser](http://diev.github.io/PTK-PSD-Browser-hta) для просмотра 
информационных посылок ПТК ПСД Банка России и
[UFEBS Viewer](http://diev.github.io/UFEBS-Viewer-hta) для просмотра файлов 
УФЭБС.

## Основные возможности программы

* Простой и интуитивно понятный интерфейс;
* Полностью автоматический режим (включая дозвон) с настраиваемыми временными 
интервалами (достаточно положить файлы в соответствующие каталоги для отправки 
и забрать ответы из приемных каталогов);
* Все пользовательские настройки вынесены в текстовый INI-файл, снабженный 
подробнейшими комментариями;
* Подробное логирование. Удобочитаемые текстовые логи;
* Работа по настраиваемому гибкому расписанию;
* Обход известных ошибок серверов РЦИ;
* Возможность работы с telnet аутентификацией и с раздельной 
web-аутентификацией.

## Замечания к использованию

* Распаковать дистрибутивный `zip` из 
[Releases](https://github.com/diev/SVK-Transport/releases) в отдельную папку.
* Программа из соображений защиты IE работает только с локального диска!
* До первого запуска программы внимательно изучите и отредактируйте 
`SVKTrans.ini`.
* Для отправки информационных сообщений требуется MSXML версии 4.0 или выше. 
Программа при старте проверяет его наличие, выдавая предупреждение при его 
отсутствии. Загрузить MSXML 6.1 можно с сайта 
[Microsoft](http://www.microsoft.com/downloads/details.aspx?FamilyID=d21c292c-368b-4ce1-9dab-3e9827b70604&displayLang=ru).
* Запускать следует `SVKTrans.hta`, снимать зависший - `mshta.exe` 
(В Windows 10 - *Microsoft(R) HTML приложение (32 бита)*).
* В Windows 7+ (проверено и в Windows 10) встроенная регистрация прилагаемых 
DLL может выдать ошибку с кодом 0x80004005. Это срабатывает защита Windows. 
Требуется пойти в "Пуск" -> "Все программы" -> "Стандартные", правой кнопкой 
мыши кликнуть на "Командная строка" -> "Запуск от имени администратора" 
(runas в этом не поможет!) и проделать регистрацию вручную:

```
      cd \SVKTrans
      regsvr32 socket.dll
      regsvr32 xbuffer.dll
```

## Дополнительная информация на сайте Банка России

* [Информация о новых версиях программного 
обеспечения](http://www.cbr.ru/mcirabis/?PrtId=itest) (СВК, УТА).

## История версий

Проект импортирован на GitHub с версии 2.9.11 с его страницы на 
[Bitbucket](https://bitbucket.org/html-applications/svk-transport).  
О более старой истории первоначального автора **mozers** есть в прилагаемом 
[файле](docs/changelog.md).

## Лицензионное соглашение

Licensed under the [Apache License, Version 2.0](LICENSE).  
(Вы можете использовать его совершенно свободно без всяких ограничений.)

Данные для обратной связи находятся в коде заголовка HTA приложения.
