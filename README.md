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
>**select greatest(message_id, user_from_id, user_to_id) max_id, date_format(read_time, '%Y-%m-%d') read_time, date_format(send_time, '%Y-%m-%d') send_time, message_text from user_private_message where send_time >= '2020-11-01' and send_time < '2020-12-01' and message_text LIKE 'A%' and datediff(read_time, send_time) <= 10;** - напишите запрос, который из таблицы user_private_message отберет записи: отправленные в ноябре 2020 года (поле send_time), текст сообщения начинается на 'A' (поле message_text), прочитанные не позже 10 дней от даты отправки (поле read_time)
## Задание 4
>**select count(approved_time) count, min(joined_time) oldest, max(approved_time) recent from users_to_discussion_groups;** - напишите запрос, который выберет из таблицы users_to_discession_groups: количество подтверждений присоединения к группам, наиболее ранюю дату присоединения пользователей к группе, дату наиболее позднего подтверждения участника в группе
## Задание 5
> **select user_id, registration_time from user order by 2 asc limit 20;** - SQL-запрос, который выбирает последних зарегистрированных пользователей. Поля в результате выборки: user_id, registration_time
## Задание 6
> **with groups_with_approve as (select * from discussion_group where approve_required = true), new_groups as (select * from groups_with_approve where year(creation_time) >= '2020') select * from new_groups;** - в запросе в секции with указаны два подзапроса: groups_with_approve - выбирает группы, в которых требуется подтверждение, new_groups - группы, созданные в 2020 году или позже, в которых требуется подтверждение, в основном запросе происзодит выборка всего из new_groups
## Задание 7
>**select user_from_id from user_private_message union select admin_user_id from discussion_group;** - SQL-запрос, который выбирает уникальные идентификаторы пользователей среди администраторов групп и отправителей приватных сообщений
## Задание 8
>*select date(send_time) message_date from user_private_message group by message_date having count(user_from_id) = 1*
## Задание 9
>
