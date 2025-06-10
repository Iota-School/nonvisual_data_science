[<<<< El�z�](../README.md) | [K�vetkez� >>>](series.md)

# Dimenzi�k az adatokban

K�pzelj�k el, hogy van egy list�nk:

```python
[10, 5, 8]
```

Ez egy lista h�rom elemmel (10, 5 �s 8). Elk�pzel�s�nkben ezeket egy balr�l jobbra halad� vonal pontjaik�nt k�pzelhetj�k el. A 10-es sz�m lehet balra, a 2-es sz�m k�z�pen, a 3-as sz�m pedig jobbra.

Ezt nevezz�k egydimenzi�s adatnak. Az egydimenzi�s adat olyan sorozat vagy lista, amely nem tartalmaz m�s sorozatokat vagy list�kat. A sorozaton bel�li hely egyetlen sz�mmal fejezhet� ki.

 Pythonban a 0 a 10, az 1 az 5, a 2 pedig a 8 hely�t �rn� le, mivel a sz�mol�st 0-t�l kezdj�k. Amikor sz�mokat haszn�lunk a helyek le�r�s�ra, ezeket a sz�mokat "indexnek" nevezz�k. 

## K�tdimenzi�s adatok

K�pzelj�k el, hogy van egy �j list�nk:

```python
[
    ['January', 'February', 'March'],
    [10, 5, 8]
]
```

A fentiekben l�trehozunk egy list�t, amely maga is k�t list�t tartalmaz. A k�t lista mindegyike h�rom elemet tartalmaz.

Ez k�tdimenzi�s adat. Ahhoz, hogy le�rjuk egy elem hely�t a k�t lista egyik�ben, most k�t sz�mra van sz�ks�g�nk. Az els� megmondja, hogy az elem melyik list�ban van. A m�sodik megadja az elem hely�t a list�n bel�l. 

Ha ezt a k�t list�t t�rbelileg gondoljuk el, akkor mindk�t list�t egy-egy vonalon balr�l jobbra, az egyes list�kon szerepl� elemeket pedig egy-egy vonalon fel�lr�l lefel� helyezhetj�k el. Ha az adatok egy s�k lenn�nek, akkor az egyes list�kat az X tengelyen, a list�kon bel�li egyes elemeket pedig az Y tengelyen helyezhetn�nk el. 

Ha haszn�lt m�r kor�bban t�bl�zatkezel� szoftvert, akkor az egyes list�kat egy t�bl�zat oszlopak�nt k�pzelheti el. Ez azt jelenti, hogy ha a fenti adatokat t�bl�zatt� alak�tan�nk, akkor k�t oszlopa �s h�rom sora lenne. Az oszlopok balr�l jobbra haladnak (X tengely), a sorok pedig fentr�l lefel� (Y tengely).

## Egy�b dimenzi�k

L�trehozhatunk olyan adatokat, amelyek k�t dimenzi�n�l t�bb dimenzi�ban l�teznek. Ha a fenti lista minden egyes elem�t (azaz 10, 5 �s 8, valamint janu�r, febru�r, m�rcius) tov�bbi list�kkal helyettes�ten�nk, h�romdimenzi�s adatokat hozn�nk l�tre. Ebben az esetben az elemeknek az eml�tett list�kon bel�li hely�t h�rom sz�mmal (X, Y �s Z) kellene le�rni. Ezt az elvet tov�bb folytathatjuk, �s tetsz�leges sz�m� dimenzi�j� adatokat hozhatunk l�tre. Ebben az oktat�anyagban nem fogunk ilyen adatokkal dolgozni, de ezt N-dimenzi�s adatoknak (tetsz�leges sz�m� dimenzi�ban l�v� adatok) nevezz�k, �s az ilyen t�pus� adatoknak sz�mos alkalmaz�si ter�lete van.

Technikailag minden olyan adat, amely nem lista vagy sorozat, a nulla dimenzi�s adatok p�ld�ja. Ez azt jelenti, hogy nincs sz�ks�g sz�mokra a t�rbeli elhelyezked�s�nek a le�r�s�hoz. 
B�r folyamatosan haszn�lunk nulla dimenzi�s adatokat, nem sok sz�ks�g van arra, hogy �gy �rjuk le �ket.

[<<< El�z�](../README.md) | [K�vetkez� >>>](series.md)
