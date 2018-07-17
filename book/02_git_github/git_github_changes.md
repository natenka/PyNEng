### Работа с репозиторием заданий и примеров

В данной главе описано, как производить базовые операции с репозиториями GitHub, такие как клонирование репозитория, его синхронизация, pull и push.

#### Создание репозитория на GitHub

Для этого нужно:

* залогиниться на GitHub;
* в правом верхнем углу нажать плюс и выбрать "New repository", чтобы создать новый репозиторий;
* в открывшемся окне надо придумать название репозиторию;
* по желанию можно нажать галочку "Initialize this repository with a README". Это создаст файл README.md, в котором будет находиться только название репозитория.

![create](https://raw.githubusercontent.com/natenka/PyNEng/master/images/git/github_new_repo.png)

#### Клонирование репозитория с GitHub на локальный диск

Для локальной работы с созданным репозиторием его нужно склонировать. Для этого используется команда git clone:

```shellsession
$ git clone ssh://git@github.com/pyneng/online-2-natasha-samoylenko.git
Cloning into 'online-2-natasha-samoylenko'...
remote: Counting objects: 241, done.
remote: Compressing objects: 100% (191/191), done.
remote: Total 241 (delta 43), reused 239 (delta 41), pack-reused 0
Receiving objects: 100% (241/241), 119.60 KiB | 0 bytes/s, done.
Resolving deltas: 100% (43/43), done.
Checking connectivity... done.
```

В этой команде нужно изменить:

* имя пользователя "pyneng" на имя своего пользователя;
* имя репозитория "online-2-natasha-samoylenko" на свой репозиторий.

В итоге, в текущем каталоге, в котором была выполнена команда git clone, появится каталог с именем репозитория, в моём случае – online-2-natasha-samoylenko. В этом каталоге теперь находится содержимое репозитория GitHub.

#### Работа с репозиторием

Предыдущая команда не просто скопировала репозиторий локально, но и настроила соответствующим образом Git:

* был создан каталог .git;
* скачаны все данные репозитория;
* скачаны все изменения, которые были в репозитории;
* репозиторий на GitHub настроен как удалённый для этого репозитория.

Теперь локально готов полноценный репозиторий Git, в котором Вы можете работать. Обычно последовательность работы будет такой:

* перед началом работы синхронизировать локальное содержимое с GitHub командой git pull (синхронизация из GitHub в локальный репозиторий);
* редактируете файлы репозитория;
* добавляете их в staging командой git add;
* делаете commit с помощью git commit;
* когда Вы готовы закачать локальные изменения на GitHub, делаете git push.

При работе с заданиями на работе и дома, надо не забывать первый и последний шаг:

* первый шаг – обновляет локальный репозиторий;
* последний шаг – загружает изменения на GitHub.

#### Синхронизация из GitHub в локальный репозиторий

Все команды выполняются внутри каталога репозитория (в примере выше – online-2-natasha-samoylenko). Если содержимое локального репозитория одинаково с удалённым репозиторием на GitHub, то вывод git pull будет таким:

```shellsession
$ git pull
Already up-to-date.
```

Если что-то было изменено, то вывод будет примерно таким:

```shellsession
$ git pull
remote: Counting objects: 5, done.
remote: Compressing objects: 100% (1/1), done.
remote: Total 5 (delta 4), reused 5 (delta 4), pack-reused 0
Unpacking objects: 100% (5/5), done.
From ssh://github.com/pyneng/online-2-natasha-samoylenko
   89c04b6..fc4c721  master     -> origin/master
Updating 89c04b6..fc4c721
Fast-forward
 exercises/03_data_structures/task_3_3.py | 2 ++
 1 file changed, 2 insertions(+)
```

#### Push на GitHub

Для загрузки всех локальных изменений на GitHub используется git push:

```shellsession
$ git push origin master
Counting objects: 5, done.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 426 bytes | 0 bytes/s, done.
Total 5 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4), completed with 4 local objects.
To ssh://git@github.com/pyneng/online-2-natasha-samoylenko.git
   fc4c721..edcf417  master -> master
```
