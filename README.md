Вы работаете в крупной компании, которая строит систему на основе микросервисной архитектуры. Вам как DevOps-специалисту необходимо выдвинуть предложение по организации инфраструктуры для разработки и эксплуатации.

## Задача 1: API Gateway

Предложите решение для обеспечения реализации API Gateway. Составьте сравнительную таблицу возможностей различных программных решений. На основе таблицы сделайте выбор решения.

Решение должно соответствовать следующим требованиям:

    маршрутизация запросов к нужному сервису на основе конфигурации,
    возможность проверки аутентификационной информации в запросах,
    обеспечение терминации HTTPS.

Обоснуйте свой выбор.

| Наименование API Gateway	| маршрутизация запросов к нужному сервису на основе конфигурации |	возможность проверки аутентификационной информации в запросах |	обеспечение терминации HTTPS |
|-|-|-|-|
|Azure API Management|+|+|+|
|Amazon API Gateway|+|+|+|
|Yandex API Gateway|+|+|+|
|KrakenD|+|+|+|
|NGINX API Gateway|+|+|+|

>Ответ: предложу KrakenD из-за его высокой скорости работы, возможности трансляции протоколов и способности работы с множеством протоколов.

## Задача 2: Брокер сообщений

Составьте таблицу возможностей различных брокеров сообщений. На основе таблицы сделайте обоснованный выбор решения.

Решение должно соответствовать следующим требованиям:

    поддержка кластеризации для обеспечения надёжности,
    хранение сообщений на диске в процессе доставки,
    высокая скорость работы,
    поддержка различных форматов сообщений,
    разделение прав доступа к различным потокам сообщений,
    простота эксплуатации.

Обоснуйте свой выбор.

|Наименование|поддержка кластеризации для обеспечения надёжности|хранение сообщений на диске в процессе доставки|высокая скорость работы|поддержка различных форматов сообщений|разделение прав доступа к различным потокам сообщений|простота эксплуатации|
|-|-|-|-|-|-|-|
|Apache Kafka|Да (репликация, ISR)|Да (основной механизм)|Высокая (оптимизирован для throughput)|JSON, Avro, ProtoBuf|Да (ACL, SASL, RBAC)|Сложная|
|RabbitMQ|Да (HA, quorum queues)|Да|Средняя|JSON, XML, AMQP, MQTT|Да (ACL, vhost)|Средняя|
|NATS JetStream|Да (JetStream Clustering)|Да|Высокая (низкая задержка)|JSON, ProtoBuf|Да (account-based security)|Простая|
|ActiveMQ|Да|Да|Средняя|JSON, XML|Да|Средняя|
|Redis Streams|Да (Sentinel, Redis Cluster)|Да|Очень высокая (но без сложной маршрутизации)|JSON, MsgPack, бинарные|Ограниченная (ACL в Redis)|Очень простая (но ограниченные возможности)|

>Ответ: лучшим выбором в большинстве случаев будет RabbitMQ или NATS JetStream, так как они обеспечивают баланс между производительностью, надёжностью и простотой эксплуатации.При этом если важна мощная маршрутизация и гарантированная доставка сообщений то RabbitMQ, а если нужна высокая скорость, лёгкость в развертывании и горизонтальная масштабируемость то NATS JetStream
