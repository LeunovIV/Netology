# Домашнее задание к занятию "2.6 Процессы, управление процессами "


## Задание 1.
Объясните, что делает команда:

ps aux | grep root | wc -l >> root

Не захватывает ли она чего лишнего? Можно ли решить эту задачу лучше / правильнее?

Ответ напишите в свободной форме.

### Ответ: 

Подсчитает количество процессов пользователя root. 
ps -aux выводит список процессов, 

grep root берёт из вывода только строки, в которых есть подстрока root. 

wc -l считает количество строк 

указываем >> root чтобы перенаправить вывод комманды в конец файла root

При выполнении комманды "ps aux | grep root | wc -l >> root" в файл рут перенаправляетя не только число которое равно количеству процессов запущеных от пользователя root, но и +1 строка заголовка таблицы и все строки содержащие слово "root"

Для записи количества процессов запущенных от пользователя "ps -hU root | wc -l >> root"

## Задание 2
Напишите команду, которая выводит все запущенные процессы пользователя root в файл “userrootps”.

### Ответ: 

ps -hU root | wc -l > userrootps


## Задание 3
Начинающий администратор захотел вывести все запущенные процессы пользователя с логином “2” в файл “user2ps”.

Для этого он набрал команду:

ps -U 2> user_2_ps

Затем, он аналогично повторил для пользователя с логином “5” вывод в файл “user_5_ps”:

ps -U 5> user_5_ps

Вопрос:

Почему вывод этих команд и содержимое файлов сильно отличаются друг от друга? Как должны выглядеть правильные команды?

Примечание:

Если у вас в системе нет пользователей “2” и/или “5” (это нормальная ситуация), то утилита ps выводит только одну строку:

PID TTY TIME CMD

### Ответ: 


# Дополнительные задания (со звездочкой)*

Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.

## Задание 4
Сформируйте команду ps так, чтобы она выводила процессы, только запущенные от имени пользователя root, со следующими полями: команда (командная строка), id процесса, потребление процессора, потребление резидентной памяти (rss). Сортировка должна быть по потреблению памяти (rss), в обратном порядке (внизу - наибольшее потребление).

Команда должна содержать только ps и опции к ней, обрабатывать вывод другими командами нельзя.

Пришлите команду и её вывод.



### Ответ: 
```bash
[LIV@localhost ~]$ ps -U root --format="cmd pid %cpu rss" --sort rss
CMD                             PID %CPU   RSS
[kthreadd]                        2  0.0     0
[rcu_gp]                          3  0.0     0
[rcu_par_gp]                      4  0.0     0
[kworker/0:0H-events_highpr       6  0.0     0
[mm_percpu_wq]                    9  0.0     0
[rcu_tasks_rude_]                10  0.0     0
[rcu_tasks_trace]                11  0.0     0
[ksoftirqd/0]                    12  0.0     0
[rcu_sched]                      13  0.0     0
[migration/0]                    14  0.0     0
[watchdog/0]                     15  0.0     0
[cpuhp/0]                        16  0.0     0
[kdevtmpfs]                      18  0.0     0
[netns]                          19  0.0     0
[kauditd]                        20  0.0     0
[khungtaskd]                     21  0.0     0
[oom_reaper]                     22  0.0     0
[writeback]                      23  0.0     0
[kcompactd0]                     24  0.0     0
[ksmd]                           25  0.0     0
[khugepaged]                     26  0.0     0
[crypto]                         27  0.0     0
[kintegrityd]                    28  0.0     0
[kblockd]                        29  0.0     0
[blkcg_punt_bio]                 30  0.0     0
[tpm_dev_wq]                     31  0.0     0
[md]                             32  0.0     0
[edac-poller]                    33  0.0     0
[watchdogd]                      34  0.0     0
[kworker/0:1H-kblockd]           35  0.0     0
[kswapd0]                        69  0.0     0
[kthrotld]                      171  0.0     0
[acpi_thermal_pm]               172  0.0     0
[kmpath_rdacd]                  173  0.0     0
[kaluad]                        174  0.0     0
[ipv6_addrconf]                 175  0.0     0
[kstrp]                         177  0.0     0
[ipmi-msghandler]               311  0.0     0
[ata_sff]                       454  0.0     0
[scsi_eh_0]                     457  0.0     0
[scsi_tmf_0]                    459  0.0     0
[scsi_eh_1]                     461  0.0     0
[scsi_tmf_1]                    462  0.0     0
[scsi_eh_2]                     472  0.0     0
[scsi_tmf_2]                    474  0.0     0
[ttm_swap]                      478  0.0     0
[irq/18-vmwgfx]                 479  0.0     0
[card0-crtc0]                   480  0.0     0
[card0-crtc1]                   481  0.0     0
[card0-crtc2]                   482  0.0     0
[card0-crtc3]                   483  0.0     0
[card0-crtc4]                   484  0.0     0
[card0-crtc5]                   485  0.0     0
[card0-crtc6]                   486  0.0     0
[card0-crtc7]                   487  0.0     0
[kdmflush/253:0]                558  0.0     0
[kdmflush/253:1]                567  0.0     0
[xfsalloc]                      591  0.0     0
[xfs_mru_cache]                 592  0.0     0
[xfs-buf/dm-0]                  593  0.0     0
[xfs-conv/dm-0]                 594  0.0     0
[xfs-cil/dm-0]                  595  0.0     0
[xfs-reclaim/dm-]               596  0.0     0
[xfs-gc/dm-0]                   597  0.0     0
[xfs-log/dm-0]                  599  0.0     0
[xfsaild/dm-0]                  600  0.0     0
[xfs-buf/sda1]                  803  0.0     0
[xfs-conv/sda1]                 804  0.0     0
[xfs-cil/sda1]                  805  0.0     0
[xfs-reclaim/sda]               806  0.0     0
[xfs-gc/sda1]                   807  0.0     0
[xfs-log/sda1]                  809  0.0     0
[xfsaild/sda1]                  810  0.0     0
[rpciod]                        848  0.0     0
[xprtiod]                       849  0.0     0
[kworker/u2:0-events_unboun    2819  0.0     0
[kworker/u2:2-xfs-gc/dm-0]    13846  0.0     0
[kworker/0:0-ata_sff]         18808  0.0     0
[kworker/0:2-ata_sff]         18973  0.0     0
[kworker/0:1-events]          19135  0.0     0
/usr/sbin/dnsmasq --conf-fi    1649  0.0   364
gpg-agent --homedir /var/ca   10320  0.0   560
gpg-agent --homedir /var/ca   10189  0.0   620
gpg-agent --homedir /var/ca    2839  0.0   644
gpg-agent --homedir /var/ca   10284  0.0   680
sleep 60                      19279  0.0   848
nginx: master process nginx    9484  0.0   876
/sbin/auditd                    834  0.0  1704
/usr/sbin/alsactl -s -n 19      874  0.0  1740
/usr/sbin/mcelog --ignoreno     868  0.0  1928
/usr/sbin/atd -f               1270  0.0  2140
gpg-agent --homedir /var/ca    2878  0.0  2232
gpg-agent --homedir /var/ca    2852  0.0  2248
gpg-agent --homedir /var/ca    2866  0.0  2256
/bin/bash /usr/sbin/ksmtune     905  0.0  2284
/usr/sbin/crond -n             1271  0.0  3008
/usr/sbin/sedispatch            836  0.0  3196
/usr/sbin/gssproxy -D           999  0.0  3444
/usr/sbin/wpa_supplicant -c    1934  0.0  5360
/usr/sbin/smartd -n -q neve     864  0.0  5536
/usr/lib/systemd/systemd-ma     876  0.0  5824
/usr/sbin/sshd -D -oCiphers     994  0.0  6656
/usr/lib/systemd/systemd-lo     882  0.0  7956
/usr/sbin/rsyslogd -n          1264  0.0  8480
/usr/lib/systemd/systemd-ud     735  0.0  8996
/usr/libexec/upowerd           1920  0.0  9084
/usr/libexec/sssd/sssd_kcm     9807  0.1  9268
/usr/libexec/accounts-daemo     869  0.0  9304
/usr/sbin/gdm                  1267  0.0  9796
/usr/sbin/cupsd -l              998  0.0 10004
sshd: LIV [priv]              10751  0.0 11068
/usr/lib/systemd/systemd --       1  0.0 11384
/usr/lib/systemd/systemd-jo     697  0.0 11520
/usr/sbin/ModemManager          916  0.0 12996
gdm-session-worker [pam/gdm    9561  0.0 13632
/usr/libexec/udisks2/udisks     865  0.0 13780
/usr/sbin/NetworkManager --     985  0.0 18416
/usr/libexec/platform-pytho     995  0.2 25640
/usr/libexec/platform-pytho     915  0.0 33260
/usr/libexec/packagekitd       1935  0.0 336064
```
