# MySQL Database - scuola

questo progetto contine ei files per inizializzare il Container con il DB "scuola" da usare con il codice Back-end.

## Come avviarlo

#### 1 - Creare Volume

Al fine di creare persistenza del dato, e' necessario creare un volume:

````docker volume create scuola-db-data````

#### 2 - Avviare il container

Per creare il container esegui il comando all'interno della directory del progetto (e' possibile personalizzare il valore dei parametri):

````docker run -d --name scuola-db -v scuola-db-data:/var/lib/mysql -v "${PWD}/initdb:/docker-entrypoint-initdb.d" -e MYSQL_ROOT_PASSWORD=1234test -e MYSQL_DATABASE=scuola -e MYSQL_USER=myuser -e MYSQL_PASSWORD=123test  -p 3306:3306  mysql:8.0````

## Comandi di gestione

Per accedere a mysql mediante client:

````docker exec -it scuola-db mysql -u root -p````


