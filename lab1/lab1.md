# 1 часть, уровень Novice

Команды cd, ls, touch, cp, mv, rm, mkdir, mcedit, pwd.
Вывод файла на экран: cat, less
Прерывание программы по сигналу: CTRL+С


## 1. Создайте директорию, создайте файл, поперемещайте и покопируйте их. Попытайтесь удалить созданную директорию.



```console
kirill@kirill-VirtualBox:~$ mkdir dir
kirill@kirill-VirtualBox:~$ ls
 dir         Видео       Загрузки      Музыка         'Рабочий стол'
 Templates   Документы   Изображения   Общедоступные

kirill@kirill-VirtualBox:~$ cd dir/
kirill@kirill-VirtualBox:~/dir$ touch file.txt
kirill@kirill-VirtualBox:~/dir$ ls
file.txt
kirill@kirill-VirtualBox:~/dir$ mcedit file.txt

kirill@kirill-VirtualBox:~/dir$ mkdir dir2
kirill@kirill-VirtualBox:~/dir$ ls
dir2  file.txt
kirill@kirill-VirtualBox:~/dir$ cp file.txt dir2
kirill@kirill-VirtualBox:~/dir$ cd dir2
kirill@kirill-VirtualBox:~/dir/dir2$ ls
file.txt
kirill@kirill-VirtualBox:~/dir/dir2$ cd ..
kirill@kirill-VirtualBox:~/dir$ ls
dir2  file.txt
kirill@kirill-VirtualBox:~/dir$ mv file.txt rename.txt
kirill@kirill-VirtualBox:~/dir$ ls
dir2  rename.txt

kirill@kirill-VirtualBox:~/dir$ ls
dir2
kirill@kirill-VirtualBox:~/dir$ cd dir2/
kirill@kirill-VirtualBox:~/dir/dir2$ ls
file.txt  rename.txt
kirill@kirill-VirtualBox:~/dir/dir2$ cd ..
kirill@kirill-VirtualBox:~/dir$ rmdir dir2/
rmdir: не удалось удалить 'dir2/': Каталог не пуст

kirill@kirill-VirtualBox:~/dir/dir2$ cat rename.txt 
text text text text text text text text text text textkirill@kirill-VirtualBox:~/dir/dir2$ ls
file.txt  rename.txt
kirill@kirill-VirtualBox:~/dir/dir2$ less rename.txt 

```


## 2. Каков полный путь до вашей домашней директории?

```console
kirill@kirill-VirtualBox:~$ pwd
/home/kirill
```
## 3. Что делает команда cd без параметров?

```console
Перемещает в домашнюю директорию.
```
## 4. Чем отличается cat от less?

```console
cat выводит содержимое текстового файла в консоль.
less позволяет в отдельном окне просматривать содержимое файла.
```
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
# 2 часть, уровень Advanced

Команды find и grep
Перенаправление вывода: >, >>, |. stdin и stderr


## 0. Скачайте крупный текстовый файл, выполнив команду wget http://factorized.net/crusoe.txt

```console
kirill@kirill-VirtualBox:~$ mkdir dir
kirill@kirill-VirtualBox:~$ ls
 dir         Видео       Загрузки      Музыка         'Рабочий стол'
 Templates   Документы   Изображения   Общедоступные
kirill@kirill-VirtualBox:~$ cd dir/
kirill@kirill-VirtualBox:~/dir$ wget http://factorized.net/crusoe.txt
--2020-11-04 15:57:28--  http://factorized.net/crusoe.txt
Распознаётся factorized.net (factorized.net)… 185.199.109.153, 185.199.110.153, 185.199.111.153, ...
Подключение к factorized.net (factorized.net)|185.199.109.153|:80... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 652809 (638K) [text/plain]
Сохранение в: «crusoe.txt»

crusoe.txt          100%[===================>] 637,51K   593KB/s    за 1,1s    

2020-11-04 15:57:30 (593 KB/s) - «crusoe.txt» сохранён [652809/652809]

kirill@kirill-VirtualBox:~/dir$ ls
crusoe.txt
```


## 1. Найти все файлы *.txt в папке /tmp

```console
kirill@kirill-VirtualBox:~$ mv dir tmp
kirill@kirill-VirtualBox:~$ ls
 Templates   Видео       Загрузки      Музыка         'Рабочий стол'
 tmp         Документы   Изображения   Общедоступные
kirill@kirill-VirtualBox:~$ cd tmp/
kirill@kirill-VirtualBox:~/tmp$ ls
crusoe.txt
kirill@kirill-VirtualBox:~/tmp$ cd ..
kirill@kirill-VirtualBox:~$ find ./tmp -name "*.txt"
./tmp/crusoe.txt
```

## 2. Найти все строки "friday" в большом текстовом файле

```console
kirill@kirill-VirtualBox:~$ cd tmp
kirill@kirill-VirtualBox:~/tmp$ grep -o -i 'friday' crusoe.txt
Friday
Friday
Friday
...
Friday
```

## 3. С помощью > и >> записать в текстовый файл фразу "Hello world"

```console
kirill@kirill-VirtualBox:~/tmp$ touch file
kirill@kirill-VirtualBox:~/tmp$ echo Hello world >> file
kirill@kirill-VirtualBox:~/tmp$ cat file
Hello world

```
## 4. Вывести в файл список файлов в текущей директории

```console
kirill@kirill-VirtualBox:~/tmp$ ls >> file
kirill@kirill-VirtualBox:~/tmp$ cat file
Hello world


crusoe.txt
crusoe.txt friday
dasfjk
file
Hello
j
sfdjk

kirill@kirill-VirtualBox:~/tmp$ ls
 crusoe.txt  'crusoe.txt friday'   dasfjk   file   Hello   j   sfdjk
```
## 5. Попробовать найти все файлы *.txt на всём диске.

```console
kirill@kirill-VirtualBox:~/tmp$ cd
kirill@kirill-VirtualBox:~$  find -name "*.txt"
./.cache/tracker/parser-version.txt
./.cache/tracker/db-locale.txt
./.cache/tracker/db-version.txt
./.cache/tracker/locale-for-miner-apps.txt
./.cache/tracker/first-index.txt
./.cache/tracker/last-crawl.txt
./.mozilla/firefox/1kuwwetb.default-release/SecurityPreloadState.txt
./.mozilla/firefox/1kuwwetb.default-release/serviceworker.txt
./.mozilla/firefox/1kuwwetb.default-release/AlternateServices.txt
./.mozilla/firefox/1kuwwetb.default-release/SiteSecurityServiceState.txt
./.mozilla/firefox/1kuwwetb.default-release/pkcs11.txt
./tmp/crusoe.txt
./Templates/Text File.txt

```

# 3 часть, уровень Expert

Более умная обработка файлов: wc, awk, sed
Полезно почитать: man hier (от слова hierarchy, иерархия)
Текстовый редактор для простых смертных: mcedit



## 1. Найти количество упоминаний слова “Friday” в большом текстовом файле.

```console
kirill@kirill-Lenovo-ideapad-330-15AST:~$ cd crusoe/
kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ ls
crusoe.txt
kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ grep -o 'Friday' crusoe.txt | wc -l
188

kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ grep -i -c "friday" crusoe.txt
188
```

## 2. Заменить в текстовом файле все слова “Friday” на “Saturday”

```console
kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ sed -i 's/Friday/Saturday/g' crusoe.txt
kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ grep -o 'Saturday' crusoe.txt | wc -l
188

```
## 3. Свободное задание на арифметические действия с данными из файла с помощью awk. 

Подсчитать сумму чисел по столбцам 

Дан входной файл, где на каждой строке находятся два целых числа, разделенных пробелом. Надо посчитать сумму чисел в первом столбце и во втором. Вывести результат на экран.

```console
kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ mcedit file

kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ cat file
1 2
2 2
3 7
kirill@kirill-Lenovo-ideapad-330-15AST:~/crusoe$ awk '{ sum1 += $1 } {sum2 += $2} END { print sum1 " " sum2}' file
6 11



```
