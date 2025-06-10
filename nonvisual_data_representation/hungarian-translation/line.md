[<<< Előző](line.md) | [Következő >>>](../README.md)

# Időbeli változások

Ebben a műhelyben már sok mindent megbeszéltünk. Befejezésül hozzuk össze a tanult technikák egy részét egy viszonylag nagy kihívás megvalósításához: egy változó időbeli változásának követése nem vizuálisan.

## Időoszlop létrehozása

Az adatkészletünk egyik oszlopa, az `last_review' azt jelzi, hogy mikor tették közzé a legutóbbi értékelést egy listáról. Nyomon követjük az egyes években utoljára felülvizsgált listák számát, 2011-től kezdődően.

Először is nézzük meg a last_review-oszlopot:

```python
df.last_review.head()
```

Vegyük észre, hogy az oszlop dtype (Pandas adattípusa) `object`. Ez azt jelenti, hogy a Pandas nem tudta automatikusan felismerni az oszlopban lévő adatok típusát. Hozzunk létre egy új sorozatot, ahol az adatainkat dátumként ismerjük fel:

```python
dates = pandas.to_datetime(df.last_review)
```

Most már van egy olyan sorozatunk, amely a `dates` változóhoz van rendelve, amelyet helyesen időadatként ismer fel. Ezen a sorozaton belül használhatunk egy speciális attribútumot, a `dt`-t, amely lehetővé teszi számunkra, hogy más, dátummal és idővel kapcsolatos módszereket és attribútumokat érjünk el. Használjuk most ezt a funkcionalitást, hogy kivonjuk az egyes listák évszámát:

```python
years = dates.dt.year
```

Számoljuk meg, hogy az egyes években hány listát vizsgáltak meg utoljára:

```python
years.value_counts()
```

Az így kapott sorozatból megtudhatjuk, hogy hány listát vizsgáltak meg utoljára az adott évben. Mivel ebben az oszlopban a későbbi értékelések felülírják a régebbi értékeléseket, feltételezhetjük, hogy nagy a torzítás az utóbbi évek irányában. Az adatok azonban arra utalnak, hogy az Airbnb népszerűsége a 2011 és 2019 közötti időszakban nőtt.

## Vonaldiagramok cseréje

A vonaldiagramokat általában valamilyen rendezett numerikus adat változásának megjelenítésére használják. A vonaldiagramokban használt rendezett numerikus adatok leggyakoribb fajtái az idők és a gyakoriságok. A fenti megközelítés használható az időbeli változást ábrázoló kimenet létrehozására, és így bizonyos körülmények között helyettesítheti a vonaldiagramot. Ahogyan a kategorikus adatok vizsgálatakor tettük, a `pct_change()` módszert is használhatjuk, hogy jobban érzékeltessük az adatok emelkedéseit és csökkenéseit:

```python
 years.value_counts().sort_index().pct_change()
 ```

Az itt látható kimenet azt mutatja meg, hogy az egyes évek listázási számai hogyan változtak az idők folyamán. 2012-ben a "last_review"-ok száma 250%-kal nőtt az előző évhez képest. 2018-ban a szám 88%-kal nőtt az előző évhez képest.

[<<< Előző](line.md) | [Következő >>>](../README.md)
