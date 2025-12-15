# Lab 1
# Лабораторная работа №1  

<a href="https://docs.github.com/en"><img src="https://img.shields.io/static/v1?logo=github&logoColor=fff&label=&message=Docs&color=36393f&style=flat" alt="GitHub Docs"></a>
<a href="https://daringfireball.net/projects/markdown"><img src="https://img.shields.io/static/v1?logo=markdown&logoColor=fff&label=&message=Markdown&color=36393f&style=flat" alt="Markdown"></a> 
<a href="https://symbl.cc/en/unicode-table"><img src="https://img.shields.io/static/v1?logo=unicode&logoColor=fff&label=&message=Unicode&color=36393f&style=flat" alt="Unicode"></a> 
<a href="https://shields.io"><img src="https://img.shields.io/static/v1?logo=shieldsdotio&logoColor=fff&label=&message=Shields&color=36393f&style=flat" alt="Shields"></a>
<a href="https://img.shields.io/badge/Risk_Analyze-2448a2"><img src="https://img.shields.io/badge/Course-Risk_Analysis-2448a2" alt= "RA"></a> <img src="https://img.shields.io/badge/AppSec-2448a2" alt= "RA"></a> <img src="https://img.shields.io/badge/Contributor-Шмаков_И._С.-8b9aff" alt="Contributor Badge"></a></div>

***

Ананикян Тигран ИУ10-96

## Данная лабораторная работа посвещена изучению систем обмена данными. Работа позволит ознакомиться с базовыми навыками необходимыми для произведения commit changes, публикации изменний в удаленный репозиторий, обновлениями данных для них, fork и тд.


## Задание

✅ 1. Зарегистрироваться на почтовом сервисе **Gmail**. В случае наличия аккаунта - не требуется

✅ 2. Зарегистрироваться на сервисе совместной разработки **GitHub**. В случае наличия аккаунта требуется произвести дополнительные настройки и обновить данные персонификации

✅ 3. Отправить зарегистрированный адрес почтового ящика личным сообщением

✅ 4. Отправить зарегистрированный логин личным сообщением

✅ 5. Ознакомиться со ссылками учебного материала и формализованными требованиями из основного описания

✅ 6. Сгенирировать **SSH** ключ и добавть его в список ключей для сервиса **GitHub**
<img width="701" height="788" alt="Снимок экрана 2025-11-24 135323" src="https://github.com/user-attachments/assets/59f39ea1-57a5-48c2-9345-bcbccce92c55" />
<img width="998" height="296" alt="Снимок экрана 2025-11-24 135642" src="https://github.com/user-attachments/assets/0ff4c665-afaf-4bed-abad-aa0c54752952" />

✅ 7. Сгенерировать Personal Token с правами gist и сохранить его в файл
<img width="1432" height="527" alt="Снимок экрана 2025-11-24 140521" src="https://github.com/user-attachments/assets/bf67e921-70a6-436c-a6d1-1a99603f6aed" />

✅8. Сгенерировать GnuPG для подтверждения подписания коммитов и возможно использование Х.509 (включить в отчет описание, что такое smimesign)

smimesign — инструмент для подписи Git-коммитов с помощью сертификатов X.509 / S/MIME, в отличие от GPG. Используется в корпоративных политиках. GitHub распознаёт такие подписи как Verified.
<img width="980" height="421" alt="Снимок экрана 2025-11-24 141229" src="https://github.com/user-attachments/assets/dac31b4b-5ba7-41f3-9329-ecb73ec072dd" />

✅9. Подготовить глобальные переменные окружения для GitHub
``` bash
┌──(tigo㉿tigo)-[~]
└─$ git config --list
user.name=tigo11
user.email=tigrulia_442@mail.ru
user.signingkey=E0C9B65FF7990225
core.editor=nano
core.autocrlf=input
help.autocorrect=prompt
credential.helper=cache
commit.gpgsign=true
```

✅11. Ознакомиться с материалами gh сервиса и использовать их для авторизации, commit, pull request и тд.
``` bash
┌──(tigo㉿tigo)-[~]
└─$ gh auth status

github.com
  ✓ Logged in to github.com account tigo11 (keyring)
  - Active account: true
  - Git operations protocol: https
  - Token: ghp_************************************
  - Token scopes: 'admin:org', 'gist', 'repo', 'workflow'
```

12. Выполнить инструкцию учебного материала
13. Оформить README.md по аналогии и использовать shield, etc.
14. Составить gist отчет и отправить ссылку личным сообщением

***

Создайте локальный репозиторий на машине, проинициализируйте репозиторий
``` bash
mkdir risk_lab1
cd risk_lab1

git init
```
Авторизуйтесь и используйте GitHub CLI для создания удаленного репозитория
``` bash
gh repo create lab1 --public
✓ Created repository tigo11/lab1 on github.com
  https://github.com/tigo11/lab1
```
Создайте пустой README.md
``` bash
git add README.md
```

Используйте указание URL своего созданного репозитория для присвоения ветки master статуса origin
``` bash
git branch -M master
git remote add origin https://github.com/tigo11/lab1.git
```
В локальном репозитории и сделайте commit
Сделайте публикацию своего commit с флагом -S в удаленный репозиторий
``` bash
git commit -S -m "Initial commit"

[master (root-commit) 56d620d] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

git push -u origin master

Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 876 bytes | 876.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/tigo11/lab1.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

```
Создайте файл hello.py в локальном репозитории. Реализуйте Hello appsec world на языке python используя несколько интерпретаторов с "грязным" кодом
``` bash
git status  
                                 
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.py

nothing added to commit but untracked files present (use "git add" to track)
                                                                     
git add hello.py 
                                                                     
git commit -S -m "hello.py - dirty version"

[master 3906629] hello.py - dirty version
 1 file changed, 1 insertion(+)
 create mode 100644 hello.py
                                                                     
git push origin master 
                    
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 3 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 978 bytes | 978.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/tigo11/lab1.git
   56d620d..3906629  master -> master

```

Измените исходный код, что бы скрипт запрашивал имя пользователя и выводил Hello appsec world from @name
``` bash
                                                    
sudo nano hello.py
                                                                     
python3 hello.py  
Enter name: tigo
Hello appsec world from @tigo
                                                                     
git add hello.py
                                                                     
git commit -S -m "Improve hello.py - add username input"
[master f6f1a27] Improve hello.py - add username input
 1 file changed, 2 insertions(+), 1 deletion(-)
                                                                     
git push origin master
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 3 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.00 KiB | 1.00 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/tigo11/lab1.git
   3906629..f6f1a27  master -> master
```
Сделайте commit с флагом -S и сделайте публикацию в удаленный репозиторий. Проверьте вывод истории изменений
В локальном репозитории создайте ветку patch1 и внесите изменения исправлению кода и модернизации до следующего вида, что бы код был рабочим. Сделайте публикацию своего commit с флагом -S в удаленный репозиторий:
``` bash
git checkout -b patch1

Switched to a new branch 'patch1'
                                                                     
git branch

  master
* patch1

git add hello.py
                                                                     
git commit -S -m "Modernize hello.py (patch1)" 
[patch1 3da1881] Modernize hello.py (patch1)
 1 file changed, 17 insertions(+), 2 deletions(-)
                                                                     
git push -u origin patch1

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 3 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.26 KiB | 1.26 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/tigo11/lab1/pull/new/patch1
remote: 
To https://github.com/tigo11/lab1.git
 * [new branch]      patch1 -> patch1
branch 'patch1' set up to track 'origin/patch1'.
```
Доработайте материалы и также опишите их в отчете:

Проверьте, что ветка patch1 в удалённом репозитории
Создайте pull-request в виде patch1 -> master
В ветке patch1 добавьте в исходный код комментарии и убедитесь, что есть указанные изменения в pull-request
В удалённый репозитории выполните слияние pull-request для patch1 -> master и удалите ветку patch1
Стяните последние актуальные изменения и просмотрите историю изменений для master
Удалите локальную ветку patch1
``` bash
gh pr create --base master --head patch1

Creating pull request for patch1 into master in tigo11/lab1

? Title (required) Modernize hello.py (patch1)
? Body <Received>
? What's next? Submit
 https:github.com/tigo11/lab1/pull/1
```

``` bash
gh pr merge 1 --merge

✓ Merged pull request tigo11/lab1#1 (Modernize hello.py (patch1))
                                                                     
git push origin --delete patch1

To https://github.com/tigo11/lab1.git
 - [deleted]         patch1
                                                                     
git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
                                                                     
git pull
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (1/1), 902 bytes | 902.00 KiB/s, done.
From https://github.com/tigo11/lab1
   f6f1a27..0209e11  master     -> origin/master
Updating f6f1a27..0209e11
Fast-forward
 hello.py | 19 +++++++++++++++++--
 1 file changed, 17 insertions(+), 2 deletions(-)
                                                                     
git log --decorate --oneline -n 3

0209e11 (HEAD -> master, origin/master) Merge pull request #1 from tigo11/patch1
3da1881 (patch1) Modernize hello.py (patch1)
f6f1a27 Improve hello.py - add username input
                                                                     
git branch -d patch1

Deleted branch patch1 (was 3da1881).
                                                                     
git branch

* master
```

Создайте новую локальную ветку patch2.
Измените code style по своему усмотрению
Сделайте публикацию своего commit с флагом -S в удаленный репозиторий и создайте pull-request patch2 -> master

``` bash 
git checkout -b patch2

Switched to a new branch 'patch2'
                                                                     
git branch

  master
* patch2
                                                                     
sudo nano hello.py

[sudo] password for tigo: 
                                                                     
git add hello.py
                                                                     
git commit -S -m "patch2: restyle hello.py"
[patch2 1a48733] patch2: restyle hello.py
 1 file changed, 18 insertions(+), 2 deletions(-)
                                                                     
git push -u origin patch2

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 3 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.06 KiB | 1.06 MiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/tigo11/lab1/pull/new/patch2
remote: 
To https://github.com/tigo11/lab1.git
 * [new branch]      patch2 -> patch2
branch 'patch2' set up to track 'origin/patch2'.
                                                                     
gh pr create --base master --head patch2

Creating pull request for patch2 into master in tigo11/lab1

? Title (required) patch2: restyle hello.py
? Body <Received>
? What's next? Submit
https://github.com/tigo11/lab1/pull/2
```
В ветке master удаленного репозитория явно измените комментарий
Увидите, что в pull-request появились расхождения
Локально сделайте rebase и исправьте расхождения (это называется конфликт)
``` bash                                                                     
sudo nano hello.py                 
                                                                     
git add hello.py
                                                                     
git commit -S -m "patch2:conflict"  
[patch2 2253d3c] patch2:conflict
 1 file changed, 1 insertion(+), 1 deletion(-)
                                                                     
git rebase origin/master

Auto-merging hello.py
CONFLICT (content): Merge conflict in hello.py
error: could not apply 2253d3c... patch2:conflict
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".                                                                  
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".                                                   
hint: Disable this message with "git config advice.mergeConflict false"                                                                   
Could not apply 2253d3c... patch2:conflict
```
Сделайте commit и опубликуйте изменения в ветке patch2
Убедитесь, что пропали конфликтны.
``` bash
                                                                     
nano hello.py
                                                                 
git add hello.py

git rebase --continue

[detached HEAD e8c9706] patch2:conflict
 1 file changed, 1 insertion(+), 1 deletion(-)
Successfully rebased and updated refs/heads/patch2.
                                                                     
git push -f

Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 3 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 1.95 KiB | 1.95 MiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/tigo11/lab1.git
 + 1a48733...e8c9706 patch2 -> patch2 (forced update)
```                                                      
Сделайте merge для pull-request patch2 -> master.
``` bash                                                                     
gh pr merge 2 --merge

✓ Merged pull request tigo11/lab1#2 (patch2: restyle hello.py)
```
Подготовьте отчет gist.
Продемонстрируйте в материалах отчета историю коммитов на локальном и удаленном репозитории.

