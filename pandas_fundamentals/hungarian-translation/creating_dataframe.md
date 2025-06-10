[<<< El�z�](keysvalues.md) | [K�vetkez� >>>](dataframe_fundamentals.md)

# adatkeret l�trehoz�sa

Ha a sorozat az, ahogyan egydimenzi�s adatokat kezel�nk a Pandasban, akkor az adatkeret az, ahogyan k�tdimenzi�s adatokat kezel�nk. A sorozathoz hasonl�an az adatkeret is sz�mos m�dszert biztos�t a benne l�v� adatokkal val� munk�hoz.

Egy sorozat l�trehoz�s�hoz el�sz�r l�trehoztunk egy list�t, �s �tadtuk azt egy Pandas Series objektumnak. Egy adatkeret l�trehoz�s�hoz el�sz�r egy sz�t�rat kell l�trehoznunk.

## A sz�t�r l�trehoz�sa

El�sz�r is hozzunk l�tre h�rom list�t. Ha az elej�t�l kezdve k�vetted a t�rt�netet, akkor az els� list�t m�r ki kellett volna adnod egy v�ltoz�nak).

```python
budget = [10, 10, 5, 15, 15]
month = ["j�nius", "j�lius", "szeptember", "okt�ber", "november"]
cookie_budget = [3, 2, 0, 4, 5]
```

�rdemes lefuttatni a `len()` parancsot minden ilyen list�n, hogy ellen�rizze, hogy �t elemet tartalmaznak-e. Ha valamelyikben t�l sok vagy t�l kev�s elem van, akkor a k�vetkez� l�p�sben hib�t fogsz kapni.

Most, hogy megvannak ezek a list�k, hozzunk l�tre egy sz�t�rt. 

```python
monthly_budget = {
    "month": month, 
    "budget": budget, 
    "cookie_budget": cookie_budget
}
```

A fentiekben l�trehozunk egy sz�t�rat h�rom kulcs-�rt�k p�rral. A kulcs egy adatot le�r� karakterl�nc, az �rt�k pedig egy lista. 

## Az adatkeret l�trehoz�sa

V�g�l haszn�ljuk a sz�t�rat egy adatkeret l�trehoz�s�ra:

```python
df = pandas.DataFrame(monthly_budget)
```

Ellen�rizz�k az �jonnan l�trehozott `df` v�ltoz�t, ha �nmag�ban be�rjuk egy sorba:

```python
df
```

Az eredm�ny egy jelent�s mennyis�g� kimenet lesz. A kimenetnek az al�bbi t�bl�zathoz hasonl�nak kell lennie, b�r vegy�k figyelembe, hogy a kimenet nem t�bl�zat, hanem struktur�latlan sz�veg lesz:

<table>
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>h�nap</th>
      <th>k�lts�gvet�s</th>
      <th>cookie_budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>J�nius</td>
      <td>10</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>J�lius</td>
      <td>10</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Szeptember</td>
      <td>5</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Okt�ber</td>
      <td>15</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>November</td>
      <td>15</td>
      <td>5</td>
    </tr>
  </tbody>
</table>

Ez az adatkeret reprezent�ci� egy t�bl�zat form�j�ban jelenik meg. Az els� sor az oszlopc�mekb�l �ll. Ezek a fejl�cek az adatkeret l�trehoz�sakor megadott sz�t�r kulcsai. Minden tov�bbi sor egy-egy sort k�pvisel. Az els� oszlop (az els� sz�m, amit minden sorban hallunk) az index, amely a 0, 1, 2, 3 �s 4 eg�sz sz�mokb�l �ll.

Mivel az adatkeret �br�zol�sa nem t�bl�zatos szerkezet�, a k�perny�olvas� felhaszn�l�k sz�m�ra csak korl�tozottan haszn�lhat�. B�r az adatokat az egyes sorok gondos �ttekint�s�vel ki lehet elemezni, az adatkeretben l�v� adatok felt�r�s�nak jobb m�djait a k�vetkez� r�szekben fogjuk megtanulni. Ezzel egy�tt j�, ha �ltal�noss�gban ismerj�k ennek az �br�zol�snak a szerkezet�t.

B�r a l�t� adattud�sok haszn�lj�k ezeket a reprezent�ci�kat, nem olyan hasznosak, mint gondoln�nk. Ennek oka, hogy nagy adathalmazok eset�n az inform�ci�k nagy r�sze am�gy is lev�g�sra ker�l, mert nem praktikus az �sszeset megjelen�teni. Nem marad le olyan sok mindenr�l, ha nem haszn�lja a fenti �br�zol�st - a l�t� adattud�soknak is haszn�lniuk kell a kimenet korl�toz�s�ra szolg�l� technik�kat, amelyeket sok oszlopot �s/vagy sort tartalmaz� adathalmazok kezel�se sor�n tanulunk meg.

[<<< El�z�](keysvalues.md) | [K�vetkez� >>>](dataframe_fundamentals.md)