[<<< Előző](categorical.md) | [Következő >>>](correlation.md)

# Indexelés és Boolean adatok

Az előző részben megismerkedtünk a számláló adatok létrehozásával, mint az elemzés hasznos köztes lépésével. Előfordulhat, hogy az elemzett adathalmazban néha találkozunk számláló adatokkal. Például az Airbnb-adatkészletünkben van egy oszlop, a `calculated_host_listings_count`, amely megmutatja, hogy hány másik bérleményt tett közzé az egyes listák gazdája. Leggyakrabban azonban az adatkészlet más mezőiből származtatott számlálási adatokkal fog dolgozni, ahogyan mi is tettük a `neighbourhood_group` oszlop számlálásával.

Egy másik, az elemzés közbenső lépéseként gyakran használt adattípus a bináris adatok. Ezek az adatok azt mutatják, hogy valami igaz vagy hamis, más lehetőség nincs. A Pandasban az ilyen típusú adatok egy boolean értékeket (`igaz` és `hamis`) tartalmazó sorozat formájában jelennek meg.

## Boolean sorozat létrehozása

Tegyük fel, hogy elemezni akarjuk a rendkívül drága Airbnb-ajánlatokat, azokat, amelyek éjszakánként több mint 1000 dollárba kerülnek. Kezdjük egy boolean sorozat létrehozásával. A sorozat létrehozásához a Pandas megnézi az `ár` oszlopunkat, és ha az ár `1000` felett van, akkor az új sorozat értékét `igaz`-ra állítja. Ha az ár `1000` alatt van, akkor az értéket `False`-re állítja. 

Próbálja ki a következőket:

```python
price_bools = df.price > 1000
```

Az eredmény, amelyet most az `price_bools`-hez rendelünk, egy olyan sorozat lesz, amely csak az `igaz` és a `Hamis` értékeket tartalmazza. Minden egyes "igaz" érték az "ár" oszlop olyan helyének felel meg, ahol az ár nagyobb, mint "1000".

A boolean-sorozat önmagában csak némileg hasznos. Megpróbálhatjuk az `value_counts()` módszer segítségével kideríteni, hogy hány `igaz` és `hamis` érték van a sorozatban:

```python
price_bools.value_counts()
```

Az eredmény azt mutatja, hogy csak 239 lista van 1000 dollár feletti éjszakánként.

A boolean sorozatoknál hasznos trükk, ha a `mean()` módszerrel megkérdezzük az átlagot. Ez megmondja, hogy a sorozatban az elemek mekkora hányada "igaz".

```python
price_bools.mean()
```

Ebben az esetben az arány `0,0048`, ami azt jelzi, hogy a listáknak csak körülbelül fél százaléka haladja meg az 1000 dollárt éjszakánként.

## Adatok részhalmazának létrehozása

A boolean-sorozat igazi ereje abban rejlik, hogy segítségével létrehozhatjuk az adatkeretünk egy részhalmazát, amely csak azokat az értékeket tartalmazza, amelyekre a tételünk igaz. Esetünkben létrehozhatunk egy új adathalmazt, amely csak azokat a listákat tartalmazza, amelyeknél az éjszakánkénti ár nagyobb, mint 1000 dollár.

Futtassa a következőt:

```python
expensive_df = df[price_bools]
```

Ezzel létrehoztunk egy új adatkeretet, amelyet az `expensive_df`-hez rendeltünk. Ellenőrizzük, hány sor van ebben az új adatkeretben:

```python
len(expensive_df)
```

Ez az új adatkeret mindössze 239 sort tartalmaz. Az ebben az új adatkészletben szereplő listák mindegyike 1000 dollár feletti éjszakai árral rendelkezik.

Most már használhatjuk ezt a származtatott adathalmazt új kérdések megválaszolásához. Például, melyik környéken van a legtöbb olyan Airbnb-ajánlat, amelynek éjszakánkénti ára meghaladja az 1000 dollárt?

```python
expensive_df.neighbourhood.value_counts().head()
```

Ebből kiderül, hogy a három környék, ahol a legtöbb 1000 dollár feletti szoba található, az Upper West Side, a Midtown és a West Village.

## Kategorikus részhalmaz

Az adataink fent létrehozott részhalmaza numerikus adatok (az ár) alapján tett különbséget. Próbáljunk meg egy új részhalmazt létrehozni egy kategorikus adatokat tartalmazó oszlop alapján.

New Yorkban élek a Woodside környékém. Tudjuk meg, hogy mennyi az átlagos és a medián Airbnb-ár a környékemen.

Először hozzunk létre egy boolean sorozatot. Egy elem akkor lesz `igaz`, ha megfelel a `szomszédság_csoport` oszlop olyan elemének, amelynek értéke `Woodside`.

```python
woodside_bools = df.neighbourhood == 'Woodside'
```

Ha már megvan a boolean sorozat, azonnal használjuk fel az eredeti adatkeret egy részhalmazának létrehozására:

```python
woodside_df = df[woodside_bools]
```

Most már használhatjuk az új Woodside-adatkészletet, hogy ellenőrizzük egy Airbnb-szoba átlagos és medián árát Woodside-ban:

```python
woodside_df.price.mean()
```

```python
woodside_df.price.median()
```

Woodside városában egy éjszaka medián ára 60 $ (vagy volt). Elég jó üzletnek tűnik.

[<<< Előző](categorical.md) | [Következő >>>](correlation.md)
