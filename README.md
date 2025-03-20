[![Maintainability](https://qlty.sh/badges/cb36b1d4-14dd-4c31-9f17-93dec816da2f/maintainability.svg)](https://qlty.sh/gh/camelCalm/projects/codeclimate)

[![Code Coverage](https://qlty.sh/badges/cb36b1d4-14dd-4c31-9f17-93dec816da2f/test_coverage.svg)](https://qlty.sh/gh/camelCalm/projects/codeclimate)

1. При создании проекта необходимо установить следующие пакеты:

``
    "@eslint/js"
    "eslint"
    "eslint-plugin-jest"
    "globals"
    "jest"
``
2. Пройти регистрацию на сайте https://qlty.sh, добавить созданную директорию в Repositories,
войти в Repo Settings, в строке Test coverage скопировать Test reporter ID.
3. Test reporter ID необходимо сохранить в 
``
https://github.com/camelCalm/<название проекта>/settings/secrets/actions 
``
под именем: CC_TEST_REPORTER_ID
4. 