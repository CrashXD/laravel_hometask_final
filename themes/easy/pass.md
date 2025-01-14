[Назад к списку](/README.md)

# Генератор паролей

Сайт "Генератор паролей" предоставляет пользователям возможность создавать надежные пароли с определенными критериями безопасности. Пользователи могут выбрать длину пароля и указать, какие символы должны включаться в пароль (буквы верхнего и нижнего регистра, цифры, специальные символы). Генератор паролей затем создает случайный пароль, учитывая указанные пользователем параметры.

## Модель "Password" с полями:

- id: уникальный идентификатор генерации пароля (целочисленное поле, автоинкрементное).
- password_length: длина сгенерированного пароля (целочисленное поле).
- include_uppercase: флаг, указывающий на включение символов в верхнем регистре (логическое поле).
- include_lowercase: флаг, указывающий на включение символов в нижнем регистре (логическое поле).
- include_digits: флаг, указывающий на включение цифр (логическое поле).
- include_special_characters: флаг, указывающий на включение специальных символов (логическое поле).
- generated_password: сгенерированный пароль (текстовое поле).
- created_at: дата и время создания записи (тип "timestamp").
- updated_at: дата и время обновления записи (тип "timestamp").

## Роутеры:

- GET /password/history - Показать историю всех сгенерированных паролей пользователя.
- POST /password/generate - Генерировать новый пароль на основе указанных пользователем параметров и сохранить его в истории.
- PUT /password/{id}/regenerate - Перегенерировать пароль с указанным идентификатором и обновить его в истории.
- DELETE /password/{id} - Удалить сгенерированный пароль с указанным идентификатором из истории.

## Контроллеры с методами:

- PasswordController@index - Метод для получения списка всех сгенерированных паролей пользователя из истории.
- PasswordController@store - Метод для генерации нового пароля на основе указанных пользователем параметров и сохранения его в истории.
- PasswordController@regenerate - Метод для перегенерации пароля с указанным идентификатором и обновления его в истории.
- PasswordController@destroy - Метод для удаления сгенерированного пароля с указанным идентификатором из истории.
