# Домашнее задание по теме «Загрузка ОС. init. Systemd»

## Задание 1

На лекции мы рассмотрели загрузку ядра и дополнительных модулей. Почему сразу не сделано ядро со всеми модулями? Так бы смогли избавиться от initrd…

Приведите ответ в свободной форме со своим комментарием.

### Ответ: 

Благодаря initrd оно может запуститься независимо от конкретной файловой системы на устройстве. 

## Задание 2

Существует ли возможность загрузить несколько ядер ОС?

Например, ОС Linux является многопользовательской и разные пользователи хотят загрузить разные версии ядра.

Приведите ответ в свободной форме со своим комментарием.

### Ответ: 

Ядро - это, по сути, и есть главная часть операционной системы.
Поэтому запустить несколько ядер - значит запустить несколько операционных систем.
Это можно делать при помощи виртуальных машин 

## Задание 3

Выполните systemd-analyze blame.

Укажите, какие модули загружаются дольше всего.

### Ответ: 

дольше всего у меня загружается кэш обновлений после старта системы 
"dnf-makecache.service"

```bash
[LIV@localhost ~]$ systemd-analyze blame
    1min 23.124s dnf-makecache.service
          8.096s plymouth-quit-wait.service
          4.766s kdump.service
          1.383s tuned.service
          1.109s dracut-initqueue.service
          1.045s udisks2.service
          1.038s NetworkManager-wait-online.service
           958ms vdo.service
           935ms systemd-udev-settle.service
           720ms firewalld.service
           707ms packagekit.service
           681ms libvirtd.service
           650ms initrd-switch-root.service
           553ms accounts-daemon.service
           507ms polkit.service
           460ms upower.service
           443ms avahi-daemon.service
           401ms systemd-logind.service
           377ms chronyd.service
           374ms systemd-machined.service
           351ms user@42.service
           317ms smartd.service
           309ms systemd-vconsole-setup.service
           263ms rtkit-daemon.service
           255ms colord.service
           255ms systemd-udev-trigger.service
           245ms ksm.service
           235ms unbound-anchor.service
           208ms dracut-shutdown.service
           203ms ModemManager.service
           201ms user@1000.service
           192ms dev-hugepages.mount
           192ms systemd-journald.service
           189ms dev-mapper-cs\x2dswap.swap
           188ms sysroot.mount
           174ms dev-mqueue.mount
           173ms kmod-static-nodes.service
           165ms gdm.service
           161ms systemd-remount-fs.service
           146ms systemd-modules-load.service
           130ms lvm2-monitor.service
           129ms systemd-udevd.service
           128ms auditd.service
           123ms ksmtuned.service
           122ms nis-domainname.service
           122ms lvm2-pvscan@8:2.service
           121ms systemd-user-sessions.service
           113ms gssproxy.service
           110ms var-lib-nfs-rpc_pipefs.mount
           109ms systemd-tmpfiles-setup-dev.service
           108ms cups.service
           105ms plymouth-start.service
           105ms sshd.service
           102ms initrd-parse-etc.service
            89ms rsyslog.service
            84ms sys-kernel-debug.mount
            75ms boot.mount
            73ms systemd-update-utmp-runlevel.service
            73ms systemd-tmpfiles-setup.service
            72ms import-state.service
            70ms systemd-sysctl.service
            67ms rpcbind.service


## Задание 4

Какой командой вы посмотрите ошибки ядра, произошедшие начиная со вчерашнего дня?

Напишите ответ в свободной форме.

### Ответ: 

journalctl --since yesterday 

## Задание 5

Запустите команду loginctl user-status.

Что выполняет, для чего предназначена эта утилита?

### Ответ: 

Показывает краткую информацию о состоянии выполнения об одном или нескольких вошедших в систему пользователях, самые последние данные из журнала. Принимает одно или несколько имен пользователей или числовых идентификаторов пользователей в качестве параметров. Если параметры не переданы, статус отображается для пользователя сеанса вызывающего абонента

## Задание 6

Есть ли у вас на машине службы, которые не смогли запуститься? Как вы это определили?

Приведите ответ в свободной форме.

### Ответ: 


sudo systemctl list-unit-files --type=service показывает службы включённые и выключенные

sudo systemctl list-units --state failed --type service Службы которые не за пустились из ошибки




# Дополнительные задания (со звездочкой)*
Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.



## Задание 7

Существует такой вид виртуализации как контейнеризация: контейнеры создаются на уровне ОС и работают в изолированных пространствах.

Вопрос: что произойдет, если в хостовой ОС установлен upstart, а в запущенном контейнере - systemd?

Приведите ответ в свободной форме со своим комментарием.

### Ответ: 



## Задание 8

Можно ли с помощью systemd отмонтировать раздел/устройство?

Приведите ответ в свободной форме.

### Ответ: 

