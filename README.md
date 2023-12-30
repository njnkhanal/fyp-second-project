# Install laravel

-   _composer create-project laravel/laravel project_name_

# serve project

-   _php artisan serve_

# laravel authentication

-   first install laravel ui package (_composer require laravel/ui_)
-   use ui auth (_php artisan ui:auth_)
-   use bootstrap v5 cdn link in resources > views > layouts > app.blade.php

# Database Connection

-   first create a database in localhost/phpmyadmin
-   replace the name of database in .env file (DB_DATABASE)
-   Migrate the tables to database (_php artisan migrate_)
-   to customize frontend of form pages will be stored in (views > auth) folder

# Role Management

-   add new role column in user table (_$table->enum('role', ['admin','seller','user'])->default('user');_)
-   rollback the migration (_php artisan migrate:rollback_) and migrate again (_php artisan migrate_)
    (option: _php artisan migrate:refresh_)
-   create new controller for admin dashboar (_php artisan make:controller AdminController_)

# Admin Route

-   create new group for admin (_Route::prefix('admin')->middleware('auth')->group(function () {_)
    -   middleware is a condition before opening the url listed in that group
-   create new route under admin group for dashboard page (_Route::get('dashboard', [AdminController::class,'dashboard'])->name('admin.dashboard');_)
    -   name is use to naming the route
    -   url become (_127.0.0.1:8000/admin/dashboard_)

# Create Middleware For Admin

-   create new middleare as AdminMiddleware (_php artisan make:middleware AdminMiddleware_)
-   make condition to check the role of user if logged in
-   register that middlware to the kernel file in $routeMiddleware (_'admin' => \App\Http\Middleware\AdminMiddleware::class,_)
-   use that admin middleware in route group of admin
