[<<< El�z�](conditionals.md) | [K�vetkez� >>>](motivation.md)

# betekint�s az objektumokba

Ebben a m�helyben eddig �t adatt�pust haszn�ltunk: eg�sz sz�mokat, lebeg� sz�mokat, karakterl�ncokat, boolean-okat �s list�kat. 
�szrevett�k, hogy vannak dolgok, amelyeket egyes objektumokkal megtehet�nk, m�sokkal viszont nem. P�ld�ul a `len` f�ggv�nyt haszn�ltuk egy lista hossz�nak ellen�rz�s�re. A `len` f�ggv�nyt stringeken is haszn�lhatjuk, ami megmondja, hogy h�ny karakter van a stringben. Amikor azonban a `len` f�ggv�nyt eg�sz sz�mra haszn�ljuk, hib�t kapunk:

```python
len(5)
```

Ez a k�vetkez� hibakimenetet adja vissza:

```
TypeError: az 'int' t�pus� objektumnak nincs len()
```

Pythonban minden egy objektum. Azt, hogy mit tehet�nk egy adott objektummal, r�szben az objektum t�pusa hat�rozza meg. Bizonyos dolgokat megtehetsz list�kkal, amiket eg�sz sz�mokkal nem, �s bizonyos dolgokat megtehetsz eg�sz sz�mokkal, amiket stringekkel nem. A t�pusok lehet�v� teszik, hogy az adatokat egy adott kateg�ri�ba soroljuk, �gy intuit�vabban tudunk vel�k dolgozni, eg�sz �s lebeg� sz�mokkal matematik�t v�gezni, list�kb�l elemeket hozz�adni vagy elt�vol�tani, �s �gy tov�bb.

Az objektumokr�l �gy is gondolkodhatunk, hogy kont�nerek. Ezekben a kont�nerekben tal�lunk f�ggv�nyeket, amelyek az adott objektumra hatnak, �s v�ltoz�kat, amelyek az objektummal kapcsolatos adatokat tartalmazz�k. Mivel a programoz�sban szeretj�k, ha a dolgoknak speci�lis kifejez�sei vannak, az objektumokon bel�l tal�lhat� f�ggv�nyeknek �s v�ltoz�knak saj�t nev�k van:

- A **Methods** - az objektumokon bel�l tal�lhat� f�ggv�nyek.
- Az *Attributes*  az objektumokban tal�lhat� egy�b adatok.

## Objektum-m�dszerek haszn�lata
(Object Methods)

Eml�kszel a kor�bban haszn�lt vir�glist�nkra? Ha �jraind�tottad azIPython munkamenetet, a k�vetkez�kkel �jra l�trehozhatod:

```python
vir�gok = ['r�zsa', 'ibolya', 'bogl�rka']
```

Mi van akkor, ha szeretn�nk egy �jabb elemet hozz�adni a `vir�gok` list�nkhoz? �rjuk be ezt a k�dsort:

```python
vir�gok.append("margar�ta")
```

Ez a `vir�gok`, egy pont, `append`, egy nyit� z�r�jel, egy id�z�jel, `margar�ta`, egy id�z�jel �s egy z�r�jel.

A `vir�gok` list�j�nak v�ltoz�s�t a `vir�gok` be�r�s�val �s az `Enter` le�t�s�vel ellen�rizheted. A k�vetkez� kimenetet kell kapnod:

```python
['r�zsa', 'ibolya', 'bogl�rka', 'margar�ta']
```

A margar�ta hozz� lett adva, vagy hozz� lett csatolva a lista v�g�hez.

Mit csin�ltunk itt? A `vir�gok` listaobjektumban tal�lhat� `append` m�dszert haszn�ltuk. Ez a m�dszer egy adatot kap, a list�hoz hozz�adand� objektumot, amelyet z�r�jelben helyez�nk el. A f�ggv�nynek vagy m�dszernek �tadott adatokat "argumentumnak" nevezz�k.

## Inform�ci�szerz�s objektumokr�l

A Pythonban m�r ismer�nk n�h�ny m�dszert arra, hogy inform�ci�t szerezz�nk egy objektumr�l.

1. Egy v�ltoz� nev�t �nmag�ban is be�rhatjuk a REPL-be, hogy megkapjuk az adott objektum reprezent�ci�j�t. Ha p�ld�ul a REPL-be be�rjuk a `vir�gok` sz�t, megtudjuk, hogy milyen adatokat tartalmaz a lista.
2. A `type` f�ggv�nnyel megtudhatjuk egy objektum adatt�pus�t. �gy megtudhatjuk, hogy eg�sz sz�m, lista, boolean, karakterl�nc vagy valamilyen m�s adatt�pusr�l van-e sz�.
3. Bizonyos objektumok eset�ben a `len` f�ggv�nnyel megtudhatjuk, hogy mennyi adatot tartalmaz. List�k eset�ben ez megadja a lista elemeinek sz�m�t, stringek eset�ben pedig a stringben l�v� karakterek sz�m�t.

Ezenk�v�l haszn�lhatjuk ezeket a tov�bbi hasznos f�ggv�nyeket is:

Ha �ltal�nos inform�ci�kat szeretn�nk kapni egy objektumr�l, haszn�lhatjuk a `help` f�ggv�nyt. Pr�b�ld ki ezt:

```python
help(vir�gok)
```

Ez ad n�mi inform�ci�t az adatt�pusr�l, bele�rtve azt is, hogy milyen m�dszerek �s attrib�tumok vannak defini�lva az objektumhoz. Egyel�re legink�bb az al�h�z�ssal k�r�lvett m�dszereket �rdemes figyelmen k�v�l hagyni.

Egy m�sik f�ggv�nyt, a `dir`-t is haszn�lhatjuk, hogy csak az objektumban l�v� m�dszerek �s attrib�tumok neveinek list�j�t kapjuk meg. 

```python
dir(vir�gok)
```

Mindk�t f�ggv�ny kimenete  a meg�rt�st tekintve el�gg� megterhel� lehet. Amikor  egy adatt�pusra keres�nk egy keres�motor seg�ts�g�vel, annak Gyakran t�bb �rtelmez�se lehet. 
De �gy megtal�lod a leggyakrabban haszn�lt m�dszerek �s attrib�tumok list�j�t, vagy �j m�dszereket �s attrib�tumokat fedezel fel, mik�zben oktat�programokat tanulm�nyozol, vagy egy adott feladat elv�gz�s�nek m�dj�t keresed.

## Gyakran ism�telt k�rd�s: Melyek az al�h�z�ssal jel�lt m�dszerek?

Ebben a r�szben azt mondtam, hogy az al�h�z�ssal jel�lt m�dszereket �rdemes figyelmen k�v�l hagyni, mivel nem val�sz�n�, hogy k�zvetlen�l haszn�lni fogod �ket. Ha nem fogjuk haszn�lni �ket, akkor mi�rt vannak ott?

Ezek speci�lis, gyakran "m�gikus m�dszereknek" nevezett m�dszerek, amelyek lehet�v� teszik a nyelv m�s funkci�inak m�k�d�s�t. P�ld�ul a m�gikus m�dszerek teszik lehet�v�, hogy eg�sz sz�mokat adjunk �ssze �s vonjunk ki plusz �s m�nusz seg�ts�g�vel. B�r a k�zvetlen munka ezekkel a m�dszerekkel hasznos a saj�t Python-interf�szek l�trehoz�s�hoz, egyel�re �rdemes ezeket figyelmen k�v�l hagyni.

[<<< El�z�](conditionals.md) | [K�vetkez� >>>](motivation.md)
