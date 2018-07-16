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

Теперь закоммитим изменения:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_commit_2.png)

##### git log

Команда git log показывает, когда были выполнены последние изменения:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_log.png)

По умолчанию команда показывает все коммиты, начиная с ближнего по времени. С помощью дополнительных параметров можно не только посмотреть информацию о коммитах, но и какие изменения были внесены.

Флаг "-p" позволяет отразить отличия, которые были внесены каждым коммитом:

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_log_p.png)

Более короткий вариант вывода можно вывести с флагом "--stat":

![alt](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/git_log_stat.png)
