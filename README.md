```
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
