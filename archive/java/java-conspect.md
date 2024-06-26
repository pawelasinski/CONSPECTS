![](_java_pictures/JDK.png)

Для проверки правильной установки компилятора Java:  
```zsh
javac -version
```
Если выдало ошибку, то нужно сперва проверить переменную PATH.

---

1. Чтобы скомпелировать исходники в байткод:
```bash
javac Draft.java
javac -classpath lib.jar Draft.java  # если нужно указать зависимые библиотеки
```
Если нужно скомпелировать несколько, то указываем их через пробел.

2. Чтобы прочитать байткод:
```zsh
javap Draft.class
```
	-v = -verbose

3. Чтобы запустить скомпелированную программу:
```zsh
java Draft
java -classpath <path/to/dir/w/bytecode> Draft
java -classpath lib.jar:draft.jar Draft  # если нужно указать зависимые библиотеки (: - Linux, ; - Windows)
```
Если программа состоит из нескольких классов, то все они должны быть доступны виртуальной машине.

---

`jar`-архив — портабельный `ZIP`-архив с дополнительным файлом `MANIFEST`, содержащий метаинформацию о программе (имя программы, версия, имя главного класса).
```zsh

jar cfe draft.jar Draft Draft.class ...  # создать такой архив

jar tf draft.jar  # посмотреть его содержимое

jar xf draft.jar  # распаковать

java -jar draft.jar  # запустить, если имеется имя главного класса 
java -classpath draft.jar Draft  # и если нет
```

---


