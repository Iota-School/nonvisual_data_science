[<<< Elõzõ](conditionals.md) | [Következõ >>>](motivation.md)

# betekintés az objektumokba

Ebben a mûhelyben eddig öt adattípust használtunk: egész számokat, lebegõ számokat, karakterláncokat, boolean-okat és listákat. 
Észrevettük, hogy vannak dolgok, amelyeket egyes objektumokkal megtehetünk, másokkal viszont nem. Például a `len` függvényt használtuk egy lista hosszának ellenõrzésére. A `len` függvényt stringeken is használhatjuk, ami megmondja, hogy hány karakter van a stringben. Amikor azonban a `len` függvényt egész számra használjuk, hibát kapunk:

```python
len(5)
```

Ez a következõ hibakimenetet adja vissza:

```
TypeError: az 'int' típusú objektumnak nincs len()
```

Pythonban minden egy objektum. Azt, hogy mit tehetünk egy adott objektummal, részben az objektum típusa határozza meg. Bizonyos dolgokat megtehetsz listákkal, amiket egész számokkal nem, és bizonyos dolgokat megtehetsz egész számokkal, amiket stringekkel nem. A típusok lehetõvé teszik, hogy az adatokat egy adott kategóriába soroljuk, így intuitívabban tudunk velük dolgozni, egész és lebegõ számokkal matematikát végezni, listákból elemeket hozzáadni vagy eltávolítani, és így tovább.

Az objektumokról úgy is gondolkodhatunk, hogy konténerek. Ezekben a konténerekben találunk függvényeket, amelyek az adott objektumra hatnak, és változókat, amelyek az objektummal kapcsolatos adatokat tartalmazzák. Mivel a programozásban szeretjük, ha a dolgoknak speciális kifejezései vannak, az objektumokon belül található függvényeknek és változóknak saját nevük van:

- A **Methods** - az objektumokon belül található függvények.
- Az *Attributes*  az objektumokban található egyéb adatok.

## Objektum-módszerek használata
(Object Methods)

Emlékszel a korábban használt viráglistánkra? Ha újraindítottad azIPython munkamenetet, a következõkkel újra létrehozhatod:

```python
virágok = ['rózsa', 'ibolya', 'boglárka']
```

Mi van akkor, ha szeretnénk egy újabb elemet hozzáadni a `virágok` listánkhoz? Írjuk be ezt a kódsort:

```python
virágok.append("margaréta")
```

Ez a `virágok`, egy pont, `append`, egy nyitó zárójel, egy idézõjel, `margaréta`, egy idézõjel és egy zárójel.

A `virágok` listájának változását a `virágok` beírásával és az `Enter` leütésével ellenõrizheted. A következõ kimenetet kell kapnod:

```python
['rózsa', 'ibolya', 'boglárka', 'margaréta']
```

A margaréta hozzá lett adva, vagy hozzá lett csatolva a lista végéhez.

Mit csináltunk itt? A `virágok` listaobjektumban található `append` módszert használtuk. Ez a módszer egy adatot kap, a listához hozzáadandó objektumot, amelyet zárójelben helyezünk el. A függvénynek vagy módszernek átadott adatokat "argumentumnak" nevezzük.

## Információszerzés objektumokról

A Pythonban már ismerünk néhány módszert arra, hogy információt szerezzünk egy objektumról.

1. Egy változó nevét önmagában is beírhatjuk a REPL-be, hogy megkapjuk az adott objektum reprezentációját. Ha például a REPL-be beírjuk a `virágok` szót, megtudjuk, hogy milyen adatokat tartalmaz a lista.
2. A `type` függvénnyel megtudhatjuk egy objektum adattípusát. Így megtudhatjuk, hogy egész szám, lista, boolean, karakterlánc vagy valamilyen más adattípusról van-e szó.
3. Bizonyos objektumok esetében a `len` függvénnyel megtudhatjuk, hogy mennyi adatot tartalmaz. Listák esetében ez megadja a lista elemeinek számát, stringek esetében pedig a stringben lévõ karakterek számát.

Ezenkívül használhatjuk ezeket a további hasznos függvényeket is:

Ha általános információkat szeretnénk kapni egy objektumról, használhatjuk a `help` függvényt. Próbáld ki ezt:

```python
help(virágok)
```

Ez ad némi információt az adattípusról, beleértve azt is, hogy milyen módszerek és attribútumok vannak definiálva az objektumhoz. Egyelõre leginkább az aláhúzással körülvett módszereket érdemes figyelmen kívül hagyni.

Egy másik függvényt, a `dir`-t is használhatjuk, hogy csak az objektumban lévõ módszerek és attribútumok neveinek listáját kapjuk meg. 

```python
dir(virágok)
```

Mindkét függvény kimenete  a megértést tekintve eléggé megterhelõ lehet. Amikor  egy adattípusra keresünk egy keresõmotor segítségével, annak Gyakran több értelmezése lehet. 
De így megtalálod a leggyakrabban használt módszerek és attribútumok listáját, vagy új módszereket és attribútumokat fedezel fel, miközben oktatóprogramokat tanulmányozol, vagy egy adott feladat elvégzésének módját keresed.

## Gyakran ismételt kérdés: Melyek az aláhúzással jelölt módszerek?

Ebben a részben azt mondtam, hogy az aláhúzással jelölt módszereket érdemes figyelmen kívül hagyni, mivel nem valószínû, hogy közvetlenül használni fogod õket. Ha nem fogjuk használni õket, akkor miért vannak ott?

Ezek speciális, gyakran "mágikus módszereknek" nevezett módszerek, amelyek lehetõvé teszik a nyelv más funkcióinak mûködését. Például a mágikus módszerek teszik lehetõvé, hogy egész számokat adjunk össze és vonjunk ki plusz és mínusz segítségével. Bár a közvetlen munka ezekkel a módszerekkel hasznos a saját Python-interfészek létrehozásához, egyelõre érdemes ezeket figyelmen kívül hagyni.

[<<< Elõzõ](conditionals.md) | [Következõ >>>](motivation.md)
