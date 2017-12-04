# filebeat-generic

Filebeat container, alternative to fluentd used to ship kubernetes cluster and pod logs

## Getting Started
This container is designed to ship logs to Redis for further processing.
You can provide following environment variables to customize it.

```bash
REDIS_HOST=example.com:6379
LOG_LEVEL=info  # log level for filebeat. Defaults to "error".
```

Check out the `docker-compose.prod.yml` and see what folders need to be mounted so filebeat can tail the files and send the logs.

Filebeat parses docker json logs and applies multiline filter on the node before pushing logs to logstash.

Make sure you add a filter in your logstash configuration if you want to process the actual log lines.

## Licence

This project is licensed under the MIT License. Refer [LICENSE](https://github.com/devops-israel/filebeat-generic/blob/master/LICENSE) for details.
