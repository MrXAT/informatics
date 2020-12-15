# 1 часть, уровень Novice

Скрытые файлы (hidden files)
Команда ls -a



## 1. Создайте файл, имя которого начинается с точки. Убедитесь, что его не видно с помощью обычной команды ls


```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ touch .filefile

kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls
 crusoe        snap        Загрузки      Общедоступные   Шаблоны
 dir           Видео       Изображения  'Рабочий стол'
 programming   Документы   Музыка        Учеба
```

## 2. Выясните, какие скрытые файлы и директории находятся в вашей домашней директории


```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls -a
 .               dir           .pki                        Документы
 ..              .filefile     .profile                    Загрузки
 .bash_history   .fontconfig   programming                 Изображения
 .bash_logout    .gnupg        snap                        Музыка
 .bashrc         .hardinfo     .ssh                        Общедоступные
 .cache          .java         .sudo_as_admin_successful  'Рабочий стол'
 .config         .local        .vscode                     Учеба
 crusoe          .mozilla      Видео                       Шаблоны

```
## 3. Ищет ли find по скрытым файлам и директориям? 


```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ find -type f -name ".*"

./.bashrc
./programming/code/CLion projects/smth/untitled/.idea/.gitignore
./programming/code/CLion projects/labs/lab0/.idea/.gitignore
./.java/.userPrefs/.userRootModFile.kirill
./.java/.userPrefs/.user.lock.kirill
./.cache/JetBrains/CLion2020.2/.appinfo
./.cache/JetBrains/CLion2020.2/log/threadDumps-freeze-20201114-153136-CL-202.7660.37/.duration
./.cache/JetBrains/CLion2020.2/index/stubs/.binary_builders
./.cache/JetBrains/CLion2020.2/index/stubs
./.vscode/extensions/ms-vscode.cpptools-1.1.1/.vsixmanifest
./.vscode/extensions/formulahendry.code-runner-0.11.1/node_modules/tree-kill/.npmignore
./.vscode/extensions/formulahendry.code-runner-0.11.1/node_modules/applicationinsights/.npmignore
./.vscode/extensions/formulahendry.code-runner-0.11.1/.vsixmanifest
./.vscode/extensions/formulahendry.code-runner-0.11.1/.travis.yml
./.config/google-chrome/Default/.com.google.Chrome.jW68Bi
./.config/google-chrome/Default/File System/000/t/.usage
./.config/google-chrome/Default/File System/005/t/.usage
./.config/google-chrome/Default/File System/004/t/.usage
./.config/google-chrome/Default/File System/001/t/.usage
./.config/google-chrome/Default/File System/008/t/.usage
./.config/google-chrome/Default/File System/006/t/.usage
./.config/google-chrome/Default/File System/003/t/.usage
./.config/google-chrome/Default/File System/007/t/.usage
./.config/google-chrome/Default/File System/002/t/.usage
./.config/google-chrome/.com.google.Chrome.6k3zxh
./.config/libreoffice/4/.lock

