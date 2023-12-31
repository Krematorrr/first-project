# Шпаргалка

## 1.Шпаргалка markdown

### Выделение текста

Вы можете выделять текст в markdown с помощью символов `_` или `*`. Например:

Пример _курсива_ и **жирного** текста.

### Заголовки

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок. Например:

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня

### Выделение кода

Чтобы выделить текст как код, поместите его в тройные кавычки `````. 

```
mkdir my_project
cd my_project
git init
```
Это лишь некоторые функции markdown.

## 2. Шпаргалка хеширование, логи, HEAD, статусы, оформление сообщений к коммитам

### Хэширование

Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.
Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.
Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке *.git*.

### Лог

После вызова _git log_ появляется список коммитов.
Можно вызвать не только полный лог, но и сокращённый — это делается командой _git log --oneline_.
В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

### HEAD

В числе прочих файлов в папке .git есть служебный файл HEAD. Он указывает на самый свежий коммит.
Вместо хеша последнего коммита можно написать слово HEAD — Git вас поймёт.

### Статусы файлов

Статусом _untracked_ помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. Этот статус — противоположность _tracked_, в который попадают все файлы, отслеживаемые Git.
Файл переходит в статус _staged_ после выполнения _git add_.
Статус _modified_ означает, что файл был изменён.
Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.

#### Схема статусов файлов

```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "???"     --> tracked/comitted;

%% стрелка без текста для примера: 
  A --> B;
```


### Оформление сообщений к коммитам
Правильно описывать коммиты — искусство, к которому стоит приобщиться как можно раньше. Хорошо, когда:
сообщение коммита легко читается;
оно информативное;
все сообщения оформлены в одном стиле.