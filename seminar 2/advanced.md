# 2 часть, уровень Advanced

Команды which и whereis
Переменная окружения $PATH
Запуск исполняемых файлов из текущей директории и из произвольной директории.




## 1. С помощью команд which и whereis выясните, в какой директории находятся программы cat, less, grep и find


```console
kirill@kirill-Lenovo-ideapad-330-15AST:~/another_dir$ which cat
/usr/bin/cat
kirill@kirill-Lenovo-ideapad-330-15AST:~/another_dir$ which less
/usr/bin/less
kirill@kirill-Lenovo-ideapad-330-15AST:~/another_dir$ whereis grep
grep: /usr/bin/grep /usr/share/man/man1/grep.1.gz /usr/share/info/grep.info.gz
kirill@kirill-Lenovo-ideapad-330-15AST:~/another_dir$ whereis find
find: /usr/bin/find /usr/share/man/man1/find.1.gz /usr/share/info/find.info-2.gz /usr/share/info/find.info-1.gz /usr/share/info/find.info.gz

```

## 2. Выведите на экран значение переменной окружения $PATH (echo $PATH) и убедитесь, что директория, найденная в п.1 входит в $PATH


```console

kirill@kirill-Lenovo-ideapad-330-15AST:~/another_dir$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

```
## 3. Скомпилируйте какую-нибудь программу на C и попробуйте запустить её, находясь в той же директории. Перейдите в другую директорию и запустите ту же программу.

```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ cd 223/
kirill@kirill-Lenovo-ideapad-330-15AST:~/223$ cat main.c
#include <stdio.h>

int main() {
    printf("Hello World! \n");

    return 0;

kirill@kirill-Lenovo-ideapad-330-15AST:~/223$ ./main 
Hello World! 
kirill@kirill-Lenovo-ideapad-330-15AST:~/223$ cd
kirill@kirill-Lenovo-ideapad-330-15AST:~$ cd another_dir/
kirill@kirill-Lenovo-ideapad-330-15AST:~/another_dir$ /home/kirill/223/main
Hello World! 
```

## 4. Добавьте директорию, в которой лежит программа из п.3 в $PATH (export PATH=$PATH:<новая директория>). 

```console
kirill@kirill-Lenovo-ideapad-330-15AST:~/223$ export PATH=$PATH:/home/kirill/223
kirill@kirill-Lenovo-ideapad-330-15AST:~/223$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/kirill/new_dir::/home/kkirill/223
```
