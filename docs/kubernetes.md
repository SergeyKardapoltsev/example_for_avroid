# Prometheus exporter for Nimble SRT

## Описание

Prometheus exporter for Nimble SRT предназначен для сбора метрик с серверов Nimble Streamer, использующих протокол SRT (Secure Reliable Transport). Эти метрики передаются в систему мониторинга Prometheus.

## Установка

Для развёртывания Prometheus exporter в Kubernetes используйте следующий YAML-манифест:

```yaml
- name: srt-exporter
  image: {{ $.Values.werf.image.exporter }}
  command:
  - /nimble_exporter
  - -auth_salt=590
  - -auth_hash=xxxx
  ports:
  - containerPort: 9017
    name: exporter
    protocol: TCP
  resources:
    {{ toYaml $.Values.resources.exporter | nindent 10 }}

```

## Использование

После развёртывания Prometheus exporter собирает метрики с серверов Nimble Streamer и передаёт их на порт 9017, откуда Prometheus может забирать данные для мониторинга.

## Метрики

Prometheus exporter предоставляет следующие метрики:

- битрейты потоков — позволяют отслеживать скорость передачи данных;
- статусы соединений — помогают контролировать стабильность подключений;
- частота ошибок — важна для выявления и устранения проблем в потоках SRT.