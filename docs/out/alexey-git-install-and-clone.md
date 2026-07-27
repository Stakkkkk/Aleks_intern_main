# Инструкция для Алексея: установить Git и клонировать репозиторий

Дата подготовки: 2026-07-24.

Результат: на компьютере будет установлен Git, а локально появится папка с проектом `Aleks_intern_main`.

## 1. Установить Git

Вариант через сайт:

1. Открой официальный сайт Git для Windows: <https://git-scm.com/install/windows>.
2. Скачай актуальный установщик Git for Windows для своей системы. Обычно нужен x64 Setup.
3. Запусти установщик.
4. На шагах установки оставляй настройки по умолчанию, если нет понятной причины менять их.
5. Дождись завершения установки.

Вариант через PowerShell, если на компьютере работает `winget`:

```powershell
winget install --id Git.Git -e --source winget
```

Официальная страница Git также приводит этот вариант установки через `winget`.

## 2. Проверить установку

Открой PowerShell или Git Bash и выполни:

```powershell
git --version
```

Если Git установлен, команда покажет версию, например `git version ...`.

## 3. Настроить имя и email для коммитов

Эти данные будут попадать в историю Git-коммитов. Если не уверен, какой email указывать, лучше использовать email GitHub или noreply-email из настроек GitHub.

```powershell
git config --global user.name "Твое имя"
git config --global user.email "твой-email@example.com"
```

Проверить настройки:

```powershell
git config --global --list
```

## 4. Выбрать папку для проектов

Пример для папки `Projects` в профиле пользователя:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\Projects"
Set-Location "$env:USERPROFILE\Projects"
```

Можно выбрать другую папку, если так удобнее.

## 5. Клонировать наш репозиторий

Выполни:

```powershell
git clone https://github.com/Stakkkkk/Aleks_intern_main.git
```

После этого перейди в папку проекта:

```powershell
Set-Location Aleks_intern_main
```

## 6. Проверить, что все получилось

Внутри папки проекта выполни:

```powershell
git status
git remote -v
```

Ожидаемо:

- `git status` показывает ветку `main` и отсутствие изменений;
- `git remote -v` показывает ссылку на `https://github.com/Stakkkkk/Aleks_intern_main.git`.

## 7. Как получать изменения из репозитория

Перед началом работы открой Git Bash, перейди в папку проекта и подтяни последние изменения:

```bash
cd ~/Projects/Aleks_intern_main
git pull origin main
```

Если ты уже находишься в папке проекта, достаточно выполнить только:

```bash
git pull origin main
```

Ожидаемый спокойный результат, если новых изменений нет: `Already up to date.`

## 8. Если что-то пошло не так

Пиши наставнику не просто "не получилось", а в таком формате:

```text
Шаг:
Команда:
Что ожидал:
Что получилось:
Текст ошибки или скриншот:
```

Так будет намного быстрее понять, где именно проблема.

## Источники

- Официальная установка Git для Windows: <https://git-scm.com/install/windows>.
- Официальная инструкция GitHub по клонированию репозитория: <https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository>.
