# Цель работы:
Написать bash скрипт, анализирующий логи nginx
# Реализованные функции:
Он выполняет следующие функции:
 * Имеет защиту от многократного запуска;
 * Поддерживает поиск самых популярных и самых непопулярных ip, запросов по роутам, а так же список ошибок 4хх и 5хх;
 * Проверяет наличие файла по указанному маршруту;
 * Проверяет что по указанному пути находится непустой файл;
# Prerequirements
 1. Командная оболочка *bash*;
 2. Пакет системы контроля версий *git* (для более простого способа скачивания скрипта);
# Использование:
1. Слонировать репозиторий со скриптом;
2. запустить скрипт с нужными параметрами: ` bash nginxparser.sh <путь к файлу логов> <опция> <количество отображаемых результатов> `. первые 2 параметра обязательны.
 1. Поддерживаемые команды: toplinks - топ самых популярных ip, lowlinks - топ самых непопулярных ip, toproutes - топ самых популярных запросов по роутам, lowroutes - топ самых непопулярных запросов, errors - список запросов вернувших ошибки;
 2. количество отображаемых результатов вводится в формате числа. если число не указано то по умолчанию будет показано 15 результатов;
3. Пример запуска: ` bash nginxparser.sh logfile.log toplinks 10 ` - такой запрос выведет 10 самых часто запрашиваемых ip.
# Список возвращаемых кодов:
* 0 - успешное окончание работы скрипта; 
* 1 - скрипт уже запущен;
* 2 - Не указаны все требуемые параметры;
* 3 - файл пуст или некорректен;
* 4 - имя файла пустое;
* 6 - неправильно указан параметр поиска.