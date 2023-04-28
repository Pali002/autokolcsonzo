# Car Rent

## Fejlesztői dokumentáció - Backend

## 2023

## Fejlesztői nézet

Lépjünk be a mappába:

```
cd backend
```

Most töltsük le a függőségeket, és futtassuk a migrációt:

```
composer install
php artisan key:generate
php artisan migrate:fresh
```

Végül indítsuk el a backendet:

```
php artisan serve
```

## Felépítés

### Könyvtárszerkezet

```txt
WebshopBackend/
|-app/
    |-Http/
        controllers/
            |-LoginController
            |-LogoutController
            |-RegisterController
    |-Models/
        |-User
|-bootstrap/
|-config/
|-database/
    |-factories/
    |-migrations/
        |-usersTable
        |-carsTable
        |-brandsTable
        |-gearsTable
    |-seeders/
|-public/
|-resources/
|-routes/
    |-api.php
|-storage/
|-tests/
|-vendor/
```

A létrehozott kontrollerek:

* LoginController - A bejelentkezésért felel
* LogoutController - A kijelentkezésért felel
* RegisterController - A regisztrációért felel

### LoginController

#### login()
```
A metódus feladata, hogy ellenőrizze és beléptesse a felhasználót. Bemenő paraméter egy Request objektum. Ha sikeres, a visszatérési érték az authenticated() metódus.
```

#### authenticated()
```
A metódus feladata, hogy az ellenőrzött, bejelentkezett felhasználót továbbvigye a céloldalra. Bemenő paraméter egy Request objektum és egy user változó. Visszatérési érték a redirect() metódus a céloldalra.
```

### LogoutController

#### logout()
```
A metódus célja, hogy a felhasználót kijelentkeztesse. Bemenő paraméter és visszatérési érték nincs.
```

### RegisterController

#### register()
```
A metódus célja, hogy felvegyen egy új felhasználót. Bemenő paraméter egy Request objektum. Visszatérési érték egy response() metódus, ami visszaadja, hogy sikerült-e a regisztráció.
```

Adattáblák kapcsolata:

* brands.id = cars.brandId
* gears.id = cars.gearId

### Útvonalak

* /register -> POST -> RegisterController@register
* /login -> POST -> LoginController@login
* /logout -> POST -> LogoutController@logout