[<<< El�z�](creating_dataframe.md) | [K�vetkez� >>>](synthesis.md)

# Az adatkeret alapjai

Az adatkeret k�tdimenzi�s adatokat tartalmaz. Ez jellemz�en oszlopok �s sorok form�j�ban jelenik meg. 

- Az oszlopok balr�l jobbra haladnak (az X tengelyen l�teznek), �s jellemz�en az adatok valamely aspektus�t k�pviselik, p�ld�ul a nevet, a d�tumot vagy a s�tikre (cookie) k�lt�tt doll�rokat. Egy oszlop �ltal�ban azonos adatt�pus� adatokat gy�jt �ssze.
- A sorok fel�lr�l lefel� haladnak (az Y tengelyen l�teznek), �s jellemz�en egy entit�st k�pviselnek, p�ld�ul egy adott szem�lyt, egy adott h�napot, egy adott k�nyvet stb. Egy sor k�l�nb�z� t�pus� adatokat tartalmaz, amelyek mind ugyanarr�l az entit�sr�l sz�lnak.

## Az adatkeret m�rete

Amikor �j adatokkal foglalkozunk, az egyik els� dolog, amit meg akarunk tudni, a sorok �s oszlopok sz�ma. A sorok sz�m�nak meg�llap�t�s�hoz az adatkereten a m�r ismert `len` f�ggv�nyt haszn�lhatjuk:

```python
len(df)
```

Ha a fentieket futtatjuk a cookie-k k�lts�gvet�s�nek adathalmaz�n, a kimenetnek �tnek kell lennie. Ez azt jelenti, hogy �t sorunk van. Minden sor egy adott h�nap kiad�sait jelenti.

A sorok �s az oszlopok sz�m�nak megad�s�hoz egyar�nt haszn�lhatjuk az adatkeret�nk `shape` attrib�tum�t. (Ez egy attrib�tum �s nem egy m�dszer, ez�rt nem haszn�lunk z�r�jelet.)

```python
df.shape
```

Ez egy listaszer� objektumot ad vissza, amely megmondja nek�nk a sorok, illetve az oszlopok sz�m�t. A kimenetnek `(5, 3)`...-nak kell lennie, ami azt jelenti, hogy �t sorunk �s h�rom oszlopunk van.

## Oszlop- �s sornevek keres�se

Ha csak az oszlopneveket szeretn�nk visszaadni az adathalmazunkb�l, akkor a k�vetkez�t haszn�lhatjuk:

```python
df.columns
```

Ez egy indexet (egy m�sik listaszer� objektumot) ad vissza az oszlopnevekkel. Ez egyben lehet�s�get biztos�t sz�munkra, hogy egy l�p�sben megtal�ljuk az oszlopok sz�m�t:

```python
len(df.columns)
```

A fentiekben a `len` f�ggv�nyt haszn�ljuk az oszlopok index�n (listaszer� objektum). (Azt fogod l�tni, hogy a tov�bbiakban egyre t�bb mindent fogunk kombin�lni a tanultakb�l, ez�rt fontos, hogy nyomon k�vess�k, mit csin�lnak az egyes f�ggv�nyek, m�dszerek �s attrib�tumok, ahogy haladunk el�re.)

A soroknak is van nev�k, �s err�l m�r tanultunk, amikor a Pandas-sorozattal dolgoztunk. A sorok nev�t vagy azonos�t�it az adatkeret vagy sorozat index�ben t�roljuk. Vegy�k most el� az indexet:

Kimenetk�nt a k�vetkez�t kell kapnunk:

```python
RangeIndex(start=0, stop=5, step=1)
```

Ez el�g furcsa kimenet, de a Python �gy �rja le, hogy az index egy olyan sz�ml�l�s, amely 0-n�l kezd�dik, 5-n�l �ll meg, �s minden alkalommal eggyel feljebb megy. Alapvet�en az index�nk egy listaszer� objektum, amely 0-t�l sz�mol felfel�, ami nem igaz�n hasznos sz�munkra.

Val�j�ban ez a kimenet egy �rv�nyes f�ggv�ny a Pandasban, amelyet haszn�lhatunk arra, hogy saj�t listaszer� objektumokat hozzunk l�tre, amelyeket indexk�nt vagy m�s okokb�l haszn�lhatunk. A k�s�bbi workshopokon egy hasonl� f�ggv�nyt fogunk haszn�lni mintaadatok l�trehoz�s�ra, de most is kipr�b�lhatja:

```python
pandas.RangeIndex(start=0, stop=5, step=1)
```

Hogyan n�z ki egy j� �s haszn�lhat� index? �ltal�ban minden sorhoz valami egyedit szeretn�nk haszn�lni, lehet�leg valami azonos�t�t. Eset�nkben tudjuk, hogy adataink a havi k�lts�gvet�s�nket k�pviselik. Minden sor egy h�napot k�pvisel. Mivel az adat�llom�ny kicsi, a h�napok is egyediek. Egyel�re a h�napok lenn�nek a legjobb index. Cser�lj�k le a nem j�l haszn�lhat� index�nket egy jobbra:

```python
df.index = df.month
```

A fentiekben az indexet ugyan�gy rendelj�k hozz�, mint egy v�ltoz�t. Ha megpr�b�ljuk az `df`-t �nmag�ban haszn�lni az adatkeret �br�zol�s�ra, azt fogjuk l�tni, hogy minden sor els� elem�t (a bal oldali oszlopot) a h�napra cser�lt�k. Az index helyettes�t�s�nek valami hasznosabbal sz�mos el�nye van, �s az adatok k�nnyebben �rtelmezhet�v� v�lnak.

## Oszlopokkal val� munka

Val�sz�n�leg az egyik leggyakoribb m�velet, amit egy adatkereten v�gz�nk, hogy egy adott oszlopot sorozatk�nt kiemel�nk. Vegy�k ki a `cookie_budget` oszlopot:

```python
df.cookie_budget
```

Ez a mi `df` v�ltoz�nk, egy pont, majd cookie_budget, egy al�h�z�ssal a cookie �s a budget k�z�tt.

A fentiekben egyszer�en a pont szintaxist haszn�ljuk, mintha az oszlop az adatkeret egy attrib�tuma lenne. Vissza kell kapnia a k�lts�gvet�s oszlop�t Pandas-sorozatk�nt. Megl�tja, hogy az oszlopon ugyan�gy v�gezhet m�veleteket, mintha b�rmilyen sorozat lenne. Pr�b�lja ki a k�vetkez�ket:

```python
df.cookie_budget.mean()
```

A fenti m�veletet v�grehajtva azt tal�ljuk, hogy a cookie-k �tlagos k�lts�gvet�se az �t h�nap alatt 2,8. Pr�b�ljon most n�h�ny percet sz�nni arra, hogy kipr�b�lja a t�bbi sorozatm�dszer�nket k�l�nb�z� oszlopokon. (P�ld�ul a `min`, `max`, `median`, �s �gy tov�bb.) Ez a technika (kiemel�nk egy oszlopot �s csin�lunk vele valamit) rendk�v�l gyakori a Pandasban.

## A k�lts�gvet�s�nk megdupl�z�sa

H�, �n szeretem a s�tiket. Szereted a s�tiket. Mi�rt ne dobjuk el h�t az �vatoss�got a sz�lnek, �s dupl�zzuk meg a havi k�lts�gvet�s�nket a s�tikre?

Pr�b�ljuk ki a k�vetkez�t:

```python
df.cookie_budget * 2
```

A fentiekben kiemelj�k a `cookie_budget` oszlopot, �s megszorozzuk `2-vel`, ahogyan b�rmely matematikai feladatot elv�gezn�nk Pythonban. Az eredm�nynek a `cookie_budget` oszlopunkat kell �br�zolnia, mint kor�bban, de most minden �rt�ket megdupl�zva. (Ha eddig nem vetted volna �szre, azt is l�tni fogod, hogy a sorozat most a h�napot haszn�lja indexk�nt. Amikor kiemel�nk egy oszlopot, az adatkeret index�t haszn�ljuk).

Ez rendben van, de van egy probl�m�nk. Ha megpr�b�ljuk az `df`-t �nmag�ban haszn�lni, azt tal�ljuk, hogy a `cookie_budget` oszlop nem v�ltozott. Ez nem j�, mert nagyon szeretn�nk t�bb p�nzt k�lteni a s�tikre.

Az el�z� oszlop fel�l�r�s�hoz pr�b�ljuk meg a k�vetkez�t:

```python
df.cookie_budget = df.cookie_budget * 2
```

Ez a `df` v�ltoz�, egy pont, a `cookie_budget` oszlopn�v, egy sz�k�z, egy egyenl�s�gjel, egy sz�k�z, a `df` v�ltoz�, egy pont, egy sz�k�z, egy csillag a szorz�shoz, egy sz�k�z �s a `2` sz�m.

A fentiekben a `cookie_budget` oszlopunkat ugyan�gy megszorozzuk 2-vel, mint kor�bban, de most az �j �rt�kekhez �jra hozz�rendelj�k az oszlopot. Ez ugyanazt a szintaxist haszn�lja, mint egy v�ltoz� hozz�rendel�se. 

Most, hogy meghoztuk azt a b�lcs d�nt�st, hogy megdupl�zzuk a cookie-k k�lts�gvet�s�t, n�zz�k meg, hogy a havi k�lts�gvet�s�nk h�ny sz�zal�k�t kellene cookie-kra k�lten�nk. Pr�b�ljuk ki a k�vetkez�ket:

```python
df.cookie_budget / df.budget
```
A kapott sorozatb�l megtudhatjuk, hogy az egyes h�napok teljes k�lts�gvet�s�nek h�ny sz�zal�k�t fogjuk cookie-kra k�lteni.

## Sorok kivon�sa

Ezt a m�veletet nem haszn�ljuk olyan gyakran, mint az oszlopok kiemel�s�t, de konkr�t sorokat is ki tudunk emelni. K�t m�dszert fogunk megtanulni egy adott sor kiemel�s�re egy adathalmazb�l.

El�sz�r is emelj�nk ki egy sort az indexb�l sz�rmaz� egyedi �rt�k seg�ts�g�vel:

```python
df.loc["June"]
```

Ez a mi `df` v�ltoz�nk, egy pont, egy nyit� sz�gletes z�r�jel, id�z�jel, a `J�nius` sz�, id�z�jel �s egy z�r� sz�gletes z�r�jel.

A loc attrib�tum a szeletel� szintaxissal (sz�gletes z�r�jelek) kombin�lva lehet�v� teszi, hogy egy sort az adott sor index�ben szerepl� elem alapj�n keress�nk. Ez egy olyan sorozatot ad ki, ahol az �rt�kek az adott sor �rt�kei, az index pedig az egyes �rt�kek oszlopneve.

Ha ismerj�k egy sor numerikus hely�t, akkor a k�vetkez�t haszn�lhatjuk:

```python
df.iloc[0]
```

Ez a `df` v�ltoz�nk, egy pont, az `iloc` attrib�tum, egy nyit� sz�gletes z�r�jel, a `0` sz�m �s egy z�r� sz�gletes z�r�jel. Ez az adatkeret els� (vagy 0.) sor�t adja ki.

## Egy�b hasznos m�dszerek

�rdemes lehet k�s�rletezni a k�vetkez� m�dszerrel:

```python
df.info()
```

Az `info()` m�dszer ki�r egy �sszefoglal�t az adatkeretr�l, amelyb�l megtudhatjuk az egyes oszlopok hossz�t, nev�t �s adatt�pus�t. Ha k�perny�olvas�t haszn�lsz, ez val�sz�n�leg t�l sok inform�ci� ahhoz, hogy elemezni akarj, de ez egy �ltal�nosan haszn�lt m�dszer arra, hogy �ttekint�st kapj egy adathalmazr�l.

[<<< El�z�](creating_dataframe.md) | [K�vetkez� >>>](synthesis.md)