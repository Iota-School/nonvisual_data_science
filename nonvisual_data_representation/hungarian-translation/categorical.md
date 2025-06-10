[<<< Előző](representing_data.md) | [Következő >>>](indexing.md)
# Kategorikus adatok feltárása

A kategorikus adatokat gyakran ábrázolják vizuálisan egy oszlop- vagy kördiagram segítségével. Azonban Pandas-sorozatban is könnyen összefoglalhatók. Ebben a szakaszban megismerkedünk a Pandasban található megközelítésekkel, amelyek segítségével kategorikus adatokat vizsgálhatunk.

A workshop hátralévő részében az Airbnb-adatkészletünket fogjuk használni. Az adathalmazt a következő paranccsal olvashatja be a Pandasba:

```python
df = pandas.read_csv('https://bit.ly/nycbnb')
```

A fenti parancs futtatása után az Airbnb-adatkészletünk az `df` változóhoz lesz rendelve.

## Mi az a kategorikus adat?

Próbáljuk meg kevésbé absztrakt módon elmagyarázni a kategorikus adatokat az adathalmazunkkal dolgozva. Először is vegyük ki az első öt elemet a `szomszédság_csoport` oszlopból az Airbnb-adatainkat tartalmazó adatkeretből:

```python
df.neighbourhood_group.head()
```

Ne feledjük, hogy a `head`()` az adatkeret vagy adatsor első elemeit mutatja meg, alapértelmezés szerint ötöt.

Az első öt elem a következő:

```
0 Brooklyn
1 Manhattan
2 Manhattan
3 Brooklyn
4 Manhattan
```

Vegyük észre, hogy a Brooklyn és a Manhattan is ismétlődik. Ez a kategorikus adatok jellegzetes tulajdonsága. Minden entitás (az adatkeret egy sora) egy korlátozott számú kategória egyikébe tartozik.

Használjunk egy új függvényt, hogy megnézzük, hány egyedi kategória van a `szomszédság_csoportban`:

```python
set(df.neighbourhood_group)
```

Ez egy listaszerű objektumot (egy halmazt) ad vissza öt elemmel: Bronx', 'Brooklyn', 'Manhattan', 'Queens', 'Staten Island'}`. A set függvény egy listában, szekvenciában vagy más listaszerű objektumban lévő egyedi értékeket jelenít meg. Ebben az esetben öt egyedi értékünk van, amelyek mindegyike azt a kerületet jelöli, ahol az adott Airbnb-ajánlat található.

## Számok

A kategorikus adatokon végzett hasznos művelet az egyes egyedi értékek előfordulásának megszámlálása. Például az `value_counts()` módszer segítségével megszámolhatjuk, hogy az egyes városrészek milyen gyakran szerepelnek a `neighbourhood_group` oszlopban:

```python
df.neighbourhood_group.value_counts()
```

A kimenet a következő:

```
Manhattan 21661
Brooklyn 20104
Queens 5666
Bronx 1091
Staten Island 373
Név: count, dtype: int64
```

A kimenetünk egy új sorozat. A sorozat indexe az oszlopban lévő egyedi értékek alapján címkék. A sorozat értékei egész számok, amelyek felsorolják, hogy az egyes kategóriák hányszor szerepelnek az oszlopban. Ez a sorozat azt mutatja, hogy Manhattanben több Airbnb-ajánlat van, mint Brooklynban, Brooklynban több ajánlat van, mint Queensben, és így tovább.

## Az oszlopdiagram cseréje

Nem vizuális szempontból ez a kimenet tisztességesen helyettesíti az oszlopdiagramot. Minden sor egy kategóriából és az adott kategória előfordulási számából áll az eredeti sorozatban. Ha egy látó adattudós által készített oszlopdiagram szöveges ábrázolását hoznánk létre, megfontolhatnánk egy ehhez hasonló formátum használatát.

Az egyik lehetséges előnye egy látó személynek, aki egy oszlop- vagy kördiagramot néz, az lenne, hogy gyorsan megérthetné az egyes számok egymáshoz viszonyított arányait. Például az oszlopdiagram vagy kördiagram gyorsan megmutatná, hogy Manhattan és Brooklyn értékei meglehetősen hasonlóak (21661 vs. 20104), és hogy Brooklyn és Queens között nagy a visszaesés (20104 vs. 5666). Bár ez valójában viszonylag egyértelmű a fentiekben létrehozott számlálási sorozatokból, az elemzésünket továbbfejlesztve még közvetlenebb képet kaphatunk a különböző arányokról.

## Számadataink finomítása

Hozzunk létre néhány azonnal érthetőbb kimenetet a `szomszédság_csoport` számlálásainkból. Először is rendeljük hozzá az előző számlálási sorozatunkat egy változóhoz:

```python
neighbourhood_counts = df.neighbourhood_group.value_counts()
```

Most használjuk a counts sorozatot, hogy megkapjuk az egyes értékek arányát tizedesjegyben:

```python
neighbourhood_counts / len(df)
```

A fentiekben a `len(df)` az eredeti adatállományunkban szereplő listák teljes száma (`48895`). Ezzel a számmal elosztjuk a sorozat minden egyes értékét. Például Manhattan esetében a `21661` értéket elosztjuk a `48895` értékkel. Így kapjuk a `0,443011` értéket, ami azt mutatja, hogy a hirdetések 44%-a Manhattanben található. 

Az új kimenetünket áttekintve a számok közötti összefüggések még világosabbak. Például `0,411167`, azaz a listák 41%-a Brooklynban található, de csak `0,115881`, azaz a listák 12%-a Queensben.

Ez lehet a legérthetőbb kimenet az arányok megértéséhez. A Pandas azonban más módszereket is kínál, amelyek még pontosabb információt adnak. Például használhatjuk a `pct_change()` módszert a `neighbourhood_counts` sorozatunkon, hogy minden egyes értéket százalékos változásként kapjunk meg az előzőhöz képest:

```python
neighbourhood_counts.pct_change()
```

Ebben a kimenetben az első érték (Manhattan) a `NaN`, azaz nincs adat feliratú. A második érték, Brooklyn esetében, `-0,071880`. Ez azt mutatja, hogy a brooklyni számok körülbelül 7%-kal alacsonyabbak, mint a manhattani számok. A következő, Queensre vonatkozó érték `-0,807448`, ami jelentős, 80%-os csökkenést mutat Brooklyn és Queens között.

## Összegzés

A fentiekben egy kis számú Pandas-módszert használtunk arra, hogy kategorikus adatok számolásakor gyorsan kiderítsük az arányokat. Ez viszonylag erőteljes helyettesítésére szolgál az oszlop- és kördiagramoknak, amikor nem vizuálisan dolgozunk adatokkal. A vizualizációban az oszlop- és kördiagramok akkor a legjobbak, ha korlátozott számú elemet mutatnak, így a kimeneteink soronkénti áttekintésével történő elemzése nem lényegesen lassabb, mint a vizuális átvizsgálás, különösen, ha meggyőződünk az olyan származtatott adatokról, mint a tizedes arányok és a százalékos változás.

## GYIK

### Hogyan készíthetek oszlopdiagramot látó kollégáim számára?

Először is, használjuk a `plot.bar` módszert a `neighbourhood_counts` változónkon, hogy létrehozzuk az oszlopdiagramot az Ipythonban. Ezután importáljuk a Pyplotot, amivel elmenthetjük a diagramot. Végül a Pyplot `savefig` metódusával mentsük el a diagramot. Az alábbi háromsoros szekvencia egy `output.png` nevű fájlba fog menteni az otthoni könyvtárunkba. Előbb a `neighbourhood_counts` változót kell hozzárendelnünk a fentiek szerint.

```python
neighbourhood_counts.plot.bar()
import matplotlib.pyplot as plt
plt.savefig('output.png')
```

### Van gyorsabb módja az arányok kiszámításának?

Az `value_counts()` módszer használatakor megadhatja a `normalize=True` opciót, az alábbiak szerint. Ez megspórolja azt a lépést, amikor a teljes adathalmaz hosszával kell osztani.

```python
df.neighbourhood_group.value_counts(normalize=True)
```

### Van rá mód, hogy tényleges százalékos arányokat lássunk a tizedes arányok helyett?

Az alábbi kód a következőket teszi:

- A `normalize=True` használatával létrehozza a kategorikus adathalmazunk minden egyes elemének arányait tizedesjegyek formájában.
- Szorozzuk meg az egyes értékeket 100-zal.
- Kerekítsük a legközelebbi "1"-re.
- Konvertálja az értékeket lebegőpontokból karakterláncokká.
- Adjunk százalékjelet minden karakterlánc végéhez.

```python
df.neighbourhood_group.value_counts(normalize=True).mul(100).round(1).astype('str') + '%'
```

Az eredmény egy olyan sorozat lesz, amely minden egyes kategóriára vonatkozóan egy rendezett százalékos értéket mutat, például Manhattan esetében "41,1%".

[<<< Előző](representing_data.md) | [Következő >>>](indexing.md)
