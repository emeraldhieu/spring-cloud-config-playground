# Spring Cloud Config Playground

## Quickstart

### 1) Start apps 

+ Start `ConfigServerApp`
+ Start `ConfigClientApp`

### 2) Play

cURLS to test:
  
#### Server

```shell
curl http://root:s3cr3t@localhost:8888/awesome-app/dev
``` 

Response
```json
{
    "name": "awesome-app",
    "profiles":
    [
        "dev"
    ],
    "label": null,
    "version": "1800e973261f81014addcf9a9df40cb2af28d023",
    "state": null,
    "propertySources":
    [
        {
            "name": "https://github.com/emeraldhieu/spring-cloud-config-playground.git/config/awesome-app/application-dev.yml",
            "source":
            {
                "user.role": "Developer",
                "user.password": "this-is-my-secret"
            }
        }
    ]
}
```

```shell
curl http://root:s3cr3t@localhost:8888/awesome-app-dev.yml
```

Response
```yaml
user:
  role: Developer
  password: this-is-my-secret
```

#### Client

```shell
curl http://localhost:8080/whoami/John
```

Response
```
Hello! You're John and you'll become a(n) Developer, but only if your password is 'this-is-my-secret'!
```

## References

https://docs.spring.io/spring-cloud-config/docs/current/reference/html