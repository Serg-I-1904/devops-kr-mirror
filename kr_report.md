# Отчёт по контрольной работе №1

Студент: Ивановский Сергей Станиславович  
Группа: ЭФБО-14-24

## Репозитории

Основной репозиторий:

```text
https://github.com/Serg-I-1904/devops-kr-template
```

Mirror-репозиторий:

```text
https://github.com/Serg-I-1904/devops-kr-mirror
```

Upstream-шаблон:

```text
https://gitverse.ru/dgimatdinov/devops-kr-template
```

## Pull Request

Смёрженный Pull Request:

```text
https://github.com/Serg-I-1904/devops-kr-template/pull/1
```

Title:

```text
feat: add phone validation
```

PR смёржен через `Squash and merge`.

## Что сделано

- Создана ветка `feature/add-phone-validation`.
- Добавлена функция `validate_phone`.
- Добавлены тесты для `validate_phone`.
- Создана "грязная" история из 4 коммитов.
- Выполнен `git rebase -i HEAD~4`: тесты и исправление опечатки приклеены через `fixup`, WIP-коммит `validate_inn` удалён через `drop`.
- Выполнен merge ветки `upstream/feature/instructor-change`.
- Разрешены конфликты в `validator.py` и `test/test_validator.py`.
- Сохранены обе функции: `validate_phone` и `validate_snils`.
- Feature-ветка отправлена в основной репозиторий и mirror.
- PR смёржен в `main`.
- `main` отправлен в оба remote.
- Ветка `feature/add-phone-validation` удалена в обоих remote и локально.

## Отчётные файлы

- `kr_log_dirty_history.txt` - грязная история до interactive rebase.
- `kr_log_clean_history.txt` - чистая история после interactive rebase.
- `kr_validator_after_rebase.txt` - `validator.py` после rebase.
- `kr_validator_conflict_before.py` - конфликт в `validator.py` до разрешения.
- `kr_test_conflict_before.py` - конфликт в `test/test_validator.py` до разрешения.
- `kr_validator_final.py` - финальный `validator.py`.
- `kr_validate_functions.txt` - список функций `validate_*`.

## Проверка

`pytest` в системном Python не установлен, поэтому была выполнена ручная Python-проверка импортом функций:

```text
manual validation checks passed
```

Проверялись:

- `validate_email`;
- `validate_phone`;
- `validate_snils`.

## Примечание по тесту СНИЛС

В конфликтующей ветке был пример `001-001-999 32`, который не проходит алгоритм контрольной суммы. После проверки он заменён на корректный валидный пример:

```text
001-001-999 65
```
