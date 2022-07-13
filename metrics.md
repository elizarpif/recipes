## Grafana tips
```
histogram | response_time_seconds{handler, protocol, client_name, status="ok|error|client_error|not_found|canceled|degraded"}
response_time_seconds{handler="hello_world", protocol="http", client_name="browser", status="ok"}
summary   | response_time_summary_seconds{}
counter   | requests_total{handler, protocol, client_name}
summary   | request_size_bytes{handler, protocol, client_name}
summary   | request_read_time_seconds{handler, protocol, client_name}
summary   | request_unmarshal_time_seconds{handler, protocol, client_name}
summary   | request_read_unmarshal_time_seconds{handler, protocol, client_name}
summary   | response_size_bytes{handler, protocol, client_name, status="ok|error|client_error|not_found|canceled|degraded"}
summary   | response_marshal_time_seconds{handler, protocol, client_name, status="ok|error|client_error|not_found|canceled|degraded"}

histogram | external_service_response_time_seconds{external_service, method, status="ok|error|client_error|timeout"}
histogram | external_service_response_unmarshal_time_seconds{external_service, method, status="ok|error|client_error|timeout"}

histogram | psql_query_duration_seconds{host, db, is_error="0|1", query, handler}
gauge     | psql_connections_total{host="psql.host.com", db="db_name"}
```

Полезно:
- цпу постгрес
- чтение топиков кафка
- кол-во транзакций
- еррор рейт на хендлеры
- респонс тайм
- отметки при кэнэри деплое
