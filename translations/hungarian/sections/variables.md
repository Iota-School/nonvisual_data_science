[<<< Elõzõ](types.md) | [Következõ >>>](lists.md)

# Változók

A változó egy olyan szimbólum, amely egy objektumra, például egy karakterláncra, egész számra vagy listára utal. Alapvetõen ez egy módja annak, hogy nevet adjunk az adatoknak. Ha az adatnak egyszer nevet adtunk, a Python a továbbiakban nyomon követi azt.

Próbáljuk meg beírni ezt a sort:

```python
x = 5
```

Ez egy x, egy szóköz, egy egyenlõségjel, egy szóköz és egy 5.

Ebbõl a sorból nem hallhatunk semmilyen kimenetet. (Vagyis csak a `In` szót és egy számot fogsz hallani, miközben a Python új bemenetre vár.)

Most írjuk be az `x` betût, és nyomjuk meg az `Enter` billentyût. Hallanunk kell az `5`-öt, ami az `x` változóba mentett adat.

Próbáljuk ki ezeket a sorokat:

```python
x + 10
```

Kimenetként a `15` értéket kell hallanod.

Mentsünk el egy sztringet `y` változóként:

```python
y = "hello"
```

Most próbáljuk meg elérni az adatokat az `y` beírásával és az `Enter` lenyomásával. Kimenetként a `"hello"-t kell hallanunk.

Próbálja meg a következõ sor beírását:

```python
y + " és viszlát"
```

Ez egy `y`, egy szóköz, egy plusz, egy szóköz, egy idézõjel, a `"és viszlát"` szavak, és egy újabb idézõjel. Kimenetként a `"hello és viszlát"-t kell hallanod.


## Magyarázat

A `=` jel segítségével olyan szimbólumokat rendelhetünk adatokhoz, mint az `x` és az `y`.

A változók hosszabb szavak is lehetnek:

```
reggeli = ["sonka", "tojás", "pirítós"]
```

Ha a fenti sort futtatjuk, akkor egy három karakterláncot tartalmazó listát rendelünk a `reggeli` változóhoz.

A változók tartalmazhatnak betûket, számokat és aláhúzásokat, de betûvel kell kezdõdniük. 

## Kérdés: Hol laknak a változók?

Amikor hozzárendelünk egy változót, a Python elkezdi számon tartani azt. A változó neve és a hozzá tartozó adatok a számítógép memóriájában tárolódnak. Ha bezárja az IPython folyamatot, az összes változó és egyéb hozzárendelés törlõdik, és új munkamenetet kezd. Vannak módok a munkamenet mentésére, hogy késõbb folytathassa, de ezekrõl késõbb beszélünk errõl.

## Kérdés: Mi a helyzet a szóközökkel?

A fenti változó hozzárendelési sorokban az egyenlõségjel elõtt és után szóközt tettem be. Ezek a sorok teljesen mûködnek szóközök nélkül is. A látó emberek azonban úgy találják, hogy a szóközök megkönnyítik a sorok olvasását, és jó stílusnak számít, ha ezeket a szóközöket beillesztjük. Jó lehet, ha szokássá válik a szóközök hozzáadása, mivel így könnyebben olvashatóvá és professzionálisabbá válik a kód. Ha azonban saját magadnak írsz kódot, vagy egy eszközzel (az úgynevezett linterrel) akarod rendbe tenni a kódodat írás után, úgy dönthetsz, hogy elhagyod a szóközöket, és azt vettem észre, hogy sok vak programozó elhagyja ezeket a szóközöket.

[<<< Elõzõ](types.md) | [Következõ >>>](lists.md)
