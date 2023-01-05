# Домашнее задание к занятию "`8.2. Что такое DevOps. СI/СD`" - `Юндин Максим`


### Задание 1

1. `Я выполнял задание на локальной машине без использования Vagrant`


```
concurrent = 1
check_interval = 0
shutdown_timeout = 0

[session_server]
  session_timeout = 1800

[[runners]]
  name = "GitLab"
  url = "http://10.211.55.28/"
  id = 4
  token = "bSXiLMuRdtVKuDwiJzu_"
  token_obtained_at = 2023-01-05T17:18:49Z
  token_expires_at = 0001-01-01T00:00:00Z
  executor = "docker"
  [runners.custom_build_dir]
  [runners.cache]
    MaxUploadedArchiveSize = 0
    [runners.cache.s3]
    [runners.cache.gcs]
    [runners.cache.azure]
  [runners.docker]
    tls_verify = false
    image = "go:1.15.15"
    privileged = false
    disable_entrypoint_overwrite = false
    oom_kill_disable = false
    disable_cache = false
    volumes = ["/cache", "/var/run/docker.sock:/var/run/docker.sock"]

   # volumes = ["/cache"]
    shm_size = 0


```

![1 задание ](https://github.com/YundinMS/Screen/blob/main/runner.png)`

---

### Задание 2


2. `Что нужно сделать:`

`Запушьте репозиторий на GitLab, изменив origin. Это изучалось на занятии по Git.`
`Создайте .gitlab-ci.yml, описав в нём все необходимые, на ваш взгляд, этапы.`
`В качестве ответа в шаблон с решением добавьте:`

`файл gitlab-ci.yml для своего проекта или вставьте код в соответствующее поле в шаблоне;`
`скриншоты с успешно собранными сборками.`

```
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.15.15
  script: 
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
```

![2 задание ](https://github.com/YundinMS/Screen/blob/main/succsess.png)`
![2_2 задание ](https://github.com/YundinMS/Screen/blob/main/passed.png)`


