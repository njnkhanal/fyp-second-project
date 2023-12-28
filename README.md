# Install laravel

-   _composer create-project laravel/laravel project_name_

# serve project

-   _php artisan serve_

# laravel authentication

-   first install laravel ui package (_composer require laravel/ui_)
-   use ui auth (_php artisan ui:auth_)
-   use bootstrap v5 cdn link in views > layouts > app.blade.php

# Database Connection

-   first create a database in localhost/phpmyadmin
-   replace the name of database in .env file (DB_DATABASE)
-   Migrate the tables to database (_php artisan migrate_)
-   to customize frontend of form pages will be stored in (views > auth) folder
