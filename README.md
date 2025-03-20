## Гайд по подключению Code Coverage и Maintainability из qlty (old name: Codeclimate)

[![Maintainability](https://qlty.sh/badges/cb36b1d4-14dd-4c31-9f17-93dec816da2f/maintainability.svg)](https://qlty.sh/gh/camelCalm/projects/codeclimate)

[![Code Coverage](https://qlty.sh/badges/cb36b1d4-14dd-4c31-9f17-93dec816da2f/test_coverage.svg)](https://qlty.sh/gh/camelCalm/projects/codeclimate)

### 1. Создаем проект в github, во вкладке actions создаем Simple workflow

![get start actions](https://github.com/camelCalm/code-coverage/blob/main/img/getStartAct.png)

- В конец созданного файла /.github/workflows/<название файла>.yml добавляем и жмем Commit Changes:

```
      - name: Test & publish code coverage
        uses: qltysh/qlty-action/coverage@main
        with:
            coverage-token: ${{secrets.QLTY_COVERAGE_TOKEN}}
            files: target/lcov.info
```

Выглядит это так:

![add Test & publish code coverage](https://github.com/camelCalm/code-coverage/blob/main/img/addActions2.png)

### 2. После создания проекта необходимо установить и инициализировать следующие пакеты:
- eslint
- jest


### 3. Пройти регистрацию на сайте:

```
https://qlty.sh
```

Подробная инструкция по регистрации от разработчиков qlty:

```
https://docs.qlty.sh/cloud/quickstart
```

### 4. Далее необходимо добавить созданную директорию в Repositories

![add project](https://github.com/camelCalm/code-coverage/blob/main/img/addProject.png)

### 5. Войти в Projects 

![open project](https://github.com/camelCalm/code-coverage/blob/main/img/openProjects.png)

Потом -> Project Settings -> в строке Code Coverage скопировать Coverage Token.

![set project](https://github.com/camelCalm/code-coverage/blob/main/img/setProj.png)

### 6. Coverage Token необходимо сохранить в:

```
https://github.com/camelCalm/<название проекта>/settings/secrets/actions 
```

![add secret key](https://github.com/camelCalm/code-coverage/blob/main/img/addSecret.png)

Под именем: ```QLTY_COVERAGE_TOKEN```

Ура! Основные действия выполнены. Теперь ваш проект связан с вашим личным кабинетом на qlty.sh , и после того как вы сделаете тест на ваш код в проекте у вас автоматически (при пуше на гитхаб) будут подтягиваться результаты code-coverage в ваш README.md! Разве это не круто?