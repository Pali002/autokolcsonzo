# Car Rental

## Car rental fejlesztői dokumentáció

    A car rental, autó kölcsönzéssel foglalkozó cégek számára készült, autó nyilvántartás.
    Alkalmas autók adatainak tárolására, megtekintésére. Beleértve az autók megjelenítését, azonosítás után új autó felvételére, szerkesztésére, törlésére.

    Ez a dokumentáció az asztali alkalmazásról szól. Az asztali alkalmazás csak az autók megtekintésére, új autó felvételére, szerkesztésére, törlésére alkalmas, mindez azonosítás után történhet meg.

## Futtatási környezet

    A futtatáshoz szükség van a REST API szerver működéséhez. A REST API PHP alapú webszerveren futtatható.
    A REST API számára szükséges egy adatbázis szerver. A restapi hai-server-el lett tesztelve.

## Felépítés

### Könyvtárszerkezet

```txt
admin/
  |-.vscode/
  |-api/
  |-bin/
  |-lib/
  |-pictures/
  |-src/
  |  |-controllers/
  |  |  |-MainController/
  |  |-models/
  |  |  |-api/
  |  |  |  |-AuthService.java/
  |  |  |  |-ChechApi.java/
  |  |  |  |-HttpClient.java/
  |  |  |  |-Restapi.java/
  |  |  |  |-User.java/
  |  |  |-Car.java/
  |  |  |-Database.java/
  |  |  |-DataService.java/
  |  |  |-MariadbDatabase.java/
  |  |  |-Pro.java/
  |  |-views/
  |  |  |-login/
  |  |  |  |-IdandPass.java/
  |  |  |  |-LoginView.java/
  |  |  |-registry/
  |  |  |  |-RegistryView.java/
  |  |  |-InputPanel.java/
  |  |  |-MainTab.java/
  |  |  |-MainView.java/
  |  |  |-PassPanel.java/
  |  |  |-TitlePanel.java/
  |  |-App.java/
  |  |-config.properties/
  |-README.md/
```

### Osztályok

### App, MainController

    A feladatuk az alkalmazás indítás

### LoginView, IdandPass

    Feladata a bejelentkező felület megjelenítése, felhasználó azonosítása email és jelszó alapján (hozzá tartozik az IdandPass, amely a bejelentkezéshez szükséges, itt található a bejelentkezéshez szükséges információk). Az oldal bekéri a felhasználó adatait, a bejelentkezés gombot meg nyomva juthatunk tovább, sikeres hitelesítés után.
    
### MainTab

    Feladata a bejelentkező felület utáni ablak megjelenítése. Az ablakhoz tartozik a MainView fájl ez tölti fel adatokkal.
   
### MainView

    Feladata a táblázat megjelenítése, ahol az autók adatait tároljuk. Itt lehet szerkeszteni, ujjat felvenni és lehetőség van törölni is. A kiválasztott sorra kattintva, majd a törlés gombot meg nyomva végrahajtódik. A fájlban található a getCars() metódus mely betölti az adatokat a restapi-ból. Az ablakon megtalálható egy kilépés gomb, mely bezárja az alkalmazást.

#### MainView tartalma

    InitTable() - megjeleníti az autók táblázatát.
    A getCars() - beolvassa az adatokat a restapi-ból, innen kerülnek az adatok a táblázatba. 
    Buttons() - gombok hozzáadása a táblázat alá (mentés, törlés, kilépés), ezen belül a hozzáadás gombhoz meg írt bekérő panel is itt található, mely új ablakot jelenít meg.

### RegistryView

    A regisztrációs fül feladata új felhasználó felvétele, tartalmaz beviteli mezőket, amely bekéri az új felhasználó adatait.  (Fejlesztés alatt)
    
### InputPanel, TitlePanel, PassPanel

    Mindhárom fül a regisztrációs panel-ez tartozik. Feladata az igazítás és maga a mezők felvétele.
    
### DataService

    Feladata az adatbázisból való ki olvasás. Ezt egy while ciklus kezeli majd a getCars() metódusba írja őket.

### Car

    Feladata változók tárolása, kesőbb ezeket használja a MainView is például.

### Restapi

    Feladata az adatbázishoz való csatalkozás.

### HttpClient

    Feladata hibák megjelenítése a felhasználónak. Például a restapi sikertelen elérése esetén ki írja, hogy Hiba! A GET kérés sikertelen!
