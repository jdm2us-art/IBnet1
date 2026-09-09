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
