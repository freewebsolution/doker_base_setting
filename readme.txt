ESEGUIRE MYSQL SU DOCKER

 -- docker run -it --rm --network=docker_my-network mysql:8 mysql -h docker-mysql-1 -u root -p

LISTA CONTAINER

 -- docker ps

LISTA DEI NETWORKS

 -- docker network ls

 CAMBIA LA PASSWORD DA MYSQL

 Accedi a MySQL con la password corrente:

 -- mysql -u root -p

Verrà richiesta la password corrente, inseriscila.

Cambia la password:

Una volta dentro la console MySQL, puoi eseguire il comando SQL per cambiare la password:


 -- ALTER USER 'root'@'localhost' IDENTIFIED BY 'nuova_password';

Sostituisci nuova_password con la nuova password desiderata.

Se vuoi consentire l'accesso a root da qualsiasi host (non solo da localhost), puoi usare '%' al posto di 'localhost':

 -- ALTER USER 'root'@'%' IDENTIFIED BY 'nuova_password';
Ricarica i privilegi:

Dopo aver cambiato la password, assicurati di ricaricare i privilegi per applicare le modifiche:

 -- FLUSH PRIVILEGES;

Ora, dovresti essere in grado di accedere a MySQL utilizzando la nuova password.

Ricorda che se hai una password vuota e desideri mantenerla vuota, dovrai eseguire l'ALTER USER senza specificare la nuova password:

 -- ALTER USER 'root'@'localhost' IDENTIFIED BY '';
o per consentire l'accesso da qualsiasi host:

 -- ALTER USER 'root'@'%' IDENTIFIED BY '';
Assicurati di sostituire nuova_password con la tua nuova password o lasciala vuota se vuoi rimuoverla.