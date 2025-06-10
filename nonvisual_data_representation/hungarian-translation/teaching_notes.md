
# Nem vizuális adatfeltárás és reprezentáció Tanítási jegyzetek

## Adattípusok


## Kategorikus adatok

Airbnb adatok beolvasása  
df.neighbourhood_group.head()  
A neighbourhood_group ismétlődő értékek megjelenítése
Kategorikus adatok magyarázata
Set függvény használata
Előfordulások számolása a value_counts használatával
Az oszlopdiagram helyettesítése?
jól érzékelhető haszon a kapcsolatok meglátásában?

Számadatok finomítása
A számlálások mentése változó neighbourhood_counts értékekbe.
Oszd el az arányok kiszámításához
neighbourhood_counts / len(df)
Használja a százalékos változást is:
neighbourhood_counts.pct_change()

Gyakran ismételt kérdések:
oszlopdiagram megjelenítések létrehozása
az osztás lépésének kihagyása
rendezett százalékok létrehozása

## Indexelés

Számok mint köztes lépés
Bináris mint másik köztes lépés
Bináris adatok leírása
$1000 feletti tételek boolean sorozatának létrehozása
Price_bools létrehozása
Érték_számlálás és átlagolás az price_bools-on
Létrehozza a expensive_df-et indexeléssel
Mutassa meg azokat a környékeket, ahol a legtöbb 1000 feletti lista van.
expensive_df.neighbourhood.value_counts().head()


Kategorikus részhalmaz
Woodside_bools létrehozása
Woodside_df létrehozása
Átlag és medián ár lekérdezése
esetleg nagyon olcsó szobanevek megjelenítése

## Korreláció

Magyarázd el, hogy a korreláció két változó közötti kapcsolat.
Magyarázd meg a pozitív, negatív, nincs kapcsolat
Magyarázd meg az összefüggés erősségét
Magyarázza meg a -1-től 1-ig terjedő skálát
Végezze el a korrelációt a number_of_reviews és a reviews_per_month értékelések számával kapcsolatban.
Futtasson korrelációt az ár és az értékelések száma között

## Idő

Nézd meg az utolsó_értékelés
A last_review-t alakítsuk át datetime-ra
dates = pandas.to_datetime(df.last_review)
Csak az évszámok kiemelése egy változóba
years = dates.dt.year
Szerezzük meg az évek értékeinek számát
A pct_change használata egy vonaldiagram közelítéséhez

## Következtetés

Mit lehet könnyen helyettesíteni?
Mit nehéz helyettesíteni?
Az interaktív megközelítés előnyei: mindig építhetsz a válaszokra. A modell mindig bővíthető. Nagyon rugalmas.
Hátránya: Nem olyan azonnali. Nem olyan jó a látókkal való együttműködésre vagy meggyőzésre. Bizonyos típusú meglátásokhoz nehezebb hozzáférni, vagy hosszabb időt vesz igénybe.
Lehet, hogy valóban tudnod kell, hogy mit csinálsz, de ez többnyire jó dolog.
