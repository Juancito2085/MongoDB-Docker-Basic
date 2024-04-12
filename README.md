# MongoDB-Docker-Basic

CREANDO UN CONTENEDOR

<h3>Instalar Mongo:</h3> 
En la línea de comando.
____________________________________________________________
Paso 1. Crear documento de docker-compose.

Opción 1.

> Usar docker compose, visual estudio code, instalando la extensión de docker.

Opción 2.

> touch docker-compose.yml
> cat > docker-compose.yml
_____________________________________________
Paso 2. Crear documento de docker-compose.yml:

version: '2.2'

services:

  mongo:
    image: mongo:4.0.4
    restart: always
    container_name: monguito
    environment:
      - MONGODB_USER="user"
      - MONGODB_PASS="pass"	
      
    volumes:
      - ./monguitodata:/data/db
      - ./monguitodata/log:/var/log/mongodb/
    ports:
      - "27017:27017"
    
____________________________________________________________
paso 3. Crear archivos para correr comando en la la terminal:

> touch mongo.sh
__________________________________________
Paso 4. Cargar comandos al archivo creado:

> cat > mongo.sh   	(Copiar y pegar los comandos que queremos se ejecuten automáticos)

#Crear carpeta para volumen de mongo:
mkdir monguitodata && cd monguitodata; cd monguitodata || mkdir log

cd

#Iniciar el contenedor:
sudo docker-compose up -d

#Mostrar mensaje:
echo "Monguito está iniciandose ......."

#entrar en el contenedor
sudo docker exec -it monguito bash

_______
Paso 5.

> Control + d
_________________________________________________________
Paso 6. Asignar permisos de ejecución y ejecutar mongo.sh
> chmod u+x mongo.sh
> ./mongo.sh 
_______
Paso 7. 

USAR MONGO A PLACER.
