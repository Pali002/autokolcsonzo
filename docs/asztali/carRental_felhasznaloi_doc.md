# Car rental (autókölcsönző) admin felület

## Fejlesztői dokumentáció

Alkalmazás autók kezelésére. Új autók felvétele és módosítására van lehetőség, ezenfelül törölni is lehet ezeket.

## Üzembe helyezés

* futnia kell a restapi szervernek, csak ez esetben töltenek be az autók (npm start)
* le kell töltenünk a függőségeket,
ha megvannak adjuk hozzá a függőségeket
(Java projects => Referenced Libraries):
* függőségek:  
    gson-2.10.1.jar,
    junit-jupiter-api-5.9.1.jar,
    junit-platform-console-standalone-1.9.1.jar,
    javafx-sdk-20 :
        javafx.base.jar
        javafx.controls.jar
        javafx.fxml.jar
        javafx.graphics.jar
        javafx.media.jar
        javafx.properties
        javafx.swing.jar
        javafx.web.jar
        javafx-swt.jar

## Használat

Login:

    Bejelentkezés, Az admi kap egy személyre szabott felhasználó nevet és jelszót amivel be tud
    jelentkezni, csak ezek után tud müveletek végrehejtani.

Main:

    A main fülön található a táblázat, itt találhatóak az autók adatai.
    A táblázat valamely cellájába duplán kattintva szerkeszthetőek az adatok.
    A hozzáadás gomb megnyomása esetén, ój ablak jelenik meg, itt új autót tudunk felvenni.
    Törlés gomb, kitörli a kiválasztott autót a táblázatból.
    Kilépés gomb megnyomása esetén a program le áll.

Registy:

    Fejlesztés alatt ál, későbbiekben lehetőségünk lesz új admin felhasználó felvételére.
