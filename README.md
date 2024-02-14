1. TERMINAL -> docker compose up -d nginx
2. TERMINAL -> docker compose run --rm -it composer install
3. TERMINAL -> docker exec -it php-container php artisan migrate --seed || docker exec -it php-container bash // php artisan command...

4. NGINX:

   - image: NGINX:latest
   - config: ./tmp/configs/nginx/nginx.conf
   - port: 80

5. PHP:

   - image: ./dockerfiles/php - PHP:8.2-fpm

6. Composer:

   - build: ./dockerfiles/composer - Composer:latest

7. MySQL:

   - image: MySQL:latest
   - user: root
   - password: root
   - port: 3306
   - env: ./mysql.env

8. Redis:

   - image: Redis:latest
   - port: 6379

9. PhpMyAdmin:
   - image: Redis:latest
   - port: 8080
   - env: ./phpmyadmin.env
