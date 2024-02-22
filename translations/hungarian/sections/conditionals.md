[<<< El�z�](lists.md) | [K�vetkez� >>>](objects.md)

# felt�telek

A felt�tel egy olyan utas�t�s, amely vagy igazra vagy hamisra �rt�kel�dik. Adjuk be p�ld�ul a k�vetkez�t a REPL-�nkbe:

```python
10 > 5
```
Ez a 10-es sz�m, majd egy nagyobb jel, majd egy �t�s. Kimenetk�nt az `igaz` �rt�ket kell visszakapnunk. A Python megn�zi az utas�t�st, ki�rt�keli (egyszer�s�ti), meg�llap�tja, hogy a t�z nagyobb, mint az �t, �s a `True` �rt�k visszaad�s�val tudatja vel�nk, hogy ez igaz.

## Boolean

A Pythonban a boolean egy olyan t�pus, amely vagy igazat, vagy hamisat jelent. Nagybet�kkel �br�zoljuk �ket: `True` �s `False`. 

## �sszehasonl�t�s

A felt�teles utas�t�sok egyik leggyakoribb felhaszn�l�si m�dja k�t objektum �sszehasonl�t�sa. Az �sszehasonl�t�s egyik m�dj�t m�r l�ttuk a `>`, vagyis a nagyobb, mint szimb�lum haszn�lat�val. P�ld�ul:

```python
10 > 50
```
Mivel 10 kisebb, mint 50, a fenti eredm�ny `False` lesz. Ha ehelyett a `<` jelet haszn�ljuk, mint al�bb, az eredm�ny `igaz` lesz.

```python
10 < 50
```

K�t objektum egyenl�s�g�t a `==` oper�torral is ellen�rizhetj�k. (Ez k�t egyenl�s�gjelet jelent.)

```python
5 == 5
```

Ez �t, egy sz�k�z, egy dupla egyenl�s�gjel, egy sz�k�z �s egy �t. Az eredm�nynek `igaznak` kell lennie.

Most pr�b�ld ki a k�vetkez�t:

```python
7 == 4
```

Ez h�t, egy sz�k�z, egy dupla egyenl�s�gjel, egy sz�k�z �s egy n�gy. Az eredm�nynek `False`-nak kell lennie.

A karakterl�ncokat is �sszehasonl�thatod �gy:

```python
"hello" == "viszl�t"
```

```python
"hello" == "hello"
```

Ne feledj�k, hogy a karakterl�ncok l�trehoz�s�hoz bizonyos sz�veget id�z�jelekkel vesz�nk k�r�l. Ha a kett�s egyenl�s�gi oper�torunkat (`==`) haszn�ljuk a `"hello"` �s a `"goodbye"` �sszehasonl�t�s�ra, akkor `False`-t kapunk, m�g a `"hello"` �s a `"hello"` �sszehasonl�t�sa `True`-t ad vissza.

## Mi�rt k�t egyenl�s�gjel?

Mi�rt haszn�lunk k�t egyenl�s�gjelet az egyenl�s�g ellen�rz�s�re? Eml�kezz�nk, hogy amikor v�ltoz�kat rendel�nk hozz�, egy egyenl�s�gjelet (`=`) haszn�lunk. A Pythonban egy egyenl�s�gjelet (`=`) haszn�lunk a v�ltoz�k hozz�rendel�s�re, �s k�t egyenl�s�gjelet (`==`) az egyenl�s�g ellen�rz�s�re.

[<<< El�z�](lists.md) | [K�vetkez� >>>](objects.md)
