# API-контракт кабинета сотрудника (DRAFT — НЕ РЕАЛИЗОВАН)

Назначение: согласовать интеграцию отдельного сайта сотрудника с backend команды. Опубликованный `index.html` **не обращается** к этим endpoint'ам.

| Метод | Маршрут | Назначение |
|---|---|---|
| GET | `/api/v1/staff/applications` | Очередь, фильтры |
| GET | `/api/v1/staff/applications/{id}` | Карточка заявки |
| GET | `/api/v1/staff/applications/{id}/score` | Скоринг и причины |
| GET | `/api/v1/staff/applications/{id}/documents` | Запросы и загруженные файлы |
| GET | `/api/v1/staff/applications/{id}/history` | Аудит |
| POST | `/api/v1/staff/applications/{id}/decision` | `approve`, `reject`, `request_documents` |
| POST | `/api/v1/staff/applications/{id}/alternative-offer` | Новые сумма и срок |

На сервере должны проверяться роль `staff`, принадлежность доступа, версия заявки и допустимость перехода. Запросы с несовпадающей версией и запрещённые переходы → HTTP 409; нет доступа → 401/403. Все операции меняют одну и ту же заявку, видимую клиенту.

`openapi-draft.yaml` содержит **проектные** запросы и ответы, а `staff-api-draft.postman_collection.json` — примерную коллекцию. Они не подтверждают существование backend.
