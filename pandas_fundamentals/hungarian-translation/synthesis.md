[<<< El�z�](dataframe_fundamentals.md) | [K�vetkez� >>>](challenges.md)

# Emelj�k ki egy�tt

Eddig a k�l�nb�z� sorozatok �s adatkeretek m�dszereit haszn�ltuk egy saj�t magunk �ltal l�trehozott j�t�kadathalmazon. Pr�b�ljuk meg haszn�lni �ket egy val�s adathalmazon.

## Adathalmazunk beolvas�sa

Ehhez a r�szhez �s a k�vetkez� workshophoz egy nagy adathalmazt fogunk haszn�lni, amely a New York-i Airbnb b�rbead�sokr�l sz�l. Az adatokat a [this repository](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data) oldalr�l szerezt�k be a Kaggle-en, amely egy elemz�sre sz�nt adathalmazok megoszt�s�ra szolg�l� weboldal. Az adatok 2019-b�l sz�rmaznak, teh�t megel�zik mind a vil�gj�rv�nyt, mind a 2023-as Airbnb-t�rv�nyt New York Cityben.

## Az adataink olvas�sa

Els� l�p�s�nk az, hogy a Pandas beh�vja az Airbnb-adatainkat. M�soljuk ki az al�bbi sort, �s futtassuk le az IPythonban:

```python
df = pandas.read_csv('https://bit.ly/nycbnb')
```

Ez a parancs fel�l�rja a kor�bbi `df` v�ltoz�nkat, ez�rt �rdemes most elmenteni a munkamenetet a `%sav` var�zslattal, ha k�s�bb szeretn�nk k�s�rletezni vele.

## Kezdeti elemz�s

Futtassuk v�gig a tanult elj�r�sokat, hogy megismerj�k az adat�llom�nyunkat... El�sz�r is kapjuk meg az adathalmaz m�ret�t sorokban �s oszlopokban:

```python
df.shape
```

A parancs kimenete a k�vetkez� kell, hogy legyen: `((48895, 16)`. Ez azt jelenti, hogy 48 895 sorunk �s 16 oszlopunk van. M�sk�pp �gy is elk�pzelhetj�k, hogy 48 895 meghirdetett Airbnb-b�rlem�ny�nk van, �s minden ilyen entit�shoz 16 inform�ci� tartozik.

Miel�tt tov�bbl�pn�nk, meg kell tudnunk, hogy milyen t�pus� adatokra t�maszkodhatunk. Szerezz�k meg az adat�llom�ny k�l�nb�z� oszlopainak nev�t:

```python
df.columns
```

Kor�bban azt mondtam, hogy ennek a parancsnak a kimenete egy listaszer� objektum. Sajnos ezt az adatt�pust (Pandas index), kiss� ideges�t� k�perny�olvas� felhaszn�l�k�nt �tn�zni. Ha a kimenetet soronk�nt szeretn� �ttekinteni, akkor az indexet a `list()` f�ggv�nnyel norm�l Python list�v� alak�thatja:

```python
list(df.columns)
```

Mivel egy sok elemet tartalmaz� norm�l lista az IPythonban soronk�nt egy elemet fog ki�rni, a kimenet k�nnyebben �ttekinthet�.

Ebben az adatk�szletben sok �rdekes oszlop van, de n�h�ny kiemelkedik:

- �r
- n�v
- szomsz�ds�g

N�zze meg ezeket az oszlopokat �gy, hogy sorozatk�nt emelje ki �ket az adathalmazb�l. Azt fogja tal�lni, hogy:

- Az "�r" oszlopok eg�sz sz�mokb�l (int64) �llnak, amelyek feltehet�en doll�rokat jel�lnek.
- A `n�v` oszlopok stringek vagy stringszer� objektumok form�j�ban jelennek meg. (A Pandas `object` n�ven t�pusk�nt.)
- A `szomsz�ds�g` oszlopok szint�n stringszer� objektumok, de sokszor ism�tl�d� �rt�kekkel.

Ezek nagyon k�l�nb�z� t�pus� adatok. A k�vetkez� workshopon megtanuljuk, hogyan kezelj�k az olyan adatokat, mint a `n�v` (sz�veges) �s a `szomsz�ds�g` (kategorikus). Fejezz�k be ezt a workshopot azzal, hogy egy kicsit dolgozunk az `�r` oszlopunkkal.

## Adataink korl�toz�sa

Tal�n �szrevetted, hogy amikor egy ilyen nagy adathalmazb�l oszlopokat emel�nk ki, mint ez, a Pandas nem nyomtatja ki a teljes 48,895 elemet. Ehelyett a Pandas az els� �t elemet adja ki, ki�r egy ellipszist, majd az utols� �t elemet. K�perny�olvas� felhaszn�l�k�nt esetleg tov�bb szeretn�nk korl�tozni ezt a kimenetet. Az egyik megk�zel�t�s lehet az `iloc[0]` haszn�lata, hogy csak az adathalmaz els� elem�t adjuk vissza. Alternat�vak�nt haszn�lhatjuk a k�t m�dszer egyik�t, amelyek mind az adatkereteken, mind a sorozatokon m�k�dnek a kimenet korl�toz�s�ra:

- A `head()` m�dszer az adatkeret vagy sorozat els� elemeit (alap�rtelmez�s szerint �t�t) emeli ki.
- A `tail()` m�dszer az utols� elemeket emeli ki egy adatkeretb�l vagy sorozatb�l (alap�rtelmez�s szerint �t�t).

## Mennyire dr�g�k a New York-i Airbnb-k?

Fejezz�k be a workshopot azzal, hogy megn�zz�k a New York-i airbnbs �rakat. Csak azokat a m�dszereket fogjuk haszn�lni, amelyeket eddig tanultunk ebben a workshopban. 

El�sz�r is der�ts�k ki, hogy mennyi az �tlagos airbnb-�r New York Cityben 2019-ben:

```python
df.price.mean()
```

Ez a df, egy pont, a `�r` oszlopunk, egy pont, majd a `k�z�p�rt�k` m�dszer�nk nyit� �s z�r� z�r�jelekkel.

A kimenet�nknek `152.7206871868289` kell lennie. Ez el�g magasnak t�nik egy �jszakai alv�shoz. Lehet, hogy NYC t�nyleg olyan dr�ga, mint ahogy hallottad?

Figyelj�k meg, hogy t�bb pontot haszn�lunk az attrib�tumok �s met�dusok sorrendben t�rt�n� �sszekapcsol�s�ra. Az adatkeretv�ltoz�nkkal kezd�nk (`df`), majd kiemelj�k az oszlopot, �s a `mean()` m�dszert haszn�ljuk. Ezt a technik�t "l�ncol�snak" nevezz�k.

Most pr�b�ljuk ki a `median()` m�dszer�nket:

```python
df.price.median()
```

A medi�nunk 106,0. Ez el�gg� elt�r az �tlagunkt�l. Mit gondolsz, mit jelent ez?

Ne feledj�k, hogy az �tlag az �sszes t�tel �sszege osztva a t�telek sz�m�val. Ha a k�vetkez� sz�mokat kapjuk:

5, 10, 10, 10, 10, 10, 99999

Akkor az �tlag 14293,42857142857. A medi�n azonban 10 lenne. Az �tlagok nagyon �rz�kenyek a kissz�m�, rendk�v�l magas sz�mokra. A medi�n azonban nem �rz�keny ilyen m�don a kis sz�m� kiugr� �rt�kre.

M�sk�pp fogalmazva, k�pzelj�k el, hogy van egy adathalmazunk mindenki nett� vagyon�r�l, akik a legut�bbi oszt�lyban vel�nk egy�tt tanultak. Most k�pzelj�k el, hogy ehhez az adathalmazhoz hozz�adjuk a multimilli�rdos Jeff Bezost. Ha Jeff Bezos is beker�l, a csoport �tlagos nett� vagyona nagym�rt�kben, val�sz�n�leg legal�bb egymilli�rddal fog n�vekedni (kiv�ve, ha �n egy nagyon nagy oszt�lyba j�rt, vagy ha az oszt�ly�ban l�v� emberek rendk�v�l gazdagok voltak). A medi�n azonban csak kis m�rt�kben v�ltozna.

Mivel az Airbnb-b�rl�s medi�nja jelent�sen alacsonyabb az �tlagn�l, felt�telezhetj�k, hogy New Yorkban sz�mos rendk�v�l dr�ga b�rlem�ny van, amelyek felfel� hajtj�k az �tlagot. Ezt m�g n�h�ny m�dszer �sszel�ncol�s�val ellen�rizhetj�k:

```python
df.price.sort_values().tail()
```

Ez rendezi az �sszes �rat, majd visszaadja az utols� �t�t. (Alap�rtelmez�s szerint a `sort_values` n�vekv� sorrendben, vagyis a legkisebbt�l a legnagyobbig rendezi az �rakat). A kimenet azt mutatja, hogy vannak nagyon dr�ga b�rlem�nyek, amelyek felfel� emelik az �tlagot. Ezt a helyzetet, amikor az �tlag nagyobb, mint a medi�n, jobbra ferde eloszl�snak nevezz�k.

Ha vizu�lis technik�t, p�ld�ul oszlopdiagramot haszn�ln�nk az adatok �br�zol�s�ra, akkor azt is l�thatn�nk, hogy az adatok k�z�tt kevesebb a nagyon nagy �rt�k. Az adatok alakj�r�l azonban hasonl� felismer�seket tehet�nk olyan technik�k seg�ts�g�vel is, mint p�ld�ul az �tlag �s a medi�n vizsg�lata. A k�vetkez� �l�sen kifinomultabb m�dszereket fogunk megvizsg�lni, amelyekkel nem vizu�lisan is megismerhet�nk nagy adathalmazokat.

[<<< El�z�](dataframe_fundamentals.md) | [K�vetkez� >>>](challenges.md)