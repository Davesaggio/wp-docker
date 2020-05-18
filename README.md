

# Entrare dentro la cartella proxy con il terminale

Runnare comando:
    docker network create proxy

Runnare comando:
    docker-compose up -d
( Questo serve per avviare il container ngnix e poter fare i proxy )    

# Poi entrare dentro la cartella principale del sito
    Runnare comando:
    docker-compose up -d

( Partirà l’installazione di worpdress, creazione del db, configurazione del wp-config e collegamento del proxy )

Il file docker-compose dentro proxy non serve modificarlo.

Nel file dockercompose della root del progetto ci sono tutte le configurazioni, potrete dare il nome del db, l’utente mysql   e la password, ora è tutto impostato con Wordpress come nome pass ecc..

Le due networks che troverete nel file servono per far comunicare mysql, Wordpress e ngnix

phpmyadmin.php inserirlo nella cartella pubblic che verrà creata dopo aver avviato l'ultimo container, serve per accedere al db.

Dopo aver installato tutto, 
aggiungere l'host:

comando da terminale mac: 
sudo nano /private/etc/hosts

aprire docker-compose.yml all'interno della cartella del sito e inserire ip e host che avete inserito scelto, inserlo nella varibile VIRTUAL_HOST: wideo-docker.local
127.0.0.1 wideo-docker.local