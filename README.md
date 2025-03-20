[![Maintainability](https://qlty.sh/badges/cb36b1d4-14dd-4c31-9f17-93dec816da2f/maintainability.svg)](https://qlty.sh/gh/camelCalm/projects/codeclimate)

[![Code Coverage](https://qlty.sh/badges/cb36b1d4-14dd-4c31-9f17-93dec816da2f/test_coverage.svg)](https://qlty.sh/gh/camelCalm/projects/codeclimate)

1. При создании проекта необходимо установить следующие пакеты:

```"@eslint/js"```
```eslint```
```eslint-plugin-jest```
```globals```
```jest```

2. Пройти регистрацию на сайте 

```https://qlty.sh```

подробная инструкция:

```https://docs.qlty.sh/cloud/quickstart```

3. Далее необходимо добавить созданную директорию в Repositories, войти в Projects -> Project Settings -> в строке Code Coverage скопировать Coverage Token.

![add project](https://github.com/camelCalm/code-coverage/blob/main/img/addProject.png)

4. Coverage Token необходимо сохранить в 

``
https://github.com/camelCalm/<название проекта>/settings/secrets/actions 
``

под именем: ```CC_TEST_REPORTER_ID```