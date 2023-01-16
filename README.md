```Last login: Mon Jan 16 07:23:22 on console
denislebedev@SBM-MSK-MB01 ~ % ssh dlebedev@213.167.46.157 -i Keys/dlebedev -p 55193
Enter passphrase for key 'Keys/dlebedev': 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 5.4.0-136-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon 16 Jan 2023 06:38:38 AM UTC

  System load:                      0.0
  Usage of /:                       45.9% of 15.15GB
  Memory usage:                     23%
  Swap usage:                       0%
  Processes:                        154
  Users logged in:                  0
  IPv4 address for br-fe4095543098: 172.18.0.1
  IPv4 address for docker0:         172.17.0.1
  IPv4 address for ens18:           192.168.1.31

 * Strictly confined Kubernetes makes edge and IoT secure. Learn how MicroK8s
   just raised the bar for easy, resilient and secure K8s cluster deployment.

   https://ubuntu.com/engage/secure-kubernetes-at-the-edge

1 update can be applied immediately.
To see these additional updates run: apt list --upgradable

New release '22.04.1 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


*** System restart required ***
Last login: Mon Jan 16 04:18:21 2023 from 109.252.171.78
dlebedev@dont-touch:~$ sudo -s
[sudo] password for dlebedev: 
root@dont-touch:/home/dlebedev# cd
root@dont-touch:~# cd git/devops-netology/
root@dont-touch:~/git/devops-netology# ls
 3script_py.sh   branching   has_been_moved.txt   README.md   terraform  'Диаграмма без названия.drawio'
root@dont-touch:~/git/devops-netology# nano README.md 




















  GNU nano 4.8                                                                                     README.md                                                                                                
1.

Необходимо найти opid операции:

db.currentOp({ "active" : true, "secs_running" : { "$gt" : 180 }})

{
    "inprog" : [
        {
            //...
            "opid" : 12345,
            "secs_running" : NumberLong(123)
            //...
        }
    ]
}

Завершить принудительно

db.killOp(12345)


 Использовать метод maxTimeMS() для установки предела исполнения по времени операций
 Используя Database Profiler, отловить медленные операции. С помощью executionStats проанализировать. Попробовать
оптимизировать: удалить или добавить индексы, настроить шардинг и т.д.


2.



Возможнo вся память занята истекшими ключами, но еще не удаленными. Redis заблокировался (ACTIVE_EXPIRE_CYCLE_LOOKUPS_PER_LOOP), чтобы вывести из DB удаленные ключи и снизить их количество менее 25%. Т.к>



3.



Из документации MySQL могут быть три причины
1)Слишком объемные запросы на миллионы строк, рекомендуется увеличение параметра net_read_timeout
2)Малое значение параметра connect_timeout, клиент не успевает установить соединение.
3)Размер сообщения/запроса превышает размер буфера max_allowed_packet на сервере или max_allowed_packet на строне клиента.


Пути решения
1)Увеличить на сервере MySQL wait_timeout, max_allowed_packet, net_write_timeout и net_read_timeout
2)В SQLAlchemy уменьшить pool_recycle, wait_timeout
3)При исчезновении ошибки Lost connection to MySQL server during query возвращать по одному параметры в исходное состояние - для локализации проблемы.


4.


Postgres недостаточно памяти


1)По возможности добавить ресурсов RAM, провести отключить или перенести ненужные приложения.

^G Get Help      ^O Write Out     ^W Where Is      ^K Cut Text      ^J Justify       ^C Cur Pos       M-U Undo         M-A Mark Text    M-] To Bracket   M-Q Previous     ^B Back          ^◀ Prev Word
^X Exit          ^R Read File     ^\ Replace       ^U Paste Text    ^T To Spell      ^_ Go To Line    M-E Redo         M-6 Copy Text    ^Q Where Was     M-W Next         ^F Forward       ^▶ Next Word
```
