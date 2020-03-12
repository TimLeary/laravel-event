###Step 1:
#####Install PHP components

* `docker-compose up`
* `docker-compose exec php composer install`
* Open browser `http://localhost:8080/`
* If necessary 
`chmod -R 777 src/l-event/storage/`

###Step 2:
#####Update
docker-compose.yml php environments with
```
environment:
  DB_DATABASE: laravel
  DB_USERNAME: root
  DB_PASSWORD: example
  DB_HOST: mysql
```
then run:
`docker-compose exec php php artisan migrate`
it creates `users` `migrations` `password_resets` and `failed_jobs`

#####Create registration
At `src/l-event`

`php composer.phar require laravel/ui ^1.0`

`php artisan ui --help`

`php artisan ui bootstrap --auth`

`npm install && npm run dev`