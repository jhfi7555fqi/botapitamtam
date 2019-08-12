# tamtamapi_lite
Попытка создать набор простых инструментов для написания ботов на базе API мессенджера TamTam. Набор содержит базовый функционал взаимодействия бота с пользователями и предназначен для начинающих программистов.

Принцип взаимодействия с библиотекой:
- 
1. Методы, которые начинаются с get_ получают события, произошедшие с ботом (написанные или пересланные сообщения, результат нажатия кнопок, вложения и т.д.).
2. Методы, которые начинаются с send_ формируют события в боте (отправляют сообщения, генерируют кнопки и т.д.).
3. В основном цикле Вашей программы осуществляем запрос (long polling), происходящих с ботом событий, методом get_updates. Результат помещаем в переменную (например updates).
4. Для получения "тела" события, которое необходимо обработать, передаем переменную updates выбранному методу get_ (например get_text), работаем с результатом. 
5. Если запрошенное событие не произошло в ответ получим None.

Описание методов...
