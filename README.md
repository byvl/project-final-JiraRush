## [REST API](http://localhost:8080/doc)

## Концепция:

- Spring Modulith
    - [Spring Modulith: достигли ли мы зрелости модульности](https://habr.com/ru/post/701984/)
    - [Introducing Spring Modulith](https://spring.io/blog/2022/10/21/introducing-spring-modulith)
    - [Spring Modulith - Reference documentation](https://docs.spring.io/spring-modulith/docs/current-SNAPSHOT/reference/html/)

```
  url: jdbc:postgresql://localhost:5432/jira
  username: jira
  password: JiraRush
```

- Есть 2 общие таблицы, на которых не fk
    - _Reference_ - справочник. Связь делаем по _code_ (по id нельзя, тк id привязано к окружению-конкретной базе)
    - _UserBelong_ - привязка юзеров с типом (owner, lead, ...) к объекту (таска, проект, спринт, ...). FK вручную будем
      проверять

## Аналоги

- https://java-source.net/open-source/issue-trackers

## Тестирование

- https://habr.com/ru/articles/259055/

Список выполненных задач:
1) Разобраться со структурой проекта (onboarding).
2) Удалить социальные сети: vk, yandex.
3) Вынести чувствительную информацию в отдельный проперти файл:
   логин
   пароль БД
   идентификаторы для OAuth регистрации/авторизации
   настройки почты
5) Написать тесты для всех публичных методов контроллера ProfileRestController.
6) Сделать рефакторинг метода com.javarush.jira.bugtracking.attachment.FileUtil#upload
7) Добавить новый функционал: добавления тегов к задаче (REST API + реализация на сервисе).
   Фронт делать необязательно.
8) Добавить подсчет времени сколько задача находилась в работе и тестировании. 
   Написать 2 метода на уровне сервиса, 
   которые параметром принимают задачу и возвращают затраченное время:
      Сколько задача находилась в работе (ready_for_review минус in_progress ).
      Сколько задача находилась на тестировании (done минус ready_for_review).