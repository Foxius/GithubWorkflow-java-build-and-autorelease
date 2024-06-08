# GithubWorkflow-java-build-and-autorelease

Данный файл нужен для автоматического билда и создания релиза кода на языке java

## Алгоритм работы

**Прежде чем начать убедитесь что у вас соотвествуют все пункты**

1) Сборщик gradle (не maven)
2) У вас присутствуют файлы: `gradlew`, `gradlew.bat`, `gradle.properties`, `build.gradle`, `gradle/wrapper/gradle-wrapper.jar`, `gradle/wrapper/gradle-wrapper.properties` (обычно появляются при первом билде)



**Затем создайте ключ (PAT):**

- Перейдите на страницу настроек токенов вашего аккаунта GitHub.
- Нажмите "Generate new token".
- Выберите права repo (и любые другие, если необходимо).
- Скопируйте созданный токен.

**После этого добавьте PAT в секреты репозитория:**

- Перейдите на страницу вашего репозитория на GitHub.
- Перейдите в "Settings" -> "Secrets and variables" -> "Actions".
- Нажмите "New repository secret".
- Назовите секрет PAT и вставьте скопированный токен в поле "Value".
- Нажмите "Add secret".


После этого в папку `.github/workflows` поместите файл [gradle.yml](https://github.com/Foxius/GithubWorkflow-java-build-and-autorelease/blob/main/gradle.yml)

Затем закомитьте его и запушьте 
```
git add .github/workflows/gradle.yml
git commit -m "Add Workflow"

git push origin main
```

После этого присвойте тег для коммита. например:
```
git tag v1.0.1
git push origin v1.0.1
```

Затем всё сбилдится автоматически и попадёт в release
