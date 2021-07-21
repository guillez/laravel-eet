#1 - Bajar repositorio

git clone https://github.com/guillez/laravel-eet.git

#2 - Dar permisos y Acceder a la carpeta
chmod 777 laravel-eet -R
cd laravel-eet

#3 - Configurar archivo .env 

cp .env.exameple .env

mcedit .env

(Los parametros minimos a modificar son:)

-APP_URL=http://localhost:8000

-DB_HOST=mysql

-DB_PASSWORD=clave

#4 - Generar imagen requerida por el contenedor

docker-compose build app

#5 - construccion de contenedores

docker-compose up -d

#6 - Instalar las dependencias requeridas por laravel

docker exec app composer install

#7 - generar una key 

docker exec app php artisan key:generate

#8 - Armar la estructura inicial de la base de laravel

docker exec app php artisan migrate

Luego probar con un navegador el acceso, el sistema mediante el nginx-proxy se encuentra en puerto 80 
por lo que al instalar en forma local es http://localhost






