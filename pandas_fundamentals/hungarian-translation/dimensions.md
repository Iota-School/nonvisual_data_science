[<<<< Elõzõ](../README.md) | [Következõ >>>](series.md)

# Dimenziók az adatokban

Képzeljük el, hogy van egy listánk:

```python
[10, 5, 8]
```

Ez egy lista három elemmel (10, 5 és 8). Elképzelésünkben ezeket egy balról jobbra haladó vonal pontjaiként képzelhetjük el. A 10-es szám lehet balra, a 2-es szám középen, a 3-as szám pedig jobbra.

Ezt nevezzük egydimenziós adatnak. Az egydimenziós adat olyan sorozat vagy lista, amely nem tartalmaz más sorozatokat vagy listákat. A sorozaton belüli hely egyetlen számmal fejezhetõ ki.

 Pythonban a 0 a 10, az 1 az 5, a 2 pedig a 8 helyét írná le, mivel a számolást 0-tól kezdjük. Amikor számokat használunk a helyek leírására, ezeket a számokat "indexnek" nevezzük. 

## Kétdimenziós adatok

Képzeljük el, hogy van egy új listánk:

```python
[
    ['January', 'February', 'March'],
    [10, 5, 8]
]
```

A fentiekben létrehozunk egy listát, amely maga is két listát tartalmaz. A két lista mindegyike három elemet tartalmaz.

Ez kétdimenziós adat. Ahhoz, hogy leírjuk egy elem helyét a két lista egyikében, most két számra van szükségünk. Az elsõ megmondja, hogy az elem melyik listában van. A második megadja az elem helyét a listán belül. 

Ha ezt a két listát térbelileg gondoljuk el, akkor mindkét listát egy-egy vonalon balról jobbra, az egyes listákon szereplõ elemeket pedig egy-egy vonalon felülrõl lefelé helyezhetjük el. Ha az adatok egy sík lennének, akkor az egyes listákat az X tengelyen, a listákon belüli egyes elemeket pedig az Y tengelyen helyezhetnénk el. 

Ha használt már korábban táblázatkezelõ szoftvert, akkor az egyes listákat egy táblázat oszlopaként képzelheti el. Ez azt jelenti, hogy ha a fenti adatokat táblázattá alakítanánk, akkor két oszlopa és három sora lenne. Az oszlopok balról jobbra haladnak (X tengely), a sorok pedig fentrõl lefelé (Y tengely).

## Egyéb dimenziók

Létrehozhatunk olyan adatokat, amelyek két dimenziónál több dimenzióban léteznek. Ha a fenti lista minden egyes elemét (azaz 10, 5 és 8, valamint január, február, március) további listákkal helyettesítenénk, háromdimenziós adatokat hoznánk létre. Ebben az esetben az elemeknek az említett listákon belüli helyét három számmal (X, Y és Z) kellene leírni. Ezt az elvet tovább folytathatjuk, és tetszõleges számú dimenziójú adatokat hozhatunk létre. Ebben az oktatóanyagban nem fogunk ilyen adatokkal dolgozni, de ezt N-dimenziós adatoknak (tetszõleges számú dimenzióban lévõ adatok) nevezzük, és az ilyen típusú adatoknak számos alkalmazási területe van.

Technikailag minden olyan adat, amely nem lista vagy sorozat, a nulla dimenziós adatok példája. Ez azt jelenti, hogy nincs szükség számokra a térbeli elhelyezkedésének a leírásához. 
Bár folyamatosan használunk nulla dimenziós adatokat, nem sok szükség van arra, hogy így írjuk le õket.

[<<< Elõzõ](../README.md) | [Következõ >>>](series.md)
