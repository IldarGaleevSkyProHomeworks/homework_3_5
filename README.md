## Задание 1

``` powershell
# создаем и заходим в папку проекта
cd (mkdir project1)

# создаем виртуальное окружение
python -m venv venv

# активируем окружение
.\venv\Scripts\activate

# путь к исполняемому файлу pip
gcm pip

# список установленных пакетов
pip list
```

![img1](images/img1.png)

## Задание 2

``` powershell
# устанавливаем необходимые пакеты
pip install django pytz requests

# записываем список пакетов в файл "requirements.txt"
pip freeze > requirements.txt

# выходим из окружения
deactivate
```

![img2](images/img2.png)

## Задание 3

``` powershell
# создаем и заходим в папку проекта
cd (mkdir ..\project2)

# создаем виртуальное окружение
python -m venv venv

# активируем окружение
.\venv\Scripts\activate

# копируем файл "requirements.txt" из предыдущего проекта в текущую папку
cp ..\project1\requirements.txt .

# устанавливаем пакеты из списка "requirements.txt"
pip install -r .\requirements.txt
```

![img3](images/img3.png)

## Задание 4

``` powershell
# создаем новый проект в Poetry
poetry new project3
cd .\project3\

# устанавливаем необходимые пакеты при помощи Poetry
poetry add pytz requests django==4.1
```

![img4](images/img4.png)

``` powershell
# дерево установленных пакетов
poetry show --tree

# удаление "requests" из зависимостей
poetry remove requests

# обновленное дерево зависимостей
poetry show --tree

# проверка наличия обновлений для пакетов
poetry show --latest
```

![img5](images/img5.png)

``` powershell
# установка "pytest" в группу зависимостей "dev"
poetry add -G dev pytest
```

![img6](images/img6.png)

## Задание 5

``` powershell
# создаем файл скрипта в VSCode
code -n .\project3\cli.py
```

![img7](images/img7.png)

Добавляем функцию к скриптам `Poetry`

``` ini
[tool.poetry.scripts]
say-welcome = 'project3.cli:welcome'
```


![img8](images/img8.png)

``` powershell
# устанавливаем скрипт
poetry install

# запускаем скрипт
poetry run say-welcome
```

![img9](images/img9.png)

``` powershell
# то же из оболочки Poetry
poetry shell
say-welcome
```

![img10](images/img10.png)