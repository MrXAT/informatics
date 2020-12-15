# 3 часть, уровень Exper

Пользователи и группы в UNIX.
Права доступа к файлам и директориям
Команды chmod и chown

## 1. Создайте в своей домашней директорию файл под названием shared.txt. Объясните, какими правами доступа он обладает (для этого можно воспользоваться командой ls -la)


```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ touch shared.txt
kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls -la shared.txt 
-rw-rw-r-- 1 kirill kirill 0 дек 15 19:49 shared.txt
```

## 2. C помощью команды chmod сделайте так, чтобы созданный файл был доступен только его владельцу и только на чтение.


```console
    Забираю все права у всех пользователей
kirill@kirill-Lenovo-ideapad-330-15AST:~$ chmod ugo-rwx shared.txt 
kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls -la shared.txt 
---------- 1 kirill kirill 0 дек 15 19:49 shared.txt
    Даю право на чтение владельцу
kirill@kirill-Lenovo-ideapad-330-15AST:~$ chmod u+r shared.txt 
kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls -la shared.txt 
-r-------- 1 kirill kirill 0 дек 15 19:49 shared.txt
```


## 3. С помощью команды chown сделайте вашего соседа справа владельцем файла shared.txt, затем верните соседу слева полученный от него файл.


```console
Не получится. Мой сосед справа уехал в Тыву :-)
```

