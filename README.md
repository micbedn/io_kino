# URUCHOMIENIE

1. pobierz docker oraz zainstaluj sterownik ODBC Driver 17 for SQL Server


2. pobierz obraz msql server:

```
    sudo docker pull mcr.microsoft.com/mssql/server:2019-latest
```


3. uruchamiamy za kazdym razem po starcie dockera:

    Jeśli uzywasz Windows: w pliku ``` bd_connection.py ``` trzeba odkomentować połączenie dla Windows

```
    docker run -e "ACCEPT_EULA=Y" --platform linux/amd64 -e "SA_PASSWORD=citqus-viVcy6-najcyq" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2019-latest
```


4. uruchom srodowisko wirtualne:

```
    python3 -m venv name_of_virtualenv
```


5. uaktywnij srodowisko wirualne:

    LINUX  : ``` source name_of_virtualenv/bin/activate ```

    WINDOWS: ``` source name_of_virtualenv/Scripts/activate ```


6. zainstaluj wszystkie niezbedne zaleznosci:

```
    pip3 install -r requirements.txt
```


7. wystartuj skrypt uruchamiajacy aplikacje oraz dodajacy funkcje i tabele do bazy danych:

```
    chmod +x start.sh
    ./start.sh
```


8. po zakonczeniu pracy zamknij proces aplikacji przez ^C oraz dezaktyowój srodowisko wirtualne:

```
    deactivate
```



___
# HELP

Żeby sprawdzić co robi interesująca funkcja, trzeba zaimportowac modul w ktorym sie znajduje oraz wywolac funkcję help, np.:

```
    python3
    import app.wyswietl_filmy
    help(main)
```

