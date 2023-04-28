# Car Rent

## Felhasználói dokumentáció - Backend

## 2023

A backend kéréseket fogad, és ezek alapján hajt végre feladatokat. Felelős a bejelentkezés, kijelentkezés, regisztráció múködéséért.

## Végpontok

### /register

Ezen a végpontok végződik a regisztráció a beírt adatok alapján. Miután regisztráltunk bejelentkezhetünk az oldalra.

### /login

Ezen a végponton végződik a bejelentkezés. Amennyiben a beírt adatok helyesek, és léteznek az adatbázisban, sikeres a bejelentkezés, és elérhetővé válnak az oldal fő funkciói pl. vásárlás.

### /logout

Ezen a végponton végződik a kijelentkezés. Gombnyomásra működik, lenyomás után a kijelentkezés megtörténik, elvesztjük a jogosultságot az oldal funkcióinak használatára.