# Микросервис user-service
Микросервис для работы с пользователями.

Модель User включает следующие поля: name, email, password, aboutMe.

Данный микросервис позволяет создавать пользователей, обновлять информацию о них (кроме email), получить пользователя по id (если пользователь запрашивает сам себя, он также сможет получить свой пароль), получить список всех пользователей (без паролей), а также удалить пользователя по id.

Микросервис написан на Java 21 и Spring Boot 3.

## Микросервис разрабатывали:
• [Владимир Баханович] (https://github.com/vvbakhanovich);

• [Виктор Вагнер] (https://github.com/Vagner-Viktor);

• [Карен Петросян] (https://github.com/kapetrosyan1);

• [Галина Лобачёва] (https://github.com/KoshanSky1).

## Технологический стек:
![](https://camo.githubusercontent.com/270dd3f671d1645fc7af25d667bb2edc3a56937650e211fd438d01d45a0c4ef4/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a6176612d2532334646373830303f7374796c653d706c6173746963)
![](https://camo.githubusercontent.com/db3b2642cd8eb16b1ca5f24ee9b3a3749072a1315f8c0a5c32fbd18301825d1a/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f537072696e67253230426f6f742d2532333644423333463f7374796c653d706c6173746963266c6f676f3d737072696e67626f6f74266c6f676f436f6c6f723d626c61636b)
![](https://camo.githubusercontent.com/7a983da2ce01a3efa8493a9212c5b2dcfe4f091bb83d527d76592225a3b8604e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f537072696e67253230446174612532304a50412d2532333644423333463f7374796c653d706c6173746963266c6f676f3d737072696e67266c6f676f436f6c6f723d626c61636b)
![](https://camo.githubusercontent.com/c03689c12a055b6b7d1e7b29e9455d4f7533b0050c53cb88a967b7ee5390fb63/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f506f737467726553514c2d2532333431363945313f7374796c653d706c6173746963266c6f676f3d706f737467726573716c266c6f676f436f6c6f723d7768697465)
![](https://camo.githubusercontent.com/27176401988b92033156421dbc03988584a6910a755c314135228ec9dd484158/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c69717569626173652d2532333239363246463f7374796c653d706c6173746963266c6f676f3d6c6971756962617365266c6f676f436f6c6f723d7768697465)
![](https://camo.githubusercontent.com/bdc010975aa753cd19c55c6b71afd77e53258c1616a204e8d58a4c13a2ee8e2e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f636b65722d2532333234393645443f7374796c653d706c6173746963266c6f676f3d646f636b6572266c6f676f436f6c6f723d7768697465)
![](https://camo.githubusercontent.com/5d5f74998aafb5e0e4366935c979556cac9096beb36a494524207e3155f6797f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f54657374253230436f6e7461696e6572732d2532333234393645443f7374796c653d706c6173746963266c6f676f3d646f636b6572266c6f676f436f6c6f723d7768697465)
![](https://camo.githubusercontent.com/255e8556350f0eb358f25432a5bac66d65a774d915c1d72df9ea2f96d408ede7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4170616368652532304d6176656e2d2532334337314133363f7374796c653d706c6173746963266c6f676f3d6170616368656d6176656e)
![](https://camo.githubusercontent.com/e80cdb9c35506cae826136848fe6463807e0052cbfd07b00df3643c50f95b475/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4769742d2532334630353033323f7374796c653d706c6173746963266c6f676f3d676974266c6f676f436f6c6f723d7768697465)
![](https://camo.githubusercontent.com/31aea4798a4079be6bffe5ca9b264e2764adf3d992ff35f0240211c221cbbe8d/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f537761676765722d2532333835454132443f7374796c653d706c6173746963266c6f676f3d73776167676572266c6f676f436f6c6f723d7768697465)
![](https://camo.githubusercontent.com/709af8eea5ce7135de90589399f9a208dd532c4858bf1cb2a2aefcec2e15c63e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a556e69742d2532333235413136323f7374796c653d706c6173746963266c6f676f3d6a756e697435266c6f676f436f6c6f723d7768697465)

## Эндпоинты:
• POST /users - создание пользователя;

• PATCH /users - обновление пользователя;

• GET /users/{id} - получение пользователя по id;

• GET /users?page={page}&size={size} - получение списка всех пользователей с пагинацией;

• DELETE /users - удаление пользователя по id.

## Запустить микросервис можно двумя способами.
### Первый способ:
•	Предварительно создать БД POSTGRES не ниже версии 15 с именем "mus".

•	Установить и запустить Docker. Необходимо для выполнения тестов с использованием test-containers.

•	Собрать jar файл при помощи maven командой mvn clean install.

•	Запустить микросервис командой java -jar user-service.jar.

•	Микросервис будет доступен по адресу http://localhost:8080.

### Второй способ:
•	Установить и запустить Docker.

•	Запустить контейнер командой docker compose up.

•	Микросервис будет доступен по адресу http://localhost:8080.

### После запуска микросервиса API документация будет доступна по ссылке:

http://localhost:8080/swagger-ui/index.html
