[<<< Elõzõ](lists.md) | [Következõ >>>](objects.md)

# feltételek

A feltétel egy olyan utasítás, amely vagy igazra vagy hamisra értékelõdik. Adjuk be például a következõt a REPL-ünkbe:

```python
10 > 5
```
Ez a 10-es szám, majd egy nagyobb jel, majd egy ötös. Kimenetként az `igaz` értéket kell visszakapnunk. A Python megnézi az utasítást, kiértékeli (egyszerûsíti), megállapítja, hogy a tíz nagyobb, mint az öt, és a `True` érték visszaadásával tudatja velünk, hogy ez igaz.

## Boolean

A Pythonban a boolean egy olyan típus, amely vagy igazat, vagy hamisat jelent. Nagybetûkkel ábrázoljuk õket: `True` és `False`. 

## Összehasonlítás

A feltételes utasítások egyik leggyakoribb felhasználási módja két objektum összehasonlítása. Az összehasonlítás egyik módját már láttuk a `>`, vagyis a nagyobb, mint szimbólum használatával. Például:

```python
10 > 50
```
Mivel 10 kisebb, mint 50, a fenti eredmény `False` lesz. Ha ehelyett a `<` jelet használjuk, mint alább, az eredmény `igaz` lesz.

```python
10 < 50
```

Két objektum egyenlõségét a `==` operátorral is ellenõrizhetjük. (Ez két egyenlõségjelet jelent.)

```python
5 == 5
```

Ez öt, egy szóköz, egy dupla egyenlõségjel, egy szóköz és egy öt. Az eredménynek `igaznak` kell lennie.

Most próbáld ki a következõt:

```python
7 == 4
```

Ez hét, egy szóköz, egy dupla egyenlõségjel, egy szóköz és egy négy. Az eredménynek `False`-nak kell lennie.

A karakterláncokat is összehasonlíthatod így:

```python
"hello" == "viszlát"
```

```python
"hello" == "hello"
```

Ne feledjük, hogy a karakterláncok létrehozásához bizonyos szöveget idézõjelekkel veszünk körül. Ha a kettõs egyenlõségi operátorunkat (`==`) használjuk a `"hello"` és a `"goodbye"` összehasonlítására, akkor `False`-t kapunk, míg a `"hello"` és a `"hello"` összehasonlítása `True`-t ad vissza.

## Miért két egyenlõségjel?

Miért használunk két egyenlõségjelet az egyenlõség ellenõrzésére? Emlékezzünk, hogy amikor változókat rendelünk hozzá, egy egyenlõségjelet (`=`) használunk. A Pythonban egy egyenlõségjelet (`=`) használunk a változók hozzárendelésére, és két egyenlõségjelet (`==`) az egyenlõség ellenõrzésére.

[<<< Elõzõ](lists.md) | [Következõ >>>](objects.md)
