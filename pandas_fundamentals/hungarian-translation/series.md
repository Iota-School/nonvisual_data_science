[<<< Elõzõ](dimensions.md) | [Következõ >>>](keysvalues.md)

# A sorozat

Most, hogy már ismerjük a b dimenziókat az adatokban, próbáljunk meg egydimenziós adatokkal dolgozni. A hagyományos Pythonban az egydimenziós adatokhoz használt alapértelmezett adattípus a lista. Menjünk elõre, és hozzuk létre az alábbi listát:

```python
budget = [10, 10, 5, 15, 15, 15]
```

A fentiekben létrehozunk egy listát öt elemmel (10, 10, 5, 15 és 15), és hozzárendeljük a 'budget' változóhoz.

Az elõzõ oktatóanyagban [megtanultunk néhány módszert a Python listákkal való mûveletekre](../..//home/patrick/projects/nonvisual_data_science/nonvisual_python/sections/lists.md) (a szeletelést, hogy konkrét elemeket emeljünk ki, a `len` módszert, hogy megtudjuk a lista hosszát, és az `append` módszert, hogy elemeket adjunk a lista végére). De potenciálisan sokkal többet is tudunk csinálni a lista adataival.

## Pandas sorozat

Importáljuk a Pandas könyvtárat:

```python
import pandas
```

A fenti sor IPythonba történõ beírása után nem szabad, hogy kimenetet kapjunk.

Most hozzunk létre egy Pandas sorozatot a listánkból egy új változóhoz, ami egyszerûen a `s` betû lesz.

```python
s = pandas.Series(budget)
```

A fentiekben a Pandas könyvtáron belül a `Series` típusú objektumot (figyeljük meg a nagybetûs írásmódot a `Series-ben) érjük el. Ezután átadjuk a `budget` listánkat.

Ez átalakítja a `budget` listánkat egy új adattípussá, a Pandas series-sé, és hozzárendeli a series-t a `s változóhoz.

## egy Sorozat olvasása

Most, hogy a sorozatunkat hozzárendeltük az `s` változóhoz, írjuk be az `s`-t a saját sorába, és nyomjuk le az `Enter` billentyût, hogy megkapjuk a sorozat ábrázolását:

```python
s
```

A sorozatunk ábrázolása a következõ lesz:


```
0 10
1 10
2 5
3 15
4 15
dtype: int64
```

A kimenet összesen hat sorból áll. Az elsõ öt sor mindegyike két számot tartalmaz, egyet balra, egyet pedig jobbra. 

- A jobb oldali szám a Budget adatunk. Ezt nevezzük `értéknek`.
- A bal oldali szám az index. Alapértelmezés szerint ez mondja meg az adatok helyét, mint amikor listaszeletelést végzünk. Az indexnek más felhasználási módjai is vannak, amelyekkel késõbb ismerkedünk meg.

A sor végén lévõ sor a lista elemeinek adattípusát mondja meg. Ebben az esetben ez `int64`, ami egész számot jelent.

## Sorozatmódszerek

A fõ ok, amiért a Pandas sorozatot választjuk a hagyományos Python listával szemben, az a Pandas sorozat által biztosított módszerek széles választéka. Próbáljunk ki most ezek közül néhányat.

Elõször is, kapjuk meg a listában lévõ számok átlagát. (Ne feledjük, hogy az átlag vagy mean az összes szám összeadásának eredménye, majd elosztjuk azzal, hogy hány szám van benne).

```python
s.mean()
```

A fentiekben a `s` változóhoz rendelt sorozatunkon belül érjük el a `mean` metódust. A metódus nem fogad el argumentumokat, ezért nem teszünk semmit a zárójelek közé.

A fenti kimenetünknek `11`-nek kell lennie. Ez a 10, 10, 5, 15 és 15 átlaga.

Szerezzük meg a sorozatunk öt számának mediánját. (Ne feledjük, hogy a medián a legközépsõ szám, vagy a két legközépsõ szám átlaga).

```python
s.median()
```

Ez az eredmény talán intuitívabb lenne, ha a sorozatok rendezettek lennének. Próbáljuk ki a `sort_values` módszert:

```python
s.sort_values()
```

Ez a sorozatunkat úgy adja ki, hogy az értékek a legkisebbtõl a legnagyobbig vannak rendezve. Ha átnézzük a kimenetet, láthatjuk, hogy az öt érték közül a középsõ szám valóban `10`.

Néhány más módszert is kipróbálhatunk:

```python
s.min()
s.max()
s.count()
s.sum()
s.std()
```

## Describe

Egy gyakran használt Pandas sorozat metódus a `describe`. Próbáljuk ki:

```python
s.describe()
```

Menj elõre és nézd meg a kimenetet. Íme néhány kiemelkedõ eredmény:

- A `count` a sorozat elemeinek száma.
- A `min` és `max` a minimális és maximális értékek.
- A `mean` az átlag.
- Az `50%` megegyezik a mediánnal, azaz a középsõ számmal. A `25%` és a `75%` (huszonötödik és hetvenötödik kvartilis) az adathalmazban a 25%-os és 75%-os értékhez legközelebbi számok, illetve az adathalmaz alsó felének, illetve felsõ felének mediánja.
- Az `std` a szabványos  szórás. A szórás annak a mérõszáma, hogy mekkora a szórás az adathalmazban. Ha a szám alacsony, akkor az adathalmazban a legtöbb érték közel van az átlaghoz. Ha az érték magas, az adatokban lévõ értékek jobban szóródnak.

## Mi a helyzet a Describe módszerrel?

A sorozatokról való gondolkodástól el fogunk térni, bár ezentúl folyamatosan használni fogjuk õket. De gondolkodjunk a describe módszerrõl és annak kimenetérõl.

Elõször is, itt egy gyors kérdés. Milyen adattípusú a `describe()` kimenete?

Ha azt válaszoltad, hogy Pandas `sorozat`, akkor igazad van. Néhány támpont, hogy a kimenet utolsó sorában szerepel egy adattípus, az `float64`. A Pandas-sorozat ábrázolásának utolsó sora tartalmazza az adattípust. A kimenet minden sora két elemet tartalmaz: a bal oldalon az indexet, a jobb oldalon pedig az értéket. Ebben az esetben az index egy hasznos címke, nem pedig egy szám.

## A describe hasznos nekünk?

Látó diákjaim gyakran kérdezik tõlem, hogy miért használunk olyan módszereket, mint a `mean` és `max`, ha a `describe` módszer kiírja ezeket az információkat és még többet is. Nekik azt válaszolom, hogy gyakran konkrét számokkal akarunk dolgozni.

A képernyõolvasó felhasználók számára a kérdés fordított. A `Describe` egy kicsit túl sok kimenetet kínál nekünk. Ritkán fordul elõ, hogy egyszerre szeretnénk tudni az átlagot, mediánt, számot, maximumot stb. Néha szükségünk lehet mindezekre az információkra, de általában egyszerûbb, ha egyszerre csak egy-egy darabot kapunk vissza. Ez kevesebb átnézést igényel a részünkrõl.

A describe tehát haszontalan? Néha sok adatot szeretnénk egyszerre megkapni, mert még nem tudjuk, hogy mit keresünk. Néha pedig egy látó kollégával dolgozol, és tudod, hogy a `describe` lenne a legjobb módja annak, hogy magas szintû áttekintést adj. 

Legtöbbször azonban képernyõolvasó felhasználóként korlátozni akarja a visszakapott kimenet mennyiségét. Szerencsére a Pandas számos eszközt ad a kezünkbe a visszaadott információ mennyiségének szabályozására, ami azt jelenti, hogy kevesebb idõt kell töltenünk a kimenet áttekintésével, és több idõt tölthetünk adattudományi munkával.

## GYIK

Miért van a `Series` nagybetûvel írva, amikor sorozat objektumot hozunk létre? A Pythonban vannak bizonyos típusú adatok, amelyek nagybetûsek. A `Series`, amelyhez a Pandasban hozzáférünk, egy `osztály`, egyfajta sablon új objektumok létrehozásához, és a Pythonban az a konvenció, hogy az osztályokat nagybetûvel írjuk. (Valójában a konvenció az, hogy a szókezdetet, vagy camel case-t használjuk, ami azt jelenti, hogy minden szó elejét nagybetûvel írjuk a névben).

Miért használunk ilyen rövid változónevet (`s`) a sorozatunkhoz? Általánosságban elmondható, hogy a Pythonban a leíró változónevek használatára ösztönöznek, és az `s` nem túl leíró. A rövid válasz itt az, hogy van néhány informális konvenció a Python adattudományi közösségben. Ha csak egy sorozat lesz, akkor azt gyakran `s`-nek nevezzük. Ezekbõl az informális rövid változó konvenciókból még egy-kettõt meg fogunk tanulni ezekben az oktatóanyagokban. Ha azonban kísértést érzel arra, hogy elkezdj elnevezni a változókat `s1`, `s2`, stb. névvel, akkor valószínûleg itt az ideje, hogy hosszabb neveket adj a változóknak.

[<<< Elõzõ](dimensions.md) | [Következõ >>>](keysvalues.md)
