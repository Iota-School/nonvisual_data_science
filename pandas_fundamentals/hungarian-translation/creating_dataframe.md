[<<< Elõzõ](keysvalues.md) | [Következõ >>>](dataframe_fundamentals.md)

# adatkeret létrehozása

Ha a sorozat az, ahogyan egydimenziós adatokat kezelünk a Pandasban, akkor az adatkeret az, ahogyan kétdimenziós adatokat kezelünk. A sorozathoz hasonlóan az adatkeret is számos módszert biztosít a benne lévõ adatokkal való munkához.

Egy sorozat létrehozásához elõször létrehoztunk egy listát, és átadtuk azt egy Pandas Series objektumnak. Egy adatkeret létrehozásához elõször egy szótárat kell létrehoznunk.

## A szótár létrehozása

Elõször is hozzunk létre három listát. Ha az elejétõl kezdve követted a történetet, akkor az elsõ listát már ki kellett volna adnod egy változónak).

```python
budget = [10, 10, 5, 15, 15]
month = ["június", "július", "szeptember", "október", "november"]
cookie_budget = [3, 2, 0, 4, 5]
```

Érdemes lefuttatni a `len()` parancsot minden ilyen listán, hogy ellenõrizze, hogy öt elemet tartalmaznak-e. Ha valamelyikben túl sok vagy túl kevés elem van, akkor a következõ lépésben hibát fogsz kapni.

Most, hogy megvannak ezek a listák, hozzunk létre egy szótárt. 

```python
monthly_budget = {
    "month": month, 
    "budget": budget, 
    "cookie_budget": cookie_budget
}
```

A fentiekben létrehozunk egy szótárat három kulcs-érték párral. A kulcs egy adatot leíró karakterlánc, az érték pedig egy lista. 

## Az adatkeret létrehozása

Végül használjuk a szótárat egy adatkeret létrehozására:

```python
df = pandas.DataFrame(monthly_budget)
```

Ellenõrizzük az újonnan létrehozott `df` változót, ha önmagában beírjuk egy sorba:

```python
df
```

Az eredmény egy jelentõs mennyiségû kimenet lesz. A kimenetnek az alábbi táblázathoz hasonlónak kell lennie, bár vegyük figyelembe, hogy a kimenet nem táblázat, hanem strukturálatlan szöveg lesz:

<table>
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>hónap</th>
      <th>költségvetés</th>
      <th>cookie_budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Június</td>
      <td>10</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Július</td>
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
      <td>Október</td>
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

Ez az adatkeret reprezentáció egy táblázat formájában jelenik meg. Az elsõ sor az oszlopcímekbõl áll. Ezek a fejlécek az adatkeret létrehozásakor megadott szótár kulcsai. Minden további sor egy-egy sort képvisel. Az elsõ oszlop (az elsõ szám, amit minden sorban hallunk) az index, amely a 0, 1, 2, 3 és 4 egész számokból áll.

Mivel az adatkeret ábrázolása nem táblázatos szerkezetû, a képernyõolvasó felhasználók számára csak korlátozottan használható. Bár az adatokat az egyes sorok gondos áttekintésével ki lehet elemezni, az adatkeretben lévõ adatok feltárásának jobb módjait a következõ részekben fogjuk megtanulni. Ezzel együtt jó, ha általánosságban ismerjük ennek az ábrázolásnak a szerkezetét.

Bár a látó adattudósok használják ezeket a reprezentációkat, nem olyan hasznosak, mint gondolnánk. Ennek oka, hogy nagy adathalmazok esetén az információk nagy része amúgy is levágásra kerül, mert nem praktikus az összeset megjeleníteni. Nem marad le olyan sok mindenrõl, ha nem használja a fenti ábrázolást - a látó adattudósoknak is használniuk kell a kimenet korlátozására szolgáló technikákat, amelyeket sok oszlopot és/vagy sort tartalmazó adathalmazok kezelése során tanulunk meg.

[<<< Elõzõ](keysvalues.md) | [Következõ >>>](dataframe_fundamentals.md)