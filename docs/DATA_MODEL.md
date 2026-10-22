# Модель данных: AS IS vs. TO BE

**AS IS:** один массив JS-объектов `initialApps` в `index.html`. Тестовая копия — `examples/synthetic_applications.json`. Все изменения состояния в оперативной памяти открытой страницы.

**TO BE:**

| Сущность | Минимальные поля |
|---|---|
| `User` | id, role, username |
| `Company` | id, name, inn, sector, age_months |
| `Application` | id, company_id, product, amount, term, status, version |
| `ScoreRun` | id, application_id, score, reasons, rule_version |
| `DocumentRequest` | id, application_id, type, status |
| `Document` | id, request_id, name, storage_key, uploaded_at |
| `AlternativeOffer` | id, application_id, amount, term, reason |
| `StatusHistory` | id, application_id, actor_id, old_status, new_status, action, timestamp |

Ни одна из проектных таблиц в этом архиве не создана. Схема в `diagrams/data_model.png` — **проект**, не снимок действующей БД.
