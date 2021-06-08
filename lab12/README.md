# Отчет по лабораторной работе № 12

### Цель работы

Данная лабораторная работа посвещена изучению специализированного текстового редактора **Vim**

### Задания

- [x] 1. Создать публичный репозиторий с названием **lab12** на сервисе **GitHub**
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Ознакомиться со ссылками учебного материала
- [x] 4. Составить отчет и отправить ссылку личным сообщением в **Slack**

### Команды, выполненные в ходе выполнения лабораторной работы

Результаты см. в текущем репозитории

```ShellSession
$ vimtutor ru
```

```ShellSession
$ git clone https://github.com/lozchkavarene/lab7timp lab12timp
$ cd lab12timp
$ git remote remove origin
$ git remote add origin https://github.com/lozchkavarene/lab12timp
```

```ShellSession
$ vim README.md
:s/lab11timp/lab12timp/g
:wq
```

```ShellSession
$ vim demo/main.cpp
# Скопировать строчку и заменить print.hpp на cstdlib
Yp3wd3wi>cstdlib<ESC>

# Поиск в файле слова while, начинаем писать с новой строки
/while<CR>ostd::string log_path = std::getenv("LOG_PATH");<ESC>

# На строчку вверх, удаляем две строчки, на две вверх, вставляем удаленные,
# выделяем две строчки, уменьшаем отступ
k2dd2kpVj<
:wq
```

```ShellSession
$ pushd $HUNTER_ROOT
$ git config --global hub.protocol https
$ git fork # no such command in git
# gh repo create
$ gh release create v0.23.300
```

```ShellSession
$ wget https://github.com/NikZheleztsov/hunter/archive/refs/tags/v0.23.300.tar.gz
$ export MYHUNTER_SHA1=`openssl sha1 ${HUNTER_VERSION}.1.tar.gz | cut -d'=' -f2 | cut -c2-41`
$ echo $MYHUNTER_SHA1
$ rm -rf ${HUNTER_VERSION}.1.tar.gz
```
![Hunter fork release](https://github.com/lozchkavarene/hunter/releases/tag/v0.23.300)

```ShellSession
$ popd
$ echo $MYHUNTER_SHA1 | pbcopy
$ vim CMakeLists.txt
/SHA1<CR>
wc2w<C-V><ESC>
:wq
```

```ShellSession
$ vim README.md
/lab11timp<CR>
e<C-A>
ne<C-A>
:wq
```

```ShellSession
$ git add .
$ git commit -m "refactoring"
$ git push origin master
```

Vim используется в качестве основного редактора и IDE. В доказательство приведен конфиг .vimrc.

### Ссылки

- [ex](https://en.wikipedia.org/wiki/Ex_(text_editor))
- [vi](https://en.wikipedia.org/wiki/Vi)
- [hub](https://github.com/github/hub)
