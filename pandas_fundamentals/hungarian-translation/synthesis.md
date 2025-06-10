[<<< Elõzõ](dataframe_fundamentals.md) | [Következõ >>>](challenges.md)

# Emeljük ki együtt

Eddig a különbözõ sorozatok és adatkeretek módszereit használtuk egy saját magunk által létrehozott játékadathalmazon. Próbáljuk meg használni õket egy valós adathalmazon.

## Adathalmazunk beolvasása

Ehhez a részhez és a következõ workshophoz egy nagy adathalmazt fogunk használni, amely a New York-i Airbnb bérbeadásokról szól. Az adatokat a [this repository](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data) oldalról szereztük be a Kaggle-en, amely egy elemzésre szánt adathalmazok megosztására szolgáló weboldal. Az adatok 2019-bõl származnak, tehát megelõzik mind a világjárványt, mind a 2023-as Airbnb-törvényt New York Cityben.

## Az adataink olvasása

Elsõ lépésünk az, hogy a Pandas behívja az Airbnb-adatainkat. Másoljuk ki az alábbi sort, és futtassuk le az IPythonban:

```python
df = pandas.read_csv('https://bit.ly/nycbnb')
```

Ez a parancs felülírja a korábbi `df` változónkat, ezért érdemes most elmenteni a munkamenetet a `%sav` varázslattal, ha késõbb szeretnénk kísérletezni vele.

## Kezdeti elemzés

Futtassuk végig a tanult eljárásokat, hogy megismerjük az adatállományunkat... Elõször is kapjuk meg az adathalmaz méretét sorokban és oszlopokban:

```python
df.shape
```

A parancs kimenete a következõ kell, hogy legyen: `((48895, 16)`. Ez azt jelenti, hogy 48 895 sorunk és 16 oszlopunk van. Másképp úgy is elképzelhetjük, hogy 48 895 meghirdetett Airbnb-bérleményünk van, és minden ilyen entitáshoz 16 információ tartozik.

Mielõtt továbblépnénk, meg kell tudnunk, hogy milyen típusú adatokra támaszkodhatunk. Szerezzük meg az adatállomány különbözõ oszlopainak nevét:

```python
df.columns
```

Korábban azt mondtam, hogy ennek a parancsnak a kimenete egy listaszerû objektum. Sajnos ezt az adattípust (Pandas index), kissé idegesítõ képernyõolvasó felhasználóként átnézni. Ha a kimenetet soronként szeretné áttekinteni, akkor az indexet a `list()` függvénnyel normál Python listává alakíthatja:

```python
list(df.columns)
```

Mivel egy sok elemet tartalmazó normál lista az IPythonban soronként egy elemet fog kiírni, a kimenet könnyebben áttekinthetõ.

Ebben az adatkészletben sok érdekes oszlop van, de néhány kiemelkedik:

- ár
- név
- szomszédság

Nézze meg ezeket az oszlopokat úgy, hogy sorozatként emelje ki õket az adathalmazból. Azt fogja találni, hogy:

- Az "ár" oszlopok egész számokból (int64) állnak, amelyek feltehetõen dollárokat jelölnek.
- A `név` oszlopok stringek vagy stringszerû objektumok formájában jelennek meg. (A Pandas `object` néven típusként.)
- A `szomszédság` oszlopok szintén stringszerû objektumok, de sokszor ismétlõdõ értékekkel.

Ezek nagyon különbözõ típusú adatok. A következõ workshopon megtanuljuk, hogyan kezeljük az olyan adatokat, mint a `név` (szöveges) és a `szomszédság` (kategorikus). Fejezzük be ezt a workshopot azzal, hogy egy kicsit dolgozunk az `ár` oszlopunkkal.

## Adataink korlátozása

Talán észrevetted, hogy amikor egy ilyen nagy adathalmazból oszlopokat emelünk ki, mint ez, a Pandas nem nyomtatja ki a teljes 48,895 elemet. Ehelyett a Pandas az elsõ öt elemet adja ki, kiír egy ellipszist, majd az utolsó öt elemet. Képernyõolvasó felhasználóként esetleg tovább szeretnénk korlátozni ezt a kimenetet. Az egyik megközelítés lehet az `iloc[0]` használata, hogy csak az adathalmaz elsõ elemét adjuk vissza. Alternatívaként használhatjuk a két módszer egyikét, amelyek mind az adatkereteken, mind a sorozatokon mûködnek a kimenet korlátozására:

- A `head()` módszer az adatkeret vagy sorozat elsõ elemeit (alapértelmezés szerint ötöt) emeli ki.
- A `tail()` módszer az utolsó elemeket emeli ki egy adatkeretbõl vagy sorozatból (alapértelmezés szerint ötöt).

## Mennyire drágák a New York-i Airbnb-k?

Fejezzük be a workshopot azzal, hogy megnézzük a New York-i airbnbs árakat. Csak azokat a módszereket fogjuk használni, amelyeket eddig tanultunk ebben a workshopban. 

Elõször is derítsük ki, hogy mennyi az átlagos airbnb-ár New York Cityben 2019-ben:

```python
df.price.mean()
```

Ez a df, egy pont, a `ár` oszlopunk, egy pont, majd a `középérték` módszerünk nyitó és záró zárójelekkel.

A kimenetünknek `152.7206871868289` kell lennie. Ez elég magasnak tûnik egy éjszakai alváshoz. Lehet, hogy NYC tényleg olyan drága, mint ahogy hallottad?

Figyeljük meg, hogy több pontot használunk az attribútumok és metódusok sorrendben történõ összekapcsolására. Az adatkeretváltozónkkal kezdünk (`df`), majd kiemeljük az oszlopot, és a `mean()` módszert használjuk. Ezt a technikát "láncolásnak" nevezzük.

Most próbáljuk ki a `median()` módszerünket:

```python
df.price.median()
```

A mediánunk 106,0. Ez eléggé eltér az átlagunktól. Mit gondolsz, mit jelent ez?

Ne feledjük, hogy az átlag az összes tétel összege osztva a tételek számával. Ha a következõ számokat kapjuk:

5, 10, 10, 10, 10, 10, 99999

Akkor az átlag 14293,42857142857. A medián azonban 10 lenne. Az átlagok nagyon érzékenyek a kisszámú, rendkívül magas számokra. A medián azonban nem érzékeny ilyen módon a kis számú kiugró értékre.

Másképp fogalmazva, képzeljük el, hogy van egy adathalmazunk mindenki nettó vagyonáról, akik a legutóbbi osztályban velünk együtt tanultak. Most képzeljük el, hogy ehhez az adathalmazhoz hozzáadjuk a multimilliárdos Jeff Bezost. Ha Jeff Bezos is bekerül, a csoport átlagos nettó vagyona nagymértékben, valószínûleg legalább egymilliárddal fog növekedni (kivéve, ha Ön egy nagyon nagy osztályba járt, vagy ha az osztályában lévõ emberek rendkívül gazdagok voltak). A medián azonban csak kis mértékben változna.

Mivel az Airbnb-bérlés mediánja jelentõsen alacsonyabb az átlagnál, feltételezhetjük, hogy New Yorkban számos rendkívül drága bérlemény van, amelyek felfelé hajtják az átlagot. Ezt még néhány módszer összeláncolásával ellenõrizhetjük:

```python
df.price.sort_values().tail()
```

Ez rendezi az összes árat, majd visszaadja az utolsó ötöt. (Alapértelmezés szerint a `sort_values` növekvõ sorrendben, vagyis a legkisebbtõl a legnagyobbig rendezi az árakat). A kimenet azt mutatja, hogy vannak nagyon drága bérlemények, amelyek felfelé emelik az átlagot. Ezt a helyzetet, amikor az átlag nagyobb, mint a medián, jobbra ferde eloszlásnak nevezzük.

Ha vizuális technikát, például oszlopdiagramot használnánk az adatok ábrázolására, akkor azt is láthatnánk, hogy az adatok között kevesebb a nagyon nagy érték. Az adatok alakjáról azonban hasonló felismeréseket tehetünk olyan technikák segítségével is, mint például az átlag és a medián vizsgálata. A következõ ülésen kifinomultabb módszereket fogunk megvizsgálni, amelyekkel nem vizuálisan is megismerhetünk nagy adathalmazokat.

[<<< Elõzõ](dataframe_fundamentals.md) | [Következõ >>>](challenges.md)