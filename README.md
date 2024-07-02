# mrsp
## Шаг 1: Подключение к VK ЦРТ по протоколу MRCP
- Настройка доступа к VK ЦРТ: Получите от VK ЦРТ доступ к API и учетные данные (логин, пароль, адрес сервера MRCP).

- Установка специализированного ПО: Необходимо установить MRCP клиентский софт, например, Asterisk с MRCP плагином или другой софт, поддерживающий MRCP протокол.

- Конфигурация соединения: Настройте параметры подключения к серверу VK ЦРТ: IP-адрес сервера MRCP, порт, аутентификационные данные.

- Тестирование подключения: Убедитесь, что соединение с VK ЦРТ через MRCP настроено правильно путем отправки тестового запроса.

## Шаг 2: Описание команд передачи диалогового фрагмента на распознавание речи
- Отправка аудиофайла: Подготовьте аудиофайл с диалоговым фрагментом (форматы: WAV, MP3, etc.).

- Формирование MRCP команды: Создайте MRCP команду для передачи аудиофайла на распознавание, включив в неё метаданные (например, язык, формат аудио).
  к приммеру:
  RECOGNIZE
  Channel-Id: 1234
  Content-Type: audio/mp3
  Audio-File: /path/to/1.mp3
  
  где:
  RECOGNIZE указывает, что мы запрашиваем распознавание речи.
  Channel-Id: 1234 это идентификатор канала, который можно использовать для идентификации обработки запроса.
  Content-Type: audio/mp3 указывает на тип контента, который отправляется (в данном случае, аудио в формате MP3).
  Audio-File: /path/to/1.mp3 путь к аудиофайлу, который вы отправляете на распознавание.

- Отправка команды: Отправьте сформированную MRCP команду на сервер VK ЦРТ через установленное соединение.
 telnet your_mrcp_server_ip your_mrcp_server_port

- Ожидание результата: Дождитесь ответа от сервера, содержащего распознанный текст или другую информацию о результате обработки.

- Обработка результата: Проанализируй полученный результат, обработай его по необходимости и передайте дальше в ваше приложение.
