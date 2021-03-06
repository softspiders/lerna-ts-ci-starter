<div align="center">
    <a href="https://github.com/softspiders/softspiders">
      <img src="./images/sslogo-from-github-20.png"/>
    </a>
</div>

# lerna-ts-ci-starter

The repository provides an example of CI settings for building and publishing lerna monorepositories to NPM based on
*Github Actions*.

## Feature tags

- github-actions
- git-flow
- lerna
- publishing
- releasing
- starter
- template
- typescript

## Parents

- [- ***git-flow***, ***lerna***, ***publishing***, ***releasing***, ***typescript***: js-github-actions](https://github.com/softspiders/js-github-actions)

---

## Author

[AlexanderLapygin](https://github.com/AlexanderLapygin)

---

## Inspiration

[AlexSav94](https://github.com/AlexSav94)

---

## Requirements

[Node.js](https://nodejs.org/en/download/package-manager/)

---

## Running

```sh
TBD
```
---

## Использованные технологии

### Git Flow

Схема работы с репозиторием основана на классическом варианте Git Flow.
![Git Flow](https://www.campingcoder.com/post/20180412-git-flow.png)

**Последовательность работы при использовании модели Gitflow:**

1. Из master создается ветка develop.
2. Из develop создаются ветки dev_*.
3. Когда разработка новой функциональности завершена, она объединяется с веткой develop.
4. Из develop создается ветка release/*.
5. Когда ветка релиза готова, она объединяется с develop и master.
6. Если в master обнаружена проблема, из нее создается ветка hotfix_*.
7. Как только исправление на ветке hotfix завершено, она объединяется с develop и master.

### Semantic versioning

Для определения версии используется [семантическое версионирование](https://semver.org/lang/ru/).
* МАЖОРНАЯ версия, когда сделаны обратно несовместимые изменения API.
* МИНОРНАЯ версия, когда вы добавляете новую функциональность, не нарушая обратной совместимости.
* ПАТЧ-версия, когда вы делаете обратно совместимые исправления.
### Conventional Commits

Формат commit-messages определяется стандартом [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/).

**Commit’ы могут содержать следующие структурные элементы для сообщений пользователям вашей библиотеки:**

* fix: commit типа fix исправляет ошибку (bug) в вашем коде (он соответствует PATCH в SemVer)
* feat: commit типа feat добавляет новую функцию (feature) в ваш код (он соответствует MINOR в SemVer).
* BREAKING CHANGE: commit, который содержит текст BREAKING CHANGE: в начале своего не обязательного тела сообщения (body) или в подвале (footer), добавляет изменения, нарушающие обратную совместимость вашего API (он соответствует MAJOR в SemVer). BREAKING CHANGE может быть частью commit’а любого типа.
* Другое: commit’ы с типами, которые отличаются от fix: и feat:, также разрешены. Например, @commitlint/config-conventional (основанный на The Angular convention) рекомендует: chore:, docs:, style:, refactor:, perf:, test:, и другие.

**Почему нужно использовать Conventional Commits**

* Автоматически генерируемый CHANGELOGs.
* Автоматическое определение семантической версии SemVer (на основе типов совершенных commit’ов).
* Коммуникация о характере изменений между товарищами по команде, общественностью и другими заинтересованными сторонами.
* Автоматически срабатываемый процесс сборки и публикации.
* Людям проще участвовать в вашем проекте, потому что им доступна более структурированная история коммитов

### CI rules

| branch | version | tag |
| :----- | :------ | :-- |
| `master` | из `package.json` | `latest` |
| `release/<version>` | `<version>-rc.<sha>` | `next` |
| `develop` | `<version>-alpha/beta<sha>` | `canary` |

* При PUSH в master обновляется версия, создается тэг, и публикуется версия в NPM
* При создании ветки release/* присваивается версия *-rc.*, публикация в NPM в ручном режиме по необходимости
* При PUSH/PULL_REQUEST в develop запускаются авто-тесты, создание альфа/бета версий и их публикация в ручном режиме по необходимости.

### Список команд

* *version:release*: обновление версий до релизных, создание тэгов и релизов github.
* *version:pre-release*: обновление версий до release candidate.
* *version:pre-release:alpha*: обновление версий до alpha.
* *version:pre-release:beta*: обновление версий до beta.
* *publish:release*: публикация релизной версии.
* *publish:pre-release*: публикация rc-версии.
* *publish:pre-release:alpha*: публикация alpha-версии.
* *publish:pre-release:beta*: публикация beta-версии.

---

### License

Licensed under the [MIT license](./LICENSE).

<div align="center">
    <a href="https://github.com/softspiders/softspiders">SOFTSPIDERS</a>
</div>
