###HW3

#Работа с LVM (все действия залоггированы в файле lvm.txt)

1. Создал PV, VG и LV.
2. Создал еще один LV на имеющейся VG.
3. Создал на LV файловую систему и смонтировал его в /data/
4. Добавил в VG еще один диск.
5. Расширил LV за счет этого диска.
6. Расширил ФС на этом LV.
7. Уменьшил LV.
8. Создал снапшот LV и смонтировал его в /data-snap/
9. Проверил работу снапшота удалив файл из /data/ и восстановив его из снапшота.
10. Создал зеркальный LV.

#Домашняя работа (все действия залоггированы в файле homework.txt)

1. Уменьшил том под / до 8G.
2. Выделил том под /home
3. Выделил том под /var - сделал его в mirror.
4. Сделал том для снэпшотов /home и проверил его работу.
5. Прописал монтирование томом /home и /var в fstab.

#Задание со звездочкой (все действия залоггированы в файле zfs.txt)

1. Установил репозиторий zfs: ```yum install http://download.zfsonlinux.org/epel/zfs-release.el7_4.noarch.rpm -y```
2. Установил zfs: ```yum install zfs -y```
3. После перезагрузки загрузил модули zfs: ```modprobe zfs```
4. Создал пул zfs на диске sdb с кешем на отдельном диске sdc: ```zpool create pool0 /dev/sdb cache /dev/sdc```
5. Замонтировал пул в директорию /opt : ```zfs set mountpoint=/opt/ pool0```
6. Создал файлы в директории /opt : ```touch /opt/file{1..10}```
7. Создал snapshot пула pool0: ```zfs snapshot pool0@snap0```
8. Удалил некоторые файлы из директории /opt
9. Восстановил состояние пула pool0 из снапшота: ```zfs rollback pool0@snap0```

