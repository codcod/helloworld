# HelloWorld

Pierwsze kroki z Py.

## Instalacja

1. [Python](https://www.python.org/ftp/python/3.7.3/python-3.7.3-amd64.exe)
1. [VSCode](https://vscode-update.azurewebsites.net/latest/win32-x64-user/stable) lub [Mu](https://codewith.mu/en/download).
1. [SQLiteBrowser](https://sqlitebrowser.org/dl/).


## �rodowisko

    C:\> mkdir %USERPROFILE%\PROJECTS
    C:\> subst r: %USERPROFILE%\PROJECTS       % po przelogowaniu trzeba
                                               % powt�rzy� to polecenie
    C:\> R:
    R:\> mkdir helloworld
    R:\> cd helloworld
    R:\helloworld> python -m venv venv         % utworzenie wirtualnego
                                               % �rodowiska o nazwie venv
    R:\helloworld> venv\Scripts\activate.bat   % aktywacja witualnego
                                               % �rodowiska
    (venv) R:\helloworld> python -m pip install --upgrade pip  % aktualizacja
                                               % narz�dzia do instalowania
                                               % bibliotek
    (venv) R:\helloworld> pip install ipython  % instalacja lepszego shella ni�
                                               % zwyk�y python
    (venv) R:\helloworld> ipython              % uruchomienie lepszego shella,
                                               % Ctrl+D to wyj�cie

### Uwagi do �rodowiska

Wirtualne �rodowisko zak�ada si� raz, uruchamia si� wiele razy (skryptem
`activate.bat`). Wyj�cie to polecenie `deactivate` lub po prostu zamkni�cie
wiersza polece�. Wirtualne �rodowisko pozwala instalowa� niezale�nie wiele
r�nych bibliotek. Mo�na mie� (i z regu�y si� ma) wiele r�nych �rodowisk
wirtualnych.

IPython (trzeba instalowa� niezale�nie w ka�dym �rodowisku wirtualnym). Pomaga
na start, bo ma uzupe�nianie sk�adni i trwa�� histori�.

## Ciekawsze biblioteki na start

* `pandas`
* `matplotlib`
* `pendulum`
* `virtualenv`, `virtualenvwrapper` (uzupe�nienie �rodowiska wirtualnego)
* `flake8`, `rope`, `pylint` (do pracy z samym kodem)

## Zaczytywanie danych z CSV

Dane z XLS zapisz jako "CSV UTF-8 (comma separated)". I nast�pnie:

    (venv) R:\helloworld> sqlite3 stage.sqlite3
    sqlite> .sep ;
    sqlite> .import test_data.csv STAGE
    sqlite> .q
    (venv) R:\helloworld> python db_import.py

