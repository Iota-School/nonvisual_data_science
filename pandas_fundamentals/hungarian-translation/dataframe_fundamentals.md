[<<< Elõzõ](creating_dataframe.md) | [Következõ >>>](synthesis.md)

# Az adatkeret alapjai

Az adatkeret kétdimenziós adatokat tartalmaz. Ez jellemzõen oszlopok és sorok formájában jelenik meg. 

- Az oszlopok balról jobbra haladnak (az X tengelyen léteznek), és jellemzõen az adatok valamely aspektusát képviselik, például a nevet, a dátumot vagy a sütikre (cookie) költött dollárokat. Egy oszlop általában azonos adattípusú adatokat gyûjt össze.
- A sorok felülrõl lefelé haladnak (az Y tengelyen léteznek), és jellemzõen egy entitást képviselnek, például egy adott személyt, egy adott hónapot, egy adott könyvet stb. Egy sor különbözõ típusú adatokat tartalmaz, amelyek mind ugyanarról az entitásról szólnak.

## Az adatkeret mérete

Amikor új adatokkal foglalkozunk, az egyik elsõ dolog, amit meg akarunk tudni, a sorok és oszlopok száma. A sorok számának megállapításához az adatkereten a már ismert `len` függvényt használhatjuk:

```python
len(df)
```

Ha a fentieket futtatjuk a cookie-k költségvetésének adathalmazán, a kimenetnek ötnek kell lennie. Ez azt jelenti, hogy öt sorunk van. Minden sor egy adott hónap kiadásait jelenti.

A sorok és az oszlopok számának megadásához egyaránt használhatjuk az adatkeretünk `shape` attribútumát. (Ez egy attribútum és nem egy módszer, ezért nem használunk zárójelet.)

```python
df.shape
```

Ez egy listaszerû objektumot ad vissza, amely megmondja nekünk a sorok, illetve az oszlopok számát. A kimenetnek `(5, 3)`...-nak kell lennie, ami azt jelenti, hogy öt sorunk és három oszlopunk van.

## Oszlop- és sornevek keresése

Ha csak az oszlopneveket szeretnénk visszaadni az adathalmazunkból, akkor a következõt használhatjuk:

```python
df.columns
```

Ez egy indexet (egy másik listaszerû objektumot) ad vissza az oszlopnevekkel. Ez egyben lehetõséget biztosít számunkra, hogy egy lépésben megtaláljuk az oszlopok számát:

```python
len(df.columns)
```

A fentiekben a `len` függvényt használjuk az oszlopok indexén (listaszerû objektum). (Azt fogod látni, hogy a továbbiakban egyre több mindent fogunk kombinálni a tanultakból, ezért fontos, hogy nyomon kövessük, mit csinálnak az egyes függvények, módszerek és attribútumok, ahogy haladunk elõre.)

A soroknak is van nevük, és errõl már tanultunk, amikor a Pandas-sorozattal dolgoztunk. A sorok nevét vagy azonosítóit az adatkeret vagy sorozat indexében tároljuk. Vegyük most elõ az indexet:

Kimenetként a következõt kell kapnunk:

```python
RangeIndex(start=0, stop=5, step=1)
```

Ez elég furcsa kimenet, de a Python így írja le, hogy az index egy olyan számlálás, amely 0-nál kezdõdik, 5-nél áll meg, és minden alkalommal eggyel feljebb megy. Alapvetõen az indexünk egy listaszerû objektum, amely 0-tól számol felfelé, ami nem igazán hasznos számunkra.

Valójában ez a kimenet egy érvényes függvény a Pandasban, amelyet használhatunk arra, hogy saját listaszerû objektumokat hozzunk létre, amelyeket indexként vagy más okokból használhatunk. A késõbbi workshopokon egy hasonló függvényt fogunk használni mintaadatok létrehozására, de most is kipróbálhatja:

```python
pandas.RangeIndex(start=0, stop=5, step=1)
```

Hogyan néz ki egy jó és használható index? Általában minden sorhoz valami egyedit szeretnénk használni, lehetõleg valami azonosítót. Esetünkben tudjuk, hogy adataink a havi költségvetésünket képviselik. Minden sor egy hónapot képvisel. Mivel az adatállomány kicsi, a hónapok is egyediek. Egyelõre a hónapok lennének a legjobb index. Cseréljük le a nem jól használható indexünket egy jobbra:

```python
df.index = df.month
```

A fentiekben az indexet ugyanúgy rendeljük hozzá, mint egy változót. Ha megpróbáljuk az `df`-t önmagában használni az adatkeret ábrázolására, azt fogjuk látni, hogy minden sor elsõ elemét (a bal oldali oszlopot) a hónapra cseréltük. Az index helyettesítésének valami hasznosabbal számos elõnye van, és az adatok könnyebben értelmezhetõvé válnak.

## Oszlopokkal való munka

Valószínûleg az egyik leggyakoribb mûvelet, amit egy adatkereten végzünk, hogy egy adott oszlopot sorozatként kiemelünk. Vegyük ki a `cookie_budget` oszlopot:

```python
df.cookie_budget
```

Ez a mi `df` változónk, egy pont, majd cookie_budget, egy aláhúzással a cookie és a budget között.

A fentiekben egyszerûen a pont szintaxist használjuk, mintha az oszlop az adatkeret egy attribútuma lenne. Vissza kell kapnia a költségvetés oszlopát Pandas-sorozatként. Meglátja, hogy az oszlopon ugyanúgy végezhet mûveleteket, mintha bármilyen sorozat lenne. Próbálja ki a következõket:

```python
df.cookie_budget.mean()
```

A fenti mûveletet végrehajtva azt találjuk, hogy a cookie-k átlagos költségvetése az öt hónap alatt 2,8. Próbáljon most néhány percet szánni arra, hogy kipróbálja a többi sorozatmódszerünket különbözõ oszlopokon. (Például a `min`, `max`, `median`, és így tovább.) Ez a technika (kiemelünk egy oszlopot és csinálunk vele valamit) rendkívül gyakori a Pandasban.

## A költségvetésünk megduplázása

Hé, én szeretem a sütiket. Szereted a sütiket. Miért ne dobjuk el hát az óvatosságot a szélnek, és duplázzuk meg a havi költségvetésünket a sütikre?

Próbáljuk ki a következõt:

```python
df.cookie_budget * 2
```

A fentiekben kiemeljük a `cookie_budget` oszlopot, és megszorozzuk `2-vel`, ahogyan bármely matematikai feladatot elvégeznénk Pythonban. Az eredménynek a `cookie_budget` oszlopunkat kell ábrázolnia, mint korábban, de most minden értéket megduplázva. (Ha eddig nem vetted volna észre, azt is látni fogod, hogy a sorozat most a hónapot használja indexként. Amikor kiemelünk egy oszlopot, az adatkeret indexét használjuk).

Ez rendben van, de van egy problémánk. Ha megpróbáljuk az `df`-t önmagában használni, azt találjuk, hogy a `cookie_budget` oszlop nem változott. Ez nem jó, mert nagyon szeretnénk több pénzt költeni a sütikre.

Az elõzõ oszlop felülírásához próbáljuk meg a következõt:

```python
df.cookie_budget = df.cookie_budget * 2
```

Ez a `df` változó, egy pont, a `cookie_budget` oszlopnév, egy szóköz, egy egyenlõségjel, egy szóköz, a `df` változó, egy pont, egy szóköz, egy csillag a szorzáshoz, egy szóköz és a `2` szám.

A fentiekben a `cookie_budget` oszlopunkat ugyanúgy megszorozzuk 2-vel, mint korábban, de most az új értékekhez újra hozzárendeljük az oszlopot. Ez ugyanazt a szintaxist használja, mint egy változó hozzárendelése. 

Most, hogy meghoztuk azt a bölcs döntést, hogy megduplázzuk a cookie-k költségvetését, nézzük meg, hogy a havi költségvetésünk hány százalékát kellene cookie-kra költenünk. Próbáljuk ki a következõket:

```python
df.cookie_budget / df.budget
```
A kapott sorozatból megtudhatjuk, hogy az egyes hónapok teljes költségvetésének hány százalékát fogjuk cookie-kra költeni.

## Sorok kivonása

Ezt a mûveletet nem használjuk olyan gyakran, mint az oszlopok kiemelését, de konkrét sorokat is ki tudunk emelni. Két módszert fogunk megtanulni egy adott sor kiemelésére egy adathalmazból.

Elõször is emeljünk ki egy sort az indexbõl származó egyedi érték segítségével:

```python
df.loc["June"]
```

Ez a mi `df` változónk, egy pont, egy nyitó szögletes zárójel, idézõjel, a `Június` szó, idézõjel és egy záró szögletes zárójel.

A loc attribútum a szeletelõ szintaxissal (szögletes zárójelek) kombinálva lehetõvé teszi, hogy egy sort az adott sor indexében szereplõ elem alapján keressünk. Ez egy olyan sorozatot ad ki, ahol az értékek az adott sor értékei, az index pedig az egyes értékek oszlopneve.

Ha ismerjük egy sor numerikus helyét, akkor a következõt használhatjuk:

```python
df.iloc[0]
```

Ez a `df` változónk, egy pont, az `iloc` attribútum, egy nyitó szögletes zárójel, a `0` szám és egy záró szögletes zárójel. Ez az adatkeret elsõ (vagy 0.) sorát adja ki.

## Egyéb hasznos módszerek

Érdemes lehet kísérletezni a következõ módszerrel:

```python
df.info()
```

Az `info()` módszer kiír egy összefoglalót az adatkeretrõl, amelybõl megtudhatjuk az egyes oszlopok hosszát, nevét és adattípusát. Ha képernyõolvasót használsz, ez valószínûleg túl sok információ ahhoz, hogy elemezni akarj, de ez egy általánosan használt módszer arra, hogy áttekintést kapj egy adathalmazról.

[<<< Elõzõ](creating_dataframe.md) | [Következõ >>>](synthesis.md)