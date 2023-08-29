# git-04-tools-hw - «Инструменты Git» - Дрибноход Давид

### Цель задания

В результате выполнения задания вы:

* научитесь работать с утилитами Git;
* потренируетесь решать типовые задачи, возникающие при работе в команде. 

### Инструкция к заданию

1. Склонируйте [репозиторий](https://github.com/hashicorp/terraform) с исходным кодом Terraform.
2. Создайте файл для ответов на задания в своём репозитории, после выполнения прикрепите ссылку на .md-файл с ответами в личном кабинете.
3. Любые вопросы по решению задач задавайте в чате учебной группы.

------

## Задание

В клонированном репозитории:

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.
Ответ: Используя команду git show aefea получаю информацию о полном хеше и комментарии в коммите
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/19bc1f4c-c547-49d3-bd4b-3d9d5417e358)
Полный хеш коммита aefead2207ef7e2aa5dc81a34aedf0cad4c32545, а комментарий к коммиту указан "Update CHANGELOG.md".

Команда git show отображает подробные данные коммита. Также информацию о хеше и коммите можно было получить используя команду git log aefea.
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/0d03c2d6-813a-4b38-83af-75df4f312b2b)

2. Ответьте на вопросы.

* Какому тегу соответствует коммит `85024d3`?
Ответ: тегу v0.12.23
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/60eb5935-9cea-491d-b6a2-e123a232e565)

* Сколько родителей у коммита `b8d720`? Напишите их хеши.
Ответ: Используя команду git log b8d720 --oneline --graph вижу что это merge commit и у него есть два родителя
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/86a55aab-db01-454d-bd37-647509f613ba)
Первый родитель - 56cd7859e05c36c06b56d013b55a252d0bb7e158

Второй родитель - 9ea88f22fc6269854151c571162c5bcf958bee2b

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами  v0.12.23 и v0.12.24.
Ответ: данные получаем командой git log v0.12.23..v0.12.24 --oneline

всего 9 коммитов

b14b74c493 [Website] vmc provider links

3f235065b9 Update CHANGELOG.md

6ae64e247b registry: Fix panic when server is unreachable

5c619ca1ba website: Remove links to the getting started guide's old location

06275647e2 Update CHANGELOG.md

d5f9411f51 command: Fix bug when using terraform login on Windows

4b6d06cc5d Update CHANGELOG.md

dd01a35078 Update CHANGELOG.md

225466bc3e Cleanup after v0.12.23 release
 
* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).
Ответ: данные получу командой git log -S "func providerSource(" --oneline
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/08e28028-2261-4b6b-8a7f-c44d5b37822c)

* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.
Ответ: Командой git grep -p "globalPluginDirs" найду что функция определена в файле plugins.go
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/8da53e8d-dfcc-4d26-99a6-9c78a81defbd)

командой git log -s -L :globalPluginDirs:plugins.go --oneline найду что имзенения в нее вносились в  5 коммитах 
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/621cfdc2-2ca6-47e3-94a9-955cfbeb6ed4)

* Кто автор функции `synchronizedWriters`?
Ответ: командой git log -S "synchronizedWriters" получим все коммиты с упоминанием данной функции, самый ранний коммит 5ac311e2a91e381e2f52234668b49ba670aa0fe5 автором которого является Martin Atkins <mart@degeneration.co.uk> 
![image](https://github.com/DrDavidN/git-04-tools-hw/assets/128225763/e0890598-af33-49a3-babf-3c2a2860be90)

*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*

---
