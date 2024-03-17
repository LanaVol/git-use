# GIT

## Basic Commans

To initialize local setting git repozitory. створиться папка проекту, що включатиме папку з .git, що контролюватиме історію змін в даному проекті

```bash
  git init myproject
```

Ввійти до папки створеного проекту

```bash
  cd myproject
```

To show modified files in working directory - checking the state of changes at the moment

```bash
  git status
```

To retrieve an entire repository from a hosted location via URL

```bash
  git clone [url]
```

To add all files to git watcher - проіндексувати зміни в репозиторії

```bash
  git add .
```

To add fileName to git watcher - проіндексувати зміни файлу fileName в репозиторії. Можна проіндексувати кілька файлів і після того виконати коміт - зміни в доданих файлах будуть позначені під одним вказаним комітом

```bash
  git add fileName
```

Зняти/скасувати індексацію доданих змін, які ми щойно проіндексували, перед комітом або скинути буферну зону (тобто зміни були проіндексовані і готові до коміту)

```bash
  git reset
```

Команда reset скидає буферну зону до HEAD. Це очищає буферну зону від змін, які ми щойно проіндексували.

```bash
  git reset HEAD hello.html
```

To add commit with short info about this part of work. Мітку -m робить коментар у командному рядку. Команда commit дозволяє інтерактивно редагувати коментарі для коміту.

```bash
  git commit -m 'first commit'
```

Додати зміни до існуючого коміту в гілці - тобто спочатку потрібно виконати git add <changeFile> i далі списати відповідно команду нижче - це додасть зміни в попередній коміт

```bash
  git commit --amend -m 'update created commit'
```

To push files with folliwing commit from local to remote repozitory

```bash
  git push origin master
```

To get previous history of commits

```bash
  git fetch
```

## Colaborations

To create adding branch with name 'new branch'

```bash
  git checkout -b <new branch>
```

To switch another branch 'master'

```bash
  git checkout master
```

To merge common branch 'master' with your developing branch you have to switch to your developing branch and than from there do the commant to merge chenges:

```bash
  git merge master
```

## Control history of git

To get the list of all changes (commits) what had been done

```bash
  git log
```

To get the list of all changes (commits) what had been done in one line view

```bash
  git log --pretty=oneline
```

За замовчуванням показується історія лише однієї поточної гілки, але мітка --all гарантує, що ми бачимо всі гілки.

```bash
  git log --all
```

## Different branches

Переглянути поточні гілки

```bash
  git branch
```

Створити іншу гілку

```bash
  git branch <branchName>
```

Щоб розробляти в новій гілці, треба на неї переключитися (зробити так, щоб на неї вказував HEAD), виконавши команду:

```bash
  git checkout <branchName>
```

Створити нову гілку і відразу переключитися на неї та працювати в новій гілці

```bash
  git checkout -b <branchName>
```

Після створення нової гілки варто перевіряти статус і на якій саме гілці ви зараз знаходитесь для уникнення помилкових комітів

```bash
  git status
```

Перемикнутись на іншу гілку

```bash
  git checkout <branchName>
```

Часто виникають ситуації, що ми робили зміни в одній гілці, а нам терміново треба переключитися на іншу. Що робити з незакоміченими змінами?
Якщо нам не треба зберігати ці зміни, можна виконати команду

```bash
  git checkout -f master
```

А якщо зміни потрібно зберегти, скористайтесь командою:

```bash
  git stash
```

Ця команда збирає незакомічені зміни і архівує в гіт. Для того, щоб їх повернути (це можна зробити в будь-якій гілці):

```bash
  git stash pop
```

Витягти з зазначеного віддаленого репозиторію копію поточної гілки та негайно злити її з локальною копією.

```bash
  git pull <remote>
```

## Update remote branch info

1. If you have some worrking code and if you don't want to make commit, you may save this in stash

```bash
  git stash
```

2. Check on what branch you are right now

```bash
  git branch
```

3. Move to branch you need

```bash
  git checkout <neded branch>
```

4. Download chenges from neded branch to your local branch but not merge with it

```bash
  git fetch
```

5. Pull (merge with your local branch) all the changes from neded branch

```bash
  git pull origin <neded branch>
```

6. Now you have to resolve the conflicts. After resolving you can move to your working branch

```bash
  git checkout <working branch>
```

7. To return to your previous code which have stashed, look which id have your saved code

```bash
  git stash list
```

8. Return your code according current id

```bash
  git stash apply <id>
```

9. You can leave this code in stash or if you want to delete this from stash use this command:

```bash
  git stash drop <id>
```

10. And continue to work :)
