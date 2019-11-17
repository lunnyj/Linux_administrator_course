# Vagrantfile с provision сборкой RAID10
В ходе выполнения домашнего задания, был выбран RAID 10-го уровня, в связи с этим добавлены 2 диска. Общее количество 6 дисков, размером по 500 Mb.

Состав provision скрипта мало чем отличается, от перечня последовательности действий в методчике, за исключением:
```bash
mkfs.ext4 /dev/md0 # 
```
и
```bash
echo "/dev/md0 /raid ext4 defaults 1 2" >> /etc/fstab # Записали в fstab информацию о RAID, чтобы при перезагрузке не было проблем с отмонтированными разделами
mount -a # монтируем все разделы
```