# Хеширование персональных данных в таблице Excel

В данном репозитории лежит [Jupyter-ноутбук](hash_customers.ipynb), в котором описан процесс хеширования персональных данных покупателей, чтобы их можно было передать третьей стороне без раскрытия исходных данных.

## Запуск

Склонируйте репозиторий, установите зависимости в виртуальное окружение и запустите сервер Jupyter.

### Инструкции

Если у вас уже установлен Python, и вы работали с pip, переходите к [командам для запуска](#pip).

Если вы не знаете, что такое pip, не знаете, как им пользоваться, ни разу не устанавливали Python, или у вас Windows, советую использовать [miniconda](#conda).

#### pip

```
git clone https://github.com/gorskii/excel-hashing-notebook.git
cd excel-hashing-notebook
python -m venv venv
source venv/bin/activate
python -m pip install -U pip
pip install -r requirements.txt
jupyter notebook
```

#### conda

Загрузите и установите [miniconda](https://docs.conda.io/en/latest/miniconda.html) — это удобный компактный дистрибутив [Anaconda](https://www.anaconda.com/), включающий в себя [conda](https://conda.io), Python и немного дополнительных утилит. conda — это просто менеджер пакетов. С его помощью можно устанавливать и удалять библиотеки, вроде [pandas](https://pandas.pydata.org/) или [jupyter](https://jupyter.org/). Инструкции для старта доступны [по ссылке](https://docs.conda.io/projects/continuumio-conda/en/latest/user-guide/getting-started.html#before-you-start).

Создайте [виртуальное окружение](https://docs.conda.io/projects/continuumio-conda/en/latest/user-guide/getting-started.html#managing-environments) с именем `hashing` и установите пакеты `pandas`, `notebook`, `openpyxl`:
```
conda create --name hashing pandas notebook openpyxl
```

Это то же самое, что сначала создать виртуальное окружение командой `conda create`, активировать его командой и затем установить нужные пакеты командой `conda install`:
```
conda create --name hashing
conda activate hashing
conda install pandas notebook openpyxl
```

Посмотреть список существующих виртуальных окружений:
```
conda info --envs
```

Соответственно, для повторного запуска не нужно заново всё устанавливать.

Нужно запустить с ярлыка командную оболочку Anaconda, склонировать репозиторий с ноутбуком, перейти в каталог с ноутбуком, активировать виртуальное окружение, запустить сервер Jupyter:
```
git clone https://github.com/gorskii/excel-hashing-notebook.git
cd excel-hashing-notebook
conda activate hashing
jupyter notebook
```
В открывшемся окне браузера запустите файл `hash_customers.ipynb`.

Можно экспериментировать с ноутбуком и даже стать дата-сайентистом, если разобраться и увлечься!

## Ссылки

Документацию по установке и работе с Jupyter можно найти [здесь](https://jupyter.org/index.html) в соответствующих разделах.

[Туториал](https://pandas.pydata.org/pandas-docs/stable/getting_started/index.html) по Pandas. [Взгляд](https://pandas.pydata.org/pandas-docs/stable/getting_started/comparison/comparison_with_spreadsheets.html#compare-with-spreadsheets) с точки зрения пользователя Excel.

[Ссылка](https://yuthakarn.medium.com/hashing-sha512-on-pandas-dataframe-more-effectively-d5e906272095) на исходную статью о хешировании, код из которой был использован.

[hashlib](https://docs.python.org/3/library/hashlib.html) — набор инструментов для хэширования из стандартной библиотеки Python.

[openpyxl](https://openpyxl.readthedocs.io/en/stable/) — библиотека, с помощью которой pandas может работать с Excel-файлами.
