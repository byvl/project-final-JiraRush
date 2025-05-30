Список выполненных задач:

1) Ознакомился со структурой проекта.
   Ознакомился с Spring Modulith, Swagger, Caffeine,
   подняты 2 базы в докере, создана БД Jira,
   запущен скрипт в консоли с тестовыми данными из data4dev/data.sql,
   была изучена структура бд по Show Diagram,
   запущен проект с профилем prod,
   ознакомился с API через Swagger,
   были успешно выполнены все тесты.
2) Убраны кнопки для VK и Yandex в resources/view/login.html и resources/view/unauth/register.html,
   удалалены два класса из src/main/java/com/javarush/jira/login/internal/sociallogin/handler,
   связанные с vk и yandex,
   в application.yaml удалены данные для аутентификации через vk и yandex,
   заново успешно были выполнены все тесты.
3) Перенесена чувствительная информация из application.yaml в app-secret.properties,
   импортировал app-secret.properties в application.yaml,
   заново успешно были выполнены все тесты.
5) Написаны тесты для всех публичных методов контроллера ProfileRestController
6) Сделан рефакторинг метода upload в com.javarush.jira.bugtracking.attachment.FileUtil
   с использованием Path и Files из Java NIO,
   заново успешно были выполнены все тесты.
7) Для возможности добавления тегов к задачам через REST API
   написан TaskTagController c get post delete,
   в TaskService добавлены getTags addTag removeTag, More actions,
   в src/main/java/com/javarush/jira/common/error добавлен AlreadyExistsException,
   в src/main/java/com/javarush/jira/bugtracking/task/Task.java для свойства tags
   сделано @ElementCollection(fetch = FetchType.EAGER,
   результат можно проверить через Swagger /{id}/add-tags и /{id}/remove-tags.
8) Для подсчета времени сколько задача находилась в работе и тестировании
   в src/main/java/com/javarush/jira/bugtracking/task/TaskController.java
   добавлены два эндпоинта в TaskController -
   "/{taskId}/work-time" и "/{taskId}/testing-time",
   в src/main/java/com/javarush/jira/bugtracking/task/TaskService.java
   реализовано вычисление времени при помощи методов
   public Duration calculateInProgressTime(Long taskId) 
   и public Duration calculateInTestingTime(Long taskId).