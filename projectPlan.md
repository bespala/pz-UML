# UML Project

## Посилання на діаграми

- [Use Case Diagram](#use-case-diagram)
- [Sequence Diagram](#sequence-diagram)
- [Activity Diagram](#activity-diagram)


## Use Case Diagram

```mermaid
flowchart LR

    User[Користувач]
    Admin[Адміністратор]

    subgraph System["Система бронювання переговорної кімнати"]
        UC1((Переглянути доступні кімнати))
        UC2((Створити бронювання))
        UC3((Скасувати бронювання))
        UC4((Отримати підтвердження))
        UC5((Керувати кімнатами))
        UC6((Переглядати всі бронювання))
    end

    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4

    Admin --> UC5
    Admin --> UC6
```
Діаграма варіантів використання показує, які дії можуть виконувати основні актори системи.
Користувач може переглядати кімнати, створювати або скасовувати бронювання.
Адміністратор має додаткові можливості: керування кімнатами та перегляд усіх бронювань.



## Sequence Diagram
```mermaid
sequenceDiagram
actor User as Користувач
participant UI as Веб-інтерфейс
participant System as Система бронювання
participant DB as База даних

User->>UI: Обирає дату і час
UI->>System: Запит доступних кімнат
System->>DB: Перевірка доступності
DB-->>System: Список вільних кімнат
System-->>UI: Повертає доступні кімнати
UI-->>User: Показує список кімнат

User->>UI: Обирає кімнату
UI->>System: Створити бронювання
System->>DB: Зберегти бронювання
DB-->>System: Бронювання збережено
System-->>UI: Підтвердження бронювання
UI-->>User: Показує повідомлення про успіх
```


