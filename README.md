# Monitoring Service

## Grafana

1. Запустите сервисы:

```bash
docker compose up -d
```

2. Откройте Grafana и перейдите в Dashboards:
    - "01 Infrastructure"
    - "02 Application Overview"
    - "03 Business KPI"
3. Логин: admin / admin.

### Настройка окна агрегации

Во всех дашбордах есть переменная `$window` (по умолчанию 5m). Меняйте ее в верхней панели Grafana, чтобы влиять на окно `rate()` и `histogram_quantile()`.

### Особенности Overview

Дашборд "02 Application Overview" специально фильтрует шумовые SPA-запросы (например `/metrics`, `OPTIONS`, `/users/me`, `/auth/validate` и WebSocket HTTP paths), чтобы показать только важные действия.