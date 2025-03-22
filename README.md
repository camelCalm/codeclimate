## Гайд по подключению Code Coverage и Maintainability из qlty (прежнее название: Codeclimate)

[![Maintainability](https://qlty.sh/badges/efd1ecb1-98ac-4153-8df7-8b21567664fb/maintainability.svg)](https://qlty.sh/gh/camelCalm/projects/code-coverage)

[![Code Coverage](https://qlty.sh/badges/efd1ecb1-98ac-4153-8df7-8b21567664fb/test_coverage.svg)](https://qlty.sh/gh/camelCalm/projects/code-coverage)

### 1. Создание проекта в GitHub.

1.1. Создаем проект в GitHub, во вкладке actions создаем Simple workflow.

![get start actions](https://github.com/camelCalm/code-coverage/blob/main/img/getStartAct.png)

1.2. В конец созданного файла /.github/workflows/<название файла>.yml добавляем следующий код:

```
      - name: Test & publish code coverage
        uses: qltysh/qlty-action/coverage@main
        with:
            coverage-token: ${{secrets.QLTY_COVERAGE_TOKEN}}
            files: target/lcov.info
```

1.3. Жмем Commit Changes:

![add Test & publish code coverage](https://github.com/camelCalm/code-coverage/blob/main/img/addActions2.png)

### 2. Установка пакета в проект.

После создания проекта необходимо установить и инициализировать следующий пакет:

- jest

### 3. Регистрация на сайте qlty.

Прежнее навзание - codeclimate, теперь разработан новый сайт от разработчиков codeclimate:

```
https://qlty.sh
```

Подробная инструкция по регистрации от разработчиков qlty:

```
https://docs.qlty.sh/cloud/quickstart
```

### 4. Добавление созданной директории.

Далее необходимо добавить созданную директорию в Repositories, который находится в вашем личном кабинете qlty.

![add project](https://github.com/camelCalm/code-coverage/blob/main/img/addProject.png)

### 5. Получение Coverage Token.

Нам необходимо получить токен, который будет хранится в настройках созданного репозитория на гитхаб.  
Он нужен нам для того чтобы qlty мог соединиться с нашим проектом. 

- Заходим в Projects

![open project](https://github.com/camelCalm/code-coverage/blob/main/img/openProjects.png)

- Далее заходим в Project Settings, и в строке Code Coverage жмем скопировать Coverage Token.

![set project](https://github.com/camelCalm/code-coverage/blob/main/img/setProj.png)

### 6. Сохранение Coverage Token.

Токен необходимо сохранить в:

```
https://github.com/camelCalm/<название проекта>/settings/secrets/actions 
```

![add secret key](https://github.com/camelCalm/code-coverage/blob/main/img/addSecret.png)

Под именем: ```QLTY_COVERAGE_TOKEN```

### Usage

И так, когда вы напишите свой код, и сделаете тесты на него, вам необходимо проверить, работает ли test-coverage.  
Проверка происходит с помощью данной команды, которую необходимо ввести в терминал:

```
npm test -- --coverage --coverageProvider=v8
```

После ввода данной команды, должна создаться папка "coverage" в вашем проекте. Исправьте код, если тесты не проходят.  
"coverage/lcov.info" содержит код, который высылается в qlty, и, собственно говоря, благодаря этому делаются результаты test-coverage.

Также обратите внимание на файл .npmrc . Это "настройки" конфигурации npm. Добавьте его в свой проект.

### Заключение.

Основные действия выполнены. Теперь ваш проект связан с вашим личным кабинетом на qlty.sh, и после того как вы сделаете тест на ваш код, при пуше на гитхаб будут подтягиваться результаты Code Coverage и Maintainability в ваш README.md  
Настройка окружения, и все остальные файлы, которые необходимы для нормальной работы, есть в этом проекте.