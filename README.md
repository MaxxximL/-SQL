# -SQL Схема базы данных:

Схема базы данных представляет собой набор таблиц для хранения пользователей, фильмов, жанров и связей между ними. 
Основные таблицы: Users, Films, Genres, Film_Genres, Friendships

## Примеры запросов

1. Получение всех фильмов:

SELECT * FROM Film;

2. Топ N наиболее популярных фильмов:

SELECT * FROM Film ORDER BY rating DESC LIMIT N;

3. Список общих друзей с другим пользователем:

SELECT U2.username 
FROM Friendship F
JOIN User U1 ON F.user_id_1 = U1.id OR F.user_id_2 = U1.id
JOIN User U2 ON (F.user_id_1 = U2.id OR F.user_id_2 = U2.id) AND U1.id != U2.id
WHERE U1.id = ? AND F.status = 'confirmed';



