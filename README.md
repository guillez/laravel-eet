#1 - Bajar repositorio

git clone https://github.com/guillez/laravel-eet.git

#2 - Acceder a la carpeta

cd laravel-eet

#3 - Configurar archivo .env 

cp .env.exameple .env

mcedit .env

APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:okZmFqjib4W0V6zJyT/aqsE/+rIkDJhMZtkLQ54Glw8=
APP_DEBUG=true
APP_URL=http://localhost:8000

LOG_CHANNEL=stack
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=clave


Si no existe copiar el archivo .env.example y configurar parametros

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

#9 - COnfiguro login de laravel

docker exec app composer require laravel/ui

docker exec app php artisan ui:auth

docker exec app php artisan migrate




