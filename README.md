Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры. Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.

## Задача 1: Обеспечить разработку

Предложите решение для обеспечения процесса разработки: хранение исходного кода, непрерывная интеграция и непрерывная поставка. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:

    облачная система;
    система контроля версий Git;
    репозиторий на каждый сервис;
    запуск сборки по событию из системы контроля версий;
    запуск сборки по кнопке с указанием параметров;
    возможность привязать настройки к каждой сборке;
    возможность создания шаблонов для различных конфигураций сборок;
    возможность безопасного хранения секретных данных (пароли, ключи доступа);
    несколько конфигураций для сборки из одного репозитория;
    кастомные шаги при сборке;
    собственные докер-образы для сборки проектов;
    возможность развернуть агентов сборки на собственных серверах;
    возможность параллельного запуска нескольких сборок;
    возможность параллельного запуска тестов.

Обоснуйте свой выбор.

>Ответ: Для обеспечения процесса разработки, включающего хранение исходного кода, непрерывную интеграцию (CI) и непрерывную поставку (CD), можно использовать комбинацию облачных сервисов и инструментов. Основные компоненты решения:

    GitHub или GitLab:
        Система контроля версий: Обеспечивает хранение исходного кода с использованием Git. Позволяет создавать репозитории для каждого сервиса.
        Интеграция CI/CD: Поддерживает запуск сборок по событиям (например, коммит, пулл-реквест) и по кнопке с указанием параметров.
        Шаблоны и настройки: Позволяет создавать шаблоны для различных конфигураций сборок и привязывать настройки к каждой сборке.
        Безопасность: Поддерживает безопасное хранение секретных данных (пароли, ключи доступа) с помощью встроенных секретов.

    GitHub Actions или GitLab CI/CD:
        Кастомные шаги сборки: Позволяет определять кастомные шаги сборки с помощью YAML-файлов.
        Докер-образы: Поддерживает использование собственных докер-образов для сборки проектов.
        Параллельные сборки: Поддерживает параллельный запуск нескольких сборок и тестов.

    Собственные серверы для агентов сборки:
        Развертывание агентов: Возможность развернуть агенты сборки на собственных серверах для выполнения задач CI/CD. Это позволяет использовать вычислительные мощности вашей инфраструктуры.

    Конфигурации сборки:
        Множественные конфигурации: Поддержка нескольких конфигураций для сборки из одного репозитория, что позволяет тестировать и развертывать приложения в различных средах (например, dev, staging, production).

    Облачная система: 
        GitHub и GitLab предоставляют облачные решения, которые легко масштабируются и поддерживают интеграцию с другими облачными сервисами.
        Автоматизация: Использование CI/CD пайплайнов для автоматизации процессов сборки, тестирования и развертывания.
        Гибкость: Возможность настройки кастомных шагов сборки и использования собственных докер-образов позволяет адаптировать процесс под специфические требования проекта.
        Безопасность: Безопасное хранение секретных данных и управление доступом обеспечивают защиту конфиденциальной информации.

    Интеграция:
        GitHub и GitLab предоставляют мощные инструменты для интеграции и автоматизации процессов разработки.
        Гибкость и масштабируемость: Возможность настройки различных конфигураций и параллельного выполнения задач позволяет эффективно управлять ресурсами и временем.
        Сообщество и поддержка: Широкое сообщество пользователей и обширная документация облегчают внедрение и использование этих инструментов.


## Задача 2: Логи

Предложите решение для обеспечения сбора и анализа логов сервисов в микросервисной архитектуре. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:

    сбор логов в центральное хранилище со всех хостов, обслуживающих систему;
    минимальные требования к приложениям, сбор логов из stdout;
    гарантированная доставка логов до центрального хранилища;
    обеспечение поиска и фильтрации по записям логов;
    обеспечение пользовательского интерфейса с возможностью предоставления доступа разработчикам для поиска по записям логов;
    возможность дать ссылку на сохранённый поиск по записям логов.

Обоснуйте свой выбор.

>Ответ: Для обеспечения сбора и анализа логов в микросервисной архитектуре, можно использовать комбинацию инструментов, известных как стек ELK (Elasticsearch, Logstash, Kibana) или его альтернативы. Основные компоненты решения:

    Elasticsearch:
        Центральное хранилище логов: Обеспечивает индексацию и хранение логов, что позволяет быстро выполнять поиск и фильтрацию по записям.
        Масштабируемость: Поддерживает горизонтальное масштабирование для обработки больших объемов данных.

    Kibana:
        Пользовательский интерфейс: Предоставляет удобный интерфейс для поиска, визуализации и анализа логов.
        Доступ для разработчиков: Позволяет настраивать доступы и предоставлять разработчикам возможность выполнять поиск по записям логов.
        Сохраненные поиски: Поддерживает создание и сохранение поисковых запросов, а также предоставление ссылок на сохраненные поиски.

    Filebeat или Vector (альтернативы Logstash):
        Легковесные агенты: Устанавливаются на каждом хосте для сбора логов и отправки их напрямую в Elasticsearch.
        Минимальные нагрузки: Обеспечивают минимальные нагрузки на систему и поддерживают гарантированную доставку логов.
>ELK-стек хорошо интегрируется и масштабируется, что позволяет обрабатывать большие объемы логов в микросервисной архитектуре. Поддержка гарантированной доставки и минимальные требования к приложениям обеспечивают надежный сбор логов. Elasticsearch и Kibana предоставляют мощные инструменты для поиска, фильтрации и анализа логов, что упрощает диагностику и мониторинг. Широкое сообщество пользователей и обширная документация облегчают внедрение и использование этих инструментов.

## Задача 3: Мониторинг

Предложите решение для обеспечения сбора и анализа состояния хостов и сервисов в микросервисной архитектуре. Решение может состоять из одного или нескольких программных продуктов и должно описывать способы и принципы их взаимодействия.

Решение должно соответствовать следующим требованиям:

    сбор метрик со всех хостов, обслуживающих систему;
    сбор метрик состояния ресурсов хостов: CPU, RAM, HDD, Network;
    сбор метрик потребляемых ресурсов для каждого сервиса: CPU, RAM, HDD, Network;
    сбор метрик, специфичных для каждого сервиса;
    пользовательский интерфейс с возможностью делать запросы и агрегировать информацию;
    пользовательский интерфейс с возможностью настраивать различные панели для отслеживания состояния системы.

Обоснуйте свой выбор.

>Ответ: Для под вышеуказанные требования подходит связка Prometheus + Grafana. Основные компоненты решения:

    Prometheus:
        Сбор метрик: Собирает метрики со всех хостов и сервисов, используя экспортеры (exporters), которые устанавливаются на каждом хосте.
        Мониторинг ресурсов: Поддерживает сбор метрик состояния ресурсов хостов (CPU, RAM, HDD, Network) и потребляемых ресурсов для каждого сервиса.
        Специфичные метрики: Позволяет собирать метрики, специфичные для каждого сервиса, с помощью кастомных экспортеров.

    Grafana:
        Пользовательский интерфейс: Предоставляет удобный интерфейс для визуализации и анализа метрик.
        Запросы и агрегация: Позволяет делать запросы к данным и агрегировать информацию для анализа.
        Настраиваемые панели: Поддерживает создание и настройку различных панелей (dashboards) для отслеживания состояния системы.

    Кастомные экспортеры:
        Специфичные метрики: Разрабатываются для каждого сервиса для сбора метрик, специфичных для данного сервиса, и отправки их в Prometheus.

>Prometheus и Grafana хорошо интегрируются и масштабируются, что позволяет обрабатывать большие объемы метрик в микросервисной архитектуре. Поддержка кастомных экспортеров и настраиваемых панелей обеспечивает гибкость в сборе и анализе метрик. Grafana предоставляет мощные инструменты для визуализации и анализа метрик, что упрощает мониторинг и диагностику. Широкое сообщество пользователей и обширная документация облегчают внедрение и использование этих инструментов.

