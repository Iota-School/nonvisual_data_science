[<<< Elõzõ](objects.md) | [Következõ >>>](magic.md)

# Egy kis motiváció

A mûhelymunkánk végéhez közeledünk. Hogy inspiráljon benneteket a sorozat következõ részére, hozzunk létre egy egyszerû alkalmazást, amely egy kis motivációt nyújt, amikor szükségetek van rá.

Elõször is létrehozunk egy üres listát, és feltöltjük néhány motiváló (vagy vicces) idézettel. Ezután egy véletlenszerûséget használunk, hogy kiválasszon nekünk egy idézetet a listából. Ahhoz, hogy ezt a véletlenszerûséget használhassuk, megismerkedünk a könyvtárak importálásával, ami vitathatatlanul a Python legerõsebb funkciója.

## Adataink létrehozása

Kezdetnek hozzunk létre egy üres listát, és rendeljük hozzá a `motivational_quotes` változóhoz. (Ez a `motivational` és az `quotes` szavakat jelenti, egy aláhúzással elválasztva).
Magyar fordítása: motivációs idézetek

```python
motivational_quotes = []
```

Ez a `motivational_quotes` változó neve, egy szóköz, egy egyenlõségjel, egy szóköz, egy nyitó szögletes zárójel és egy záró szögletes zárójel.


Most már van egy üres listánk, készen arra, hogy idézetekkel töltsük meg. 
Használjuk az `append` metódusunkat, hogy néhány idézetet adjunk a listához: (Ne feledjük, hogy a tabulátor billentyûvel kitölthetjük a hosszú változónevünket).

```python
motivational_quotes .append("Azt hiszem, kezdek belejönni ebbe a Python dologba.")
```

Ez már egy idézet. Adjunk hozzá még kettõt-hármat:

```python
motivational_quotes .append("Imádom a szintaktikai hibákat. Jöhet a kihívás!")
```

```python
motivational_quotes .append("Bogarakat eszem reggelire. De nem ilyeneket.")
```

```python
motivational_quotes .append("Nézd, anya, a parancssort használom!")
```

Bármilyen idézõjelet használhatsz, csak ne feledd, hogy dupla idézõjellel kezdd és fejezd be, ne aposztróffal (szimpla idézõjel).

Nézzük meg a listánkat úgy, hogy a REPL-be önmagában beírjuk a `motivational_quotes` változó nevû változót. Vissza kell kapnunk egy listát az általunk hozzáadott idézetekkel.

```python
Out[6]: 
["Azt hiszem, kezdek belejönni ebbe a Python dologba.",
 'Imádom a szintaktikai hibákat. jöhet a kihívás!',
'Bogarakat eszem reggelire. De nem ilyeneket.'
 "Nézd, anya, a parancssort használom!"]]
```

## Könyvtár importálása

Minden, amit eddig ebben a workshopban csináltunk, a Python nyelv beépített funkcióit használta. Ahhoz azonban, hogy véletlenszerûen válasszunk egy idézetet a listánkból, szükségünk lesz egy speciálisabb függvényre a `random` könyvtárból. Adjuk hozzá ezt a függvényt a programunkhoz, majd elmagyarázzuk, hogy mik azok a könyvtárak, és hogyan használjuk õket Pythonban.

Elõször is importáljuk a `random` könyvtárat.

```python
import random
```
Ezzel létrehozunk egy új objektumot, amely elérhetõ számunkra a REPL-ben. Próbáljuk meg beírni a `random`-t önmagában, és megtudjuk, hogy ez egy `random` nevû modul.

Használjunk egy függvényt a `random` könyvtárból, hogy kiválasszunk egy véletlenszerû idézetet a listánkból:

```python
random.choice(motivational_quotes)
```

Meghallgatunk egy idézetet a listánkból. Nyomjuk meg a fel gombot, hogy kitöltsük ugyanazt a sort, majd nyomjuk meg az `Enter` billentyût, és minden alkalommal más idézetet fogunk hallani.

## Mi az a könyvtár?

A könyvtár olyan függvények és egyéb objektumok tárolója, amelyeket könnyen be lehet húzni a saját Python programjaidba. A könyvtárakat általában egy adott célra hozzák létre: vannak könyvtárak weboldalak letöltésére, matematikai munkára, bizonyos fájltípusokkal való munkára és szinte minden másra, ami csak eszedbe jut. A könyvtár általános kifejezés az importálásra szánt kódra, a Python-specifikus kifejezés a modul.

A Python egy szabványos könyvtárral rendelkezik, amely számos gyakori feladatra tartalmaz modulokat. Ezen kívül az általunk használt Anaconda disztribúció számos könyvtárat tartalmaz az adattudományhoz kapcsolódó feladatokhoz.

Az olyan függvények, mint a `help` és a `dir` az importált könyvtárakkal mûködnek, bár érdemes lehet utánanézni a könyvtár saját dokumentációjában vagy valamilyen más oktatóprogramban, hogy megtudjuk, hogyan használjunk egy adott könyvtárat.

[<<< Elõzõ](objects.md) | [Következõ >>>](magic.md)
