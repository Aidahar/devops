## Part 1. Установка ОС

#### Установить **Ubuntu 20.04 Server LTS** без графического интерфейса. (Используем программу для виртуализации - VirtualBox)

- Узнайте версию Ubuntu, выполнив команду \
`cat /etc/issue.`

  ![etc_isue](screen/etc_issue.png)

## Part 2. Создание пользователя

#### Создать пользователя, отличного от пользователя, который создавался при установке. 

- Вставьте скриншот вызова команды для создания пользователя.

  ![add_user](screen/add_user.png)

 - Пользователь должен быть добавлен в группу `adm`.

    ![adm_user](screen/user_adm.png)

- Новый пользователь должен быть в выводе команды \
`cat /etc/passwd`

  ![cat_passwd](screen/cat_passwd.png)

## Part 3. Настройка сети ОС

#### Задать название машины вида user-1
- Задать название машины вида user-1

  ![hostname](screen/hostname.png)

#### Установить временную зону, соответствующую вашему текущему местоположению.

![timezone](screen/localtime.png)

#### Вывести названия сетевых интерфейсов с помощью консольной команды.

![timezone](screen/ip_link.png)

- lo (loopback device) - виртуальный сетевой интерфейс. Используется для отладки сетевых программ и запуска серверных приложений на локальной машине по адресу 127.0.0.1 (localhost).

#### Используя консольную команду получить ip адрес устройства, на котором вы работаете, от DHCP сервера. 

![dhcp](screen/ip_dhcp.png)

- Dynamic Host Configuration Protocol — протокол динамической настройки узла, позволяющий сетевым устройствам автоматически получать IP-адрес и другие параметры, необходимые для работы в сети TCP/IP.

#### Определить и вывести на экран внешний ip-адрес шлюза (ip) и внутренний IP-адрес шлюза, он же ip-адрес по умолчанию (gw). 

- внешний IP
![ip](screen/ip_addr.png)

- внутренний IP адрес шлюза

  ![gw](screen/ip_gw.png)

- Задать статичные настройки ip, gw, dns (использовать публичный DNS серверы, например 1.1.1.1 или 8.8.8.8).

  ![ip_static](screen/ip_static.png)


 - Перезагрузить виртуальную машину. Убедиться, что статичные сетевые настройки (ip, gw, dns) соответствуют заданным в предыдущем пункте. 

- Успешно пропинговать удаленные хосты `1.1.1.1` и `ya.ru` и вставить в отчёт скрин с выводом команды. В выводе команды должна быть фраза "0% packet loss".

  ![ping](screen/ping.png)

## Part 4. Обновление ОС

#### Обновить системные пакеты до последней на момент выполнения задания версии.  

  ![upgrade](screen/upgrade.png)

## Part 5. Использование команды **sudo**

##### Разрешить пользователю, выполнять команду sudo.

![image](screen/sudo.png)

- sudo позволяет другому пользователю выполнять команду от суперпользователя, либо другого пользователя. Команда используется для разграничения полномочий между пользователями входящими в группу sudo, не выдавая при этом пароля root

- Поменять hostname ОС от имени пользователя, созданного в пункте [Part 2] используя sudo).
![sudo_ira](screen/sudo_ira.png)

  ![sudo_change](screen/sudo_hostname.png)

## Part 6. Установка и настройка службы времени

- Вывести время, часового пояса, в котором вы сейчас находитесь.
![date](screen/data.png)
- Вывод следующей команды должен содержать `NTPSynchronized=yes`: 
timedatectl show
- Вставить скрины с корректным временем и выводом команды в отчёт.
![timedatectl](screen/timedatectl.png)

## Part 7. Установка и использование текстовых редакторов 

- установка редакторов командой `sudo apt install vim nano micro`
#### Используя каждый из трех выбранных редакторов, создайте файл *test_X.txt*, где X название редактора, в котором создан файл. Напишите в нём свой никнейм, закройте файл с сохранением изменений.

- Vim

  ![vim](screen/vim_save.png)

- для выхода и сохранения нужно сочетание клавишь `:wq`

- Nano

  ![nano](screen/nano_save.png)
- для выхода и сохранения последовательность клавишь `ctrl+O` и подтвердить выбраный файл для сохранения и `ctrl+X` для выхода

- Micro

  ![micro](screen/micro_save.png)
- для выхода и сохранения последовательность клавишь ctrl+S и ctrl+Q
- содержимое всех файлов
![all](screen/test_all.png)


#### Используя каждый из трех выбранных редакторов, откройте файл на редактирование, отредактируйте файл, заменив никнейм на строку "21 School 21", закройте файл без сохранения изменений.

- Vim 
![vim_no](screen/vim_no_save.png)
- выход без сохранения `:q!`

- Nano
![nano_no](screen/nano_no_save.png)
- выход без сохранения  ctrl+x и N

- Micro
![micro_no](screen/micro_no_save.png)
- выход без сохранения `ctrl + Q` и N

- содержимое всех файлов
![all_2](screen/test_all_2.png)

#### Используя каждый из трех выбранных редакторов, отредактируйте файл ещё раз (по аналогии с предыдущим пунктом), а затем освойте функции поиска по содержимому файла (слово) и замены слова на любое другое.

- результаты поиска слова.

  ### Vim

- для поиска нажимаем `/что ищем`

  ![vim_find](screen/vim_find.png)

- для замены вводим `:%s/что меняем/на что`

  ![vim_find](screen/vim_replace.png)

  ### Nano

- для поиска нажимаем `ctrl+W` и пишем что ищем 

  ![nano_find](screen/nano_find.png)

- для замены вводим `ctrl+\` и пишем 'что заменить' `enter` 'на что'

  ![vim_find](screen/nano_replace.png)

### Micro

- для поиска нажимаем `ctrl+F` и пишем что ищем 

  ![nano_find](screen/micro_find.png)

- для замены вводим `ctrl + E` открывается командная строка, печатаем `replace` что  на что, подтверждаем изменения

  ![vim_find](screen/micro_replace.png)

## Part 8. Установка и базовая настройка сервиса **SSHD**

- Установить службу `sshd`
![sshd](screen/sshd.png)

- Добавить автостарт службы при загрузке системы. 
![sshd_enable](screen/sshd_enable.png)

- Перенастраиваем службу `sshd` на `порт 2022` редактируя конфиг `sudo vim /etc/ssh/sshd.config`
![sshd_conf](screen/sshd_2022.png)

- перзапускаем службу для принятия настроек
![sshd_restart](screen/sshd_restart.png)

- Используя команду `ps`, показать наличие процесса `sshd`. Для этого к команде нужно подобрать ключи.

  ![sshd_ps](screen/sshd_ps.png)

Утилита `ps` одна из самых простых и в то же время часто используемых программ для просмотра списка процессов в Linux.

-a - выбрать все процессы, кроме фоновых

-u - выбрать процессы пользователя

-x - При отображении процессов, соответствующих другим параметрам, включите процессы, у которых нет управляющего терминала. Это противоположность опции -X. Если в одной команде указаны и -X, и -x, то ps будет использовать тот, который был указан последним.

- Перезагружаем систему командой `reboot`

- Вывод команды `netstat -tan`
![sshd_netstat](screen/sshd_netstat.png)

Программа `netstat` показывает статус сети, флаг `-t` отображает список соединения TCP, флаг `-a` показывает список всех портов, флаг `-n` отображает в числовом формате, не отображая имя хоста.

Расшифровка столбцов: 
1 - протокол подключения, 2 - полученные пакеты, 3 - отправленные пакеты, 4 - локальный адрес, 5 - удаленный адресс, 6 - статус.

Адресс `0.0.0.0` используется в сети как немаршрутизируемый адрес IPv4, он используется во время инициализации системы, когда устройство использует его до того, как ему будет назначен реальный IP-адрес, в качестве адреса по умолчанию.

## Part 9. Установка и использование утилит **top**, **htop**

#### Top
- По выводу команды top определить и написать в отчёте:

uptime 1час 54 минуты

количество авторизованных пользователей 1 user

общую загрузку системы load average 0,00 0,00 0,00

общее количество процессов tasks 94

загрузку cpu 
![top_cpu](screen/top_cpu.png)
загрузку памяти
![top_mem](screen/top_mem.png)
pid процесса занимающего больше всего памяти
![top_pid_mem](screen/top_pid_mem.png)
pid процесса, занимающего больше всего процессорного времени
![top_pid_cpu](screen/top_pid_cpu.png)

- В отчёт вставить скрин с выводом команды htop:

отсортированному по PID
![htop_pid](screen/htop_pid.png)
отсортированному по PERCENT_CPU
![htop_cpu](screen/htop_cpu_perc.png)
отсортированному по PERCENT_MEM
![htop_mem](screen/htop_mem_perc.png)
отсортированному по TIME
![htop_time](screen/htop_time.png)

отфильтрованному для процесса sshd
![htop_sshd](screen/htop_sshd.png)

с процессом syslog, найденным, используя поиск
![htop_syslog](screen/htop_syslog.png)

с добавленным выводом hostname, clock и uptime
![htop_add](screen/htop_add.png)

## Part 10. Использование утилиты **fdisk**
- Запустить команду fdisk -l.

- название жесткого диска /dev/sda
- его размер 10G
- количество секторов 20971520
- размер swap 1.47G

## Part 11. Использование утилиты df
- Запустить команду df /

- размер раздела 8408452
- размер занятого пространства 4745636
- размер свободного пространства 3214100
- процент использования 60%

единица измерения в выводе килобайт

- Запустить команду df -Th /

- размер раздела 8.1G
- размер занятого пространства 4.6G
- размер свободного пространства 3.1G
- процент использования 60%

тип файловой системы для раздела ext4(extendet file system)

## Part 12. Использование утилиты du

- Запустить команду du и вывести размер папок (в байтах)
#### /home

  ![du_home_b](screen/du_home_b.png)

#### /var

  ![du_var_b](screen/du_var_b.png)

#### /var/log

  ![du_var_log_b](screen/du_var_log_b.png)

- Вывести размер папок (в человекочитаемом виде)
#### /home

  ![du_home_h](screen/du_home_h.png)

#### /var

  ![du_var_h](screen/du_var_h.png)

#### /var/log

  ![du_var_log_h](screen/du_var_log_h.png)

- Вывести размер всего содержимого в /var/log (не общее, а каждого вложенного элемента, используя *)
`sudo du -ha /var/log/*`

  ![du_var_log_ha](screen/du_var_log_ha.png)

## Part 13. Установка и использование утилиты ncdu
- Установить утилиту ncdu

- Запускаем командой `ncdu /` Вывести размер папок /home, /var, /var/log.

  ![ncdu](screen/ncdu_root.png)

  ![ncdu_log](screen/ncdu_var_log.png)

## Part 14. Работа с системными журналами
- Открыть для просмотра:

1. /var/log/dmesg

    ![log_dmsg](screen/dmsg.png)

2. /var/log/syslog

    ![log_syslog](screen/syslog.png)

3. /var/log/auth.log

    ![log_auth](screen/auth.png)

- время последней успешной авторизации, имя пользователя и метод входа в систему

  ![login](screen/login.png)

- Перезапустить службу SSHd

  ![sshd](screen/log_restart.png)

- Вставить в отчёт скрин с сообщением о рестарте службы (искать в логах) `sudo cat /var/log/syslog`

  ![syslog_restart](screen/log_restart_sshd.png)

## Part 15. Использование планировщика заданий CRON

- Используя планировщик заданий, запустите команду uptime через каждые 2 минуты.

  ![cron](screen/cron_e.png)

- Найти в системных журналах строчки (минимум две в заданном временном диапазоне) о выполнении.

  ![image](screen/cron_uptime.png)

- Вывести на экран список текущих заданий для CRON.

  ![image](screen/cron_l.png)

- Удалите все задания из планировщика заданий.

  ![image](screen/cron_remove.png)