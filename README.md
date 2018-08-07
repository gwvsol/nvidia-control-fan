# nvidia-control-fan
# Automatic fan speed control for NVIDIA graphics cards in overclocking mode

Программа для автоматической регулировки скорости вращения вентиляторов видеокарт NVIDIA 
в режиме overclocking

Для работы программы необходимо установить следующие зависимости:
sudo apt install zenity
А так же отредактировать переменные программы по используемых в системе текстовых редакторах 

# Справка по работе с программой
h или help - справка
r          - Ручное включение регулировки скорости вращения
on         - Включение автоматичекой регулировки
off        - Выключение автоматической регулировки
m          - Включение мониторинга работы программы
e          - Редактирование файла настроек программы
Если программа включена без передачи каких-либо параметров, включается графичесский интерфейс упарвления
и ожидает выбора соответствующего выбора меню. Если ранее работа скрипта была выключена передачей
соответствующего параметра скрипту или же выбором нужного меню графического интерфейса, графический 
интерфейс будет содержать только 2 меню, Редактирование и Включение регулировки. В другом случае
графический интерфейс будет включать в себя 4 пункта меню

Для автоматического включение скрипта, создаем в CRON следующее задание

SHELL=/bin/bash
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/usr/local/cuda/bin
@hourly /opt/mining/.bin/controlTemp REG # включение скрипта каждый час
*/10 * * * * /opt/mining/.bin/controlTemp REG # включение скрипта каждые 10 минут

Последняя строка правила cron используется для включения скрипта 1 раз в 10 мин. Предпоследняя используется для включения
скрипта 1 раз в час 
