# Задание 1.

На картинке изображена схема подключения хаба к свитчу. К хабу одновременно может подключаться не более 3 трех устройств. Если будет обнаружено, что подключено более 3 устройств, то необходимо запретить трафик с дополнительных устройств и отправить уведомление о нарушении.

Как необходимо настроить порт Fa0/5 на свитче?

Отправьте список команд.


enable  \
configure terminal  

interface fastEthernet 0/5  \
 switchport mode access  \
 switchport port-security  \
 switchport port-security maximum 3  \
 switchport port-security violation restrict  \
end  

write memory  

#Задание 2.

Для отдела мониторинга необходимо настроить view monitoring, в котором можно будет делать следующие операции:

Смотреть логи устройства  \
Смотреть таблицу MAC адресов  \
Смотреть таблицу arp  \
Смотреть полную конфигурацию свитча  \
Отправьте конфигурацию parser view monitoring.  \

enable view  \
configure terminal

parser view monitoring inclusive  \
 secret 5 your_password_here

 commands exec include show logging  \
 commands exec include show mac address-table  \
 commands exec include show arp  \
 commands exec include show running-config  \

end
