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

kirill@kirill-Lenovo-ideapad-330-15AST:~$ chown right-hand-man ./shared.txt 
```

## 4. Проделайте те же операции, что и в п.1-3, но с директорией


```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls -la another_dir/
итого 8
drwxrwxr-x  2 kirill kirill 4096 дек 15 19:28 .
drwxr-xr-x 30 kirill kirill 4096 дек 15 19:49 ..
kirill@kirill-Lenovo-ideapad-330-15AST:~$ chmod ugo-rwx another_dir/
kirill@kirill-Lenovo-ideapad-330-15AST:~$ chmod u+r another_dir/
kirill@kirill-Lenovo-ideapad-330-15AST:~$ ls -la another_dir/
ls: невозможно получить доступ к 'another_dir/.': Отказано в доступе
ls: невозможно получить доступ к 'another_dir/..': Отказано в доступе
итого 0
d????????? ? ? ? ?            ? .
d????????? ? ? ? ?            ? ..

```

## 5. Объясните что было бы, если операции из пункта 3  и 4 можно было бы делать обычным пользователям. Какие проблемы безопасности это имеет и почему они были запрещены.



```console
потому что локальный доступ к файлам для всех программ и всех пользователей позволил бы вирусам без проблем уничтожить систему.
```
