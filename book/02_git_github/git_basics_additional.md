#### Дополнительные возможности

##### git diff

Команда git diff позволяет просмотреть разницу между различными состояниями. Например, в репозитории внесены изменения в файл README и .gitignore.

Команда git status показывает, что оба файла изменены:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_status_5.png)

git diff показывает, какие изменения были внесены со времени последнего коммита:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_diff.png)

Если добавить изменения в файлы без коммита, и затем ещё раз выполнить git diff, она ничего не покажет:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_add_git_diff.png)

Чтобы показать отличия между staging и последним коммитом, надо добавить в команду параметр --staged:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_diff_staged.png)

##### git log

Команда git log показывает, когда были выполнены последние изменения:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_log.png)

По умолчанию, команда показывает все коммиты, начиная с ближайшего по времени. С помощью дополнительных параметров можно не только посмотреть информацию о коммитах, но и какие изменения были внесены.

Флаг "-p" позволяет отразить отличия, которые были внесены каждым коммитом:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_log_p.png)

Параметр "-p" указывает путь, откуда будут выводиться данные по коммитам. Например если использовать "-p ..origin/master", выведутся коммиты с репозитория на GitHub, которых нет в локальном репозитории.

```shellsession
$ git log -p ..origin/master
commit 4c1821030d20b3682b67caf362fd777d098d9126
Author: Наташа Самойленко <nataliya.samoylenko@gmail.com>
Date:   Mon May 29 07:53:45 2017 +0300

Update README.md

diff --git a/tools/README.md b/tools/README.md
index 2b6f380..4f8d4af 100644
--- a/tools/README.md
+++ b/tools/README.md
@@ -1 +1,4 @@
+
+Тут находятся PDF версии руководств по настройке инструментов, которые используются на курсе.
```

Параметр "-1" позволяет вывести только один последний коммит.

Более короткий вариант вывода можно вывести с флагом "--stat":

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_log_stat.png)
