# Пример создания документации с применением docs as code

В примере использованы:

- Система контроля версий Git.
- Язык разметки Markdown.
- Генератор документации MkDocs – генерирует из MD-файлов HTML-версию сайта.
- Сервис GitHub – в качестве удалённого репозитория для хранения файлов проекта, в котором все изменения отслеживаются с помощью Git.
-  Сервис GitHub Actions – в качестве CI/CD для автоматической сборки и публикации документации.
- Aspell – для проверки орфографии документации на необходимом языке. Проверка будет выполняться в процессе сборки документации и деплоя на сайт. Можно настроить определённые правила проверки. Например, если в документации будут найдены слова, которые отсутствуют в словарях Aspell, то сборка завершится неудачей. Сайт в этом случае не обновится. В разделе Actions репозитория можно будет ознакомиться с описанием этой ошибки. Правила можно настроить таким образом, чтобы в описании ошибки были указаны слова, не прошедшие проверку.

На данном сайте для примера созданы три раздела (страницы):

- главная страница (эта) – Home;
- раздел [Kubernetes](kubernetes.md);
- раздел [About](about.md).

В разделе [Kubernetes](kubernetes.md) для примера описана инструкция по установке программы в среде Kubernetes.

Раздел [About](about.md) – ещё одна страница для примера структуры проекта с документацией.