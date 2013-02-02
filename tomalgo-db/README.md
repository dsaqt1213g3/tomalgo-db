 ---------------------------------------------------------------------------------------------------
|  -------------    -------     ----    ----     --------     ---          ----------     -------    |
| |             | /    _    \  |     \/     |  /    /\    \  |   |       /    _______|  /    _    \  |
|  ----     ---- |    / \    | |            | |    /  \    | |   |      |   /          |    / \    | |
|      |   |     |   |   |   | |    \  /    | |    \  /    | |   |      |   |    ----  |   |   |   | |
|      |   |     |    \_/    | |   | -- |   | |   | -- |   | |   -----  |   |___\    | |    \_/    | |
|      |   |      \         /  |   |    |   | |   |    |   | |        |  \          /   \         /  |
|      |___|        -------     ---      ---   ---      ---   --------     --------       -------    |
 ----------------------------------------------------------------------------------------------------


***Creaci�n del usuario***

Si es la primera vez que restauramos la base de datos desde un fichero de respaldo, tenemos que crear un usuario espec�fico para ella. Como usuario root de mysql tenemos que hacer lo siguiente:

mysql> grant usage on tomalgo.* to [usuario]@localhost identified by '[contrase�a]';
mysql> grant all privileges on tomalgo.* to [usuario]@localhost;

Donde [usuario] es el identificador para el nuevo usuario, [contrase�a] su contrase�a.

Si es la primera vez que hacemos el respaldo, tenemos que crear la base de datos de nombre tomalgo a la que otorgamos al [usuario] todos los privilegios.

Entramos a mysql con el usuario creado en el paso anterior:

$ mysql -u [usuario] -p
Enter password: [contrase�a]

y creamos la base de datos:

mysql> create database tomalgo;
mysql> exit;

Ahora restauraremos la base de datos desde uno de los dos ficheros de respaldo:

    tomalgo_data.sql - para recuperar la estructura de la base de datos con registros.

Desde la shell:

$ mysql -u [usuario] -p tomalgo < tomalgo_data.sql
Enter password: [contrase�a]
