[<<< El�z�](dimensions.md) | [K�vetkez� >>>](keysvalues.md)

# A sorozat

Most, hogy m�r ismerj�k a b dimenzi�kat az adatokban, pr�b�ljunk meg egydimenzi�s adatokkal dolgozni. A hagyom�nyos Pythonban az egydimenzi�s adatokhoz haszn�lt alap�rtelmezett adatt�pus a lista. Menj�nk el�re, �s hozzuk l�tre az al�bbi list�t:

```python
budget = [10, 10, 5, 15, 15, 15]
```

A fentiekben l�trehozunk egy list�t �t elemmel (10, 10, 5, 15 �s 15), �s hozz�rendelj�k a 'budget' v�ltoz�hoz.

Az el�z� oktat�anyagban [megtanultunk n�h�ny m�dszert a Python list�kkal val� m�veletekre](../..//home/patrick/projects/nonvisual_data_science/nonvisual_python/sections/lists.md) (a szeletel�st, hogy konkr�t elemeket emelj�nk ki, a `len` m�dszert, hogy megtudjuk a lista hossz�t, �s az `append` m�dszert, hogy elemeket adjunk a lista v�g�re). De potenci�lisan sokkal t�bbet is tudunk csin�lni a lista adataival.

## Pandas sorozat

Import�ljuk a Pandas k�nyvt�rat:

```python
import pandas
```

A fenti sor IPythonba t�rt�n� be�r�sa ut�n nem szabad, hogy kimenetet kapjunk.

Most hozzunk l�tre egy Pandas sorozatot a list�nkb�l egy �j v�ltoz�hoz, ami egyszer�en a `s` bet� lesz.

```python
s = pandas.Series(budget)
```

A fentiekben a Pandas k�nyvt�ron bel�l a `Series` t�pus� objektumot (figyelj�k meg a nagybet�s �r�sm�dot a `Series-ben) �rj�k el. Ezut�n �tadjuk a `budget` list�nkat.

Ez �talak�tja a `budget` list�nkat egy �j adatt�puss�, a Pandas series-s�, �s hozz�rendeli a series-t a `s v�ltoz�hoz.

## egy Sorozat olvas�sa

Most, hogy a sorozatunkat hozz�rendelt�k az `s` v�ltoz�hoz, �rjuk be az `s`-t a saj�t sor�ba, �s nyomjuk le az `Enter` billenty�t, hogy megkapjuk a sorozat �br�zol�s�t:

```python
s
```

A sorozatunk �br�zol�sa a k�vetkez� lesz:


```
0 10
1 10
2 5
3 15
4 15
dtype: int64
```

A kimenet �sszesen hat sorb�l �ll. Az els� �t sor mindegyike k�t sz�mot tartalmaz, egyet balra, egyet pedig jobbra. 

- A jobb oldali sz�m a Budget adatunk. Ezt nevezz�k `�rt�knek`.
- A bal oldali sz�m az index. Alap�rtelmez�s szerint ez mondja meg az adatok hely�t, mint amikor listaszeletel�st v�gz�nk. Az indexnek m�s felhaszn�l�si m�djai is vannak, amelyekkel k�s�bb ismerked�nk meg.

A sor v�g�n l�v� sor a lista elemeinek adatt�pus�t mondja meg. Ebben az esetben ez `int64`, ami eg�sz sz�mot jelent.

## Sorozatm�dszerek

A f� ok, ami�rt a Pandas sorozatot v�lasztjuk a hagyom�nyos Python list�val szemben, az a Pandas sorozat �ltal biztos�tott m�dszerek sz�les v�laszt�ka. Pr�b�ljunk ki most ezek k�z�l n�h�nyat.

El�sz�r is, kapjuk meg a list�ban l�v� sz�mok �tlag�t. (Ne feledj�k, hogy az �tlag vagy mean az �sszes sz�m �sszead�s�nak eredm�nye, majd elosztjuk azzal, hogy h�ny sz�m van benne).

```python
s.mean()
```

A fentiekben a `s` v�ltoz�hoz rendelt sorozatunkon bel�l �rj�k el a `mean` met�dust. A met�dus nem fogad el argumentumokat, ez�rt nem tesz�nk semmit a z�r�jelek k�z�.

A fenti kimenet�nknek `11`-nek kell lennie. Ez a 10, 10, 5, 15 �s 15 �tlaga.

Szerezz�k meg a sorozatunk �t sz�m�nak medi�nj�t. (Ne feledj�k, hogy a medi�n a legk�z�ps� sz�m, vagy a k�t legk�z�ps� sz�m �tlaga).

```python
s.median()
```

Ez az eredm�ny tal�n intuit�vabb lenne, ha a sorozatok rendezettek lenn�nek. Pr�b�ljuk ki a `sort_values` m�dszert:

```python
s.sort_values()
```

Ez a sorozatunkat �gy adja ki, hogy az �rt�kek a legkisebbt�l a legnagyobbig vannak rendezve. Ha �tn�zz�k a kimenetet, l�thatjuk, hogy az �t �rt�k k�z�l a k�z�ps� sz�m val�ban `10`.

N�h�ny m�s m�dszert is kipr�b�lhatunk:

```python
s.min()
s.max()
s.count()
s.sum()
s.std()
```

## Describe

Egy gyakran haszn�lt Pandas sorozat met�dus a `describe`. Pr�b�ljuk ki:

```python
s.describe()
```

Menj el�re �s n�zd meg a kimenetet. �me n�h�ny kiemelked� eredm�ny:

- A `count` a sorozat elemeinek sz�ma.
- A `min` �s `max` a minim�lis �s maxim�lis �rt�kek.
- A `mean` az �tlag.
- Az `50%` megegyezik a medi�nnal, azaz a k�z�ps� sz�mmal. A `25%` �s a `75%` (huszon�t�dik �s hetven�t�dik kvartilis) az adathalmazban a 25%-os �s 75%-os �rt�khez legk�zelebbi sz�mok, illetve az adathalmaz als� fel�nek, illetve fels� fel�nek medi�nja.
- Az `std` a szabv�nyos  sz�r�s. A sz�r�s annak a m�r�sz�ma, hogy mekkora a sz�r�s az adathalmazban. Ha a sz�m alacsony, akkor az adathalmazban a legt�bb �rt�k k�zel van az �tlaghoz. Ha az �rt�k magas, az adatokban l�v� �rt�kek jobban sz�r�dnak.

## Mi a helyzet a Describe m�dszerrel?

A sorozatokr�l val� gondolkod�st�l el fogunk t�rni, b�r ezent�l folyamatosan haszn�lni fogjuk �ket. De gondolkodjunk a describe m�dszerr�l �s annak kimenet�r�l.

El�sz�r is, itt egy gyors k�rd�s. Milyen adatt�pus� a `describe()` kimenete?

Ha azt v�laszoltad, hogy Pandas `sorozat`, akkor igazad van. N�h�ny t�mpont, hogy a kimenet utols� sor�ban szerepel egy adatt�pus, az `float64`. A Pandas-sorozat �br�zol�s�nak utols� sora tartalmazza az adatt�pust. A kimenet minden sora k�t elemet tartalmaz: a bal oldalon az indexet, a jobb oldalon pedig az �rt�ket. Ebben az esetben az index egy hasznos c�mke, nem pedig egy sz�m.

## A describe hasznos nek�nk?

L�t� di�kjaim gyakran k�rdezik t�lem, hogy mi�rt haszn�lunk olyan m�dszereket, mint a `mean` �s `max`, ha a `describe` m�dszer ki�rja ezeket az inform�ci�kat �s m�g t�bbet is. Nekik azt v�laszolom, hogy gyakran konkr�t sz�mokkal akarunk dolgozni.

A k�perny�olvas� felhaszn�l�k sz�m�ra a k�rd�s ford�tott. A `Describe` egy kicsit t�l sok kimenetet k�n�l nek�nk. Ritk�n fordul el�, hogy egyszerre szeretn�nk tudni az �tlagot, medi�nt, sz�mot, maximumot stb. N�ha sz�ks�g�nk lehet mindezekre az inform�ci�kra, de �ltal�ban egyszer�bb, ha egyszerre csak egy-egy darabot kapunk vissza. Ez kevesebb �tn�z�st ig�nyel a r�sz�nkr�l.

A describe teh�t haszontalan? N�ha sok adatot szeretn�nk egyszerre megkapni, mert m�g nem tudjuk, hogy mit keres�nk. N�ha pedig egy l�t� koll�g�val dolgozol, �s tudod, hogy a `describe` lenne a legjobb m�dja annak, hogy magas szint� �ttekint�st adj. 

Legt�bbsz�r azonban k�perny�olvas� felhaszn�l�k�nt korl�tozni akarja a visszakapott kimenet mennyis�g�t. Szerencs�re a Pandas sz�mos eszk�zt ad a kez�nkbe a visszaadott inform�ci� mennyis�g�nek szab�lyoz�s�ra, ami azt jelenti, hogy kevesebb id�t kell t�lten�nk a kimenet �ttekint�s�vel, �s t�bb id�t t�lthet�nk adattudom�nyi munk�val.

## GYIK

Mi�rt van a `Series` nagybet�vel �rva, amikor sorozat objektumot hozunk l�tre? A Pythonban vannak bizonyos t�pus� adatok, amelyek nagybet�sek. A `Series`, amelyhez a Pandasban hozz�f�r�nk, egy `oszt�ly`, egyfajta sablon �j objektumok l�trehoz�s�hoz, �s a Pythonban az a konvenci�, hogy az oszt�lyokat nagybet�vel �rjuk. (Val�j�ban a konvenci� az, hogy a sz�kezdetet, vagy camel case-t haszn�ljuk, ami azt jelenti, hogy minden sz� elej�t nagybet�vel �rjuk a n�vben).

Mi�rt haszn�lunk ilyen r�vid v�ltoz�nevet (`s`) a sorozatunkhoz? �ltal�noss�gban elmondhat�, hogy a Pythonban a le�r� v�ltoz�nevek haszn�lat�ra �szt�n�znek, �s az `s` nem t�l le�r�. A r�vid v�lasz itt az, hogy van n�h�ny inform�lis konvenci� a Python adattudom�nyi k�z�ss�gben. Ha csak egy sorozat lesz, akkor azt gyakran `s`-nek nevezz�k. Ezekb�l az inform�lis r�vid v�ltoz� konvenci�kb�l m�g egy-kett�t meg fogunk tanulni ezekben az oktat�anyagokban. Ha azonban k�s�rt�st �rzel arra, hogy elkezdj elnevezni a v�ltoz�kat `s1`, `s2`, stb. n�vvel, akkor val�sz�n�leg itt az ideje, hogy hosszabb neveket adj a v�ltoz�knak.

[<<< El�z�](dimensions.md) | [K�vetkez� >>>](keysvalues.md)
