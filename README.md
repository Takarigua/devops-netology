# Новая строка из ДЗ 2
# Новая строка из ДЗ 2




# Новая строка из ДЗ 2
# devops-netology


Домашнее задание к занятию «Системы контроля версий»


### Игнорируемые файлы

Благодаря `.gitignore` в каталоге `terraform/` будут игнорироваться:

1. **Локальные каталоги .terraform**  
   Правило: `**/.terraform/*`  
   Игнорирует: все каталоги `.terraform` в любых поддиректориях

2. **Файлы состояний Terraform**  
   Правила: `*.tfstate`, `*.tfstate.*`  
   Игнорирует: файлы с расширением `.tfstate` и производными

3. **Файлы логов**  
   Правила: `crash.log`, `crash.*.log`  
   Игнорирует: логи аварийных завершений

4. **Файлы переменных**  
   Правила: `*.tfvars`, `*.tfvars.json`  
   Игнорирует: файлы с переменными окружения

5. **Override-файлы**  
   Правила: `override.tf`, `override.tf.json`, `*_override.tf`, `*_override.tf.json`  
   Игнорирует: файлы переопределения конфигураций

6. **Файлы блокировок**  
   Правило: `.terraform.tfstate.lock.info`  
   Игнорирует: файлы блокировок состояния

7. **Конфигурационные файлы CLI**  
   Правила: `.terraformrc`, `terraform.rc`  
   Игнорирует: локальные настройки Terraform CLI


# Домашнее задание к занятию «Системы контроля версий»
## Задание 1. Создать и настроить репозиторий для дальнейшей работы на курсе

В рамках курса вы будете писать скрипты и создавать конфигурации для различных систем, которые необходимо сохранять для будущего использования. 
Сначала надо создать и настроить локальный репозиторий, после чего добавить удалённый репозиторий на GitHub.

### Создание репозитория и первого коммита

1. Зарегистрируйте аккаунт на [https://github.com/](https://github.com/). Если предпочитаете другое хранилище для репозитория, можно использовать его.
2. Создайте публичный репозиторий, который будете использовать дальше на протяжении всего курса, желательное с названием `devops-netology`.
   Обязательно поставьте галочку `Initialize this repository with a README`.
   3. Создайте [авторизационный токен](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) для клонирования репозитория.
4. Склонируйте репозиторий, используя протокол HTTPS (`git clone ...`).
5. Перейдите в каталог с клоном репозитория (`cd devops-netology`).
6. Произведите первоначальную настройку Git, указав своё настоящее имя, чтобы нам было проще общаться, и email (`git config --global user.name` и `git config --global user.email johndoe@example.com`). 
7. Выполните команду `git status` и запомните результат.
8. Отредактируйте файл `README.md` любым удобным способом, тем самым переведя файл в состояние `Modified`.
9. Ещё раз выполните `git status` и продолжайте проверять вывод этой команды после каждого следующего шага. 
10. Теперь посмотрите изменения в файле `README.md`, выполнив команды `git diff` и `git diff --staged`.
11. Переведите файл в состояние `staged` (или, как говорят, просто добавьте файл в коммит) командой `git add README.md`.
12. И ещё раз выполните команды `git diff` и `git diff --staged`. Поиграйте с изменениями и этими командами, чтобы чётко понять, что и когда они отображают. 
13. Теперь можно сделать коммит `git commit -m 'First commit'`.
14. И ещё раз посмотреть выводы команд `git status`, `git diff` и `git diff --staged`.
15. ### Создание файлов `.gitignore` и второго коммита

1. Создайте файл `.gitignore` (обратите внимание на точку в начале файла), проверьте его статус сразу после создания. 
1. Добавьте файл `.gitignore` в следующий коммит (`git add...`).
1. На одном из следующих блоков вы будете изучать `Terraform`, давайте сразу создадим соотвествующий каталог `terraform` и внутри этого каталога — файл `.gitignore` по примеру: https://github.com/github/gitignore/blob/master/Terraform.gitignore.  
1. В файле `README.md` опишите своими словами, какие файлы будут проигнорированы в будущем благодаря добавленному `.gitignore`.
1. Закоммитьте все новые и изменённые файлы. Комментарий к коммиту должен быть `Added gitignore`.

### Эксперимент с удалением и перемещением файлов (третий и четвёртый коммит)

1. Создайте файлы `will_be_deleted.txt` (с текстом `will_be_deleted`) и `will_be_moved.txt` (с текстом `will_be_moved`) и закоммите их с комментарием `Prepare to delete and move`.
1. В случае необходимости обратитесь к [официальной документации](https://git-scm.com/book/ru/v2/Основы-Git-Запись-изменений-в-репозиторий) — здесь подробно описано, как выполнить следующие шаги. 
1. Удалите файл `will_be_deleted.txt` с диска и из репозитория. 
1. Переименуйте (переместите) файл `will_be_moved.txt` на диске и в репозитории, чтобы он стал называться `has_been_moved.txt`.
1. Закоммитьте результат работы с комментарием `Moved and deleted`.

### Проверка изменения

1. В результате предыдущих шагов в репозитории должно быть как минимум пять коммитов (если вы сделали ещё промежуточные — нет проблем):
    * `Initial Commit` — созданный GitHub при инициализации репозитория. 
    * `First commit` — созданный после изменения файла `README.md`.
    * `Added gitignore` — после добавления `.gitignore`.
    * `Prepare to delete and move` — после добавления двух временных файлов.
    * `Moved and deleted` — после удаления и перемещения временных файлов. 
2. Проверьте это, используя комманду `git log`. Подробно о формате вывода этой команды мы поговорим на следующем занятии, но посмотреть, что она отображает, можно уже сейчас.

### Отправка изменений в репозиторий

Выполните команду `git push`, если Git запросит логин и пароль — введите ваши логин и пароль от GitHub. 

В качестве результата отправьте ссылку на репозиторий. 

### Скриншоты выполнения
![1](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/1.png)
![2](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/2.png)
![3](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/3.png)
![4](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/4.png)
![5](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/5.png)
![6](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/6.png)
![7](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/7.png)
![8](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/8.png)
![9](https://github.com/Takarigua/devops-netology/blob/f55b053cad4b50446e18ae17547593c006b77380/screen/9.png)
