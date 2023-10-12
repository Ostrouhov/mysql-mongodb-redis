# MySQL, MongoDB, Redis
## Задание 1
> **use my_db** - сменить текущую БД на my_db
> 
> **show tables;** - посмотреть, какие таблицы есть в my_db
>
> **desc user_private_message;** - посмотреть, какие типы полей есть в таблице user_private_message
## Задание 2
>**select name Name from discussion_group where approve_required = true** - запрос, который вернет название дискуссионных групп, которые требуют подтверждение регистрации, т.е. таблица - discussion_group, поле - approve_required равно 1 или true
## Задание 3
>**select greatest(message_id, user_from_id, user_to_id) max_id, date_format(read_time, '%Y-%m-%d') read_time, date_format(send_time, '%Y-%m-%d') send_time, message_text from user_private_message where send_time >= '2020-11-01' and send_time < '2020-12-01' and message_text LIKE 'A%' and datediff(read_time, send_time) <= 10;** - напиши запрос, который из таблицы user_private_message отберет записи: отправленные в ноябре 2020 года (поле send_time), текст сообщения начинается на 'A' (поле message_text), прочитанные не позже 10 дней от даты отправки (поле read_time)
## Задание 4
>
