# clamshellctl

CLI-утилита для macOS, которая включает режим keep-awake и помогает работать в clamshell-режиме.

Используются:
- `caffeinate -dimsu`
- `pmset -a disablesleep 1`

---

## ⚙️ Stack

- Bash
- macOS `caffeinate`
- macOS `pmset`

---

## 🚀 Установка

1. Клонируй репозиторий:

```bash
git clone https://github.com/akarmain/clamshellctl.git
cd clamshellctl
```

2. Дай права и установи команду в PATH:

```bash
chmod +x clamshellctl
./clamshellctl install
```

Если без `sudo`:

```bash
./clamshellctl install --user
```

---

## ▶️ Использование

Включить режим:

```bash
clamshellctl on
```

Включить режим на N минут:

```bash
clamshellctl on 45
# или
clamshellctl on -m 45
```

Выключить:

```bash
clamshellctl off
```

Проверить статус:

```bash
clamshellctl status
```

Справка:

```bash
clamshellctl help
```

---

## 🛠 Troubleshooting

Если при запуске видишь:

- `zsh: permission denied: clamshellctl`
- `zsh: too many levels of symbolic links: ./clamshellctl`

значит сломалась символическая ссылка установки.

Починка:

```bash
cd /path/to/clamshellctl-repo
chmod +x ./clamshellctl
rm -f ~/.local/bin/clamshellctl
ln -s "$(pwd)/clamshellctl" ~/.local/bin/clamshellctl
rehash
clamshellctl help
```

После обновления скрипта `install --user` дополнительно проверяет источник и защищается от циклов симлинков.

---

## ⚠️ Важно

- При закрытой крышке без охлаждения возможен перегрев.
- После работы выключай режим через `clamshellctl off`.
- Нужны права администратора для изменения `pmset`.

---

## 🧾 История промптов

Эта версия утилиты была собрана за **4 запроса** (из них 3 уникальных).  
Полный список смотри в [PROMPTS.md](./PROMPTS.md).

---

## 🔑 License

MIT

---
_Спасибо, что читаете мой код!_
