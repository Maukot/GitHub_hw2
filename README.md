# GitHub_hw2

**1. На локальном репозитории сделать ветки**

  - Создать удаленный репозиторий *+New repository*
  - Code - HTTPS - Copy link
  - В Git Bash:
```
$ git clone https://github.com/Maukot/GitHub_hw2.git
$ cd GitHub_hw2
$ cat > script.sh                                   # скрипт для создания нескольких веток
#!/bin/bash
for branchName in Postman Jmeter CheckLists BugReports SQL Charles MobileTesting
do git branch $branchName 
done

$ ./script.sh                                       # запускаю скрипт
$ git branch                                        # проверяю, что всё создалось
  BugReports
  Charles
  CheckLists
  Jmeter
  MobileTesting
  Postman
  SQL
* main

$ rm script.sh                                      # удаляю скрипт, чтоб не мешал
```

**2. Запушить все ветки на внешний репозиторий**
```
$ git push -u origin  --all
```
**3. В ветке BugReports сделать текстовый документ со структурой багрепорта**
```
$ git checkout BugReports
$ vim bug_report_template.txt
```
*в Vim i - вход в режим редактирования, Esc - выход из режима редактирования, :wq - для выхода из Vim с сохранением изменений*

**4. Запушить структуру багрепорта на внешний реп**
```
$ git add bug_report_template.txt
$ git commit -m "add file with bug report template"
$ git push                                         # файл появится только в ветке BugReports
```

**5. Вмержить ветку BugReports в main**
```
$ git checkout main                                #сначала переходим в ту ветку, в которую будем мержить
$ git merge BugReports
```

**6. Запушить main на внешний репозиторий**
```
$ git push
```

**7. В ветке CheckLists набросать структуру чек-листа**
```
$ git checkout CheckLists
$ vim checklist.txt
```

**8. Запушить структуру на внешний реп**
```
$ git add checklist.txt ; git commit -m "add checklist.txt"
$ git push
```

**9. На внешнем репозитории сделать Pull request ветки CheckLists в main**

кнопка *Compare & pull request*  
кнопка *Create pull request*  
кнопка *Merge pull request*  
кнопка *Confirm merge*

**10. Синхронизировать внешнюю и локальную ветки main**
```
$ git checkout main
$ git fetch
$ git pull
```
