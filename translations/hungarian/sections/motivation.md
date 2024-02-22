[<<< El�z�](objects.md) | [K�vetkez� >>>](magic.md)

# Egy kis motiv�ci�

A m�helymunk�nk v�g�hez k�zeled�nk. Hogy inspir�ljon benneteket a sorozat k�vetkez� r�sz�re, hozzunk l�tre egy egyszer� alkalmaz�st, amely egy kis motiv�ci�t ny�jt, amikor sz�ks�getek van r�.

El�sz�r is l�trehozunk egy �res list�t, �s felt�ltj�k n�h�ny motiv�l� (vagy vicces) id�zettel. Ezut�n egy v�letlenszer�s�get haszn�lunk, hogy kiv�lasszon nek�nk egy id�zetet a list�b�l. Ahhoz, hogy ezt a v�letlenszer�s�get haszn�lhassuk, megismerked�nk a k�nyvt�rak import�l�s�val, ami vitathatatlanul a Python leger�sebb funkci�ja.

## Adataink l�trehoz�sa

Kezdetnek hozzunk l�tre egy �res list�t, �s rendelj�k hozz� a `motivational_quotes` v�ltoz�hoz. (Ez a `motivational` �s az `quotes` szavakat jelenti, egy al�h�z�ssal elv�lasztva).
Magyar ford�t�sa: motiv�ci�s id�zetek

```python
motivational_quotes = []
```

Ez a `motivational_quotes` v�ltoz� neve, egy sz�k�z, egy egyenl�s�gjel, egy sz�k�z, egy nyit� sz�gletes z�r�jel �s egy z�r� sz�gletes z�r�jel.


Most m�r van egy �res list�nk, k�szen arra, hogy id�zetekkel t�lts�k meg. 
Haszn�ljuk az `append` met�dusunkat, hogy n�h�ny id�zetet adjunk a list�hoz: (Ne feledj�k, hogy a tabul�tor billenty�vel kit�lthetj�k a hossz� v�ltoz�nev�nket).

```python
motivational_quotes .append("Azt hiszem, kezdek belej�nni ebbe a Python dologba.")
```

Ez m�r egy id�zet. Adjunk hozz� m�g kett�t-h�rmat:

```python
motivational_quotes .append("Im�dom a szintaktikai hib�kat. J�het a kih�v�s!")
```

```python
motivational_quotes .append("Bogarakat eszem reggelire. De nem ilyeneket.")
```

```python
motivational_quotes .append("N�zd, anya, a parancssort haszn�lom!")
```

B�rmilyen id�z�jelet haszn�lhatsz, csak ne feledd, hogy dupla id�z�jellel kezdd �s fejezd be, ne aposztr�ffal (szimpla id�z�jel).

N�zz�k meg a list�nkat �gy, hogy a REPL-be �nmag�ban be�rjuk a `motivational_quotes` v�ltoz� nev� v�ltoz�t. Vissza kell kapnunk egy list�t az �ltalunk hozz�adott id�zetekkel.

```python
Out[6]: 
["Azt hiszem, kezdek belej�nni ebbe a Python dologba.",
 'Im�dom a szintaktikai hib�kat. j�het a kih�v�s!',
'Bogarakat eszem reggelire. De nem ilyeneket.'
 "N�zd, anya, a parancssort haszn�lom!"]]
```

## K�nyvt�r import�l�sa

Minden, amit eddig ebben a workshopban csin�ltunk, a Python nyelv be�p�tett funkci�it haszn�lta. Ahhoz azonban, hogy v�letlenszer�en v�lasszunk egy id�zetet a list�nkb�l, sz�ks�g�nk lesz egy speci�lisabb f�ggv�nyre a `random` k�nyvt�rb�l. Adjuk hozz� ezt a f�ggv�nyt a programunkhoz, majd elmagyar�zzuk, hogy mik azok a k�nyvt�rak, �s hogyan haszn�ljuk �ket Pythonban.

El�sz�r is import�ljuk a `random` k�nyvt�rat.

```python
import random
```
Ezzel l�trehozunk egy �j objektumot, amely el�rhet� sz�munkra a REPL-ben. Pr�b�ljuk meg be�rni a `random`-t �nmag�ban, �s megtudjuk, hogy ez egy `random` nev� modul.

Haszn�ljunk egy f�ggv�nyt a `random` k�nyvt�rb�l, hogy kiv�lasszunk egy v�letlenszer� id�zetet a list�nkb�l:

```python
random.choice(motivational_quotes)
```

Meghallgatunk egy id�zetet a list�nkb�l. Nyomjuk meg a fel gombot, hogy kit�lts�k ugyanazt a sort, majd nyomjuk meg az `Enter` billenty�t, �s minden alkalommal m�s id�zetet fogunk hallani.

## Mi az a k�nyvt�r?

A k�nyvt�r olyan f�ggv�nyek �s egy�b objektumok t�rol�ja, amelyeket k�nnyen be lehet h�zni a saj�t Python programjaidba. A k�nyvt�rakat �ltal�ban egy adott c�lra hozz�k l�tre: vannak k�nyvt�rak weboldalak let�lt�s�re, matematikai munk�ra, bizonyos f�jlt�pusokkal val� munk�ra �s szinte minden m�sra, ami csak eszedbe jut. A k�nyvt�r �ltal�nos kifejez�s az import�l�sra sz�nt k�dra, a Python-specifikus kifejez�s a modul.

A Python egy szabv�nyos k�nyvt�rral rendelkezik, amely sz�mos gyakori feladatra tartalmaz modulokat. Ezen k�v�l az �ltalunk haszn�lt Anaconda disztrib�ci� sz�mos k�nyvt�rat tartalmaz az adattudom�nyhoz kapcsol�d� feladatokhoz.

Az olyan f�ggv�nyek, mint a `help` �s a `dir` az import�lt k�nyvt�rakkal m�k�dnek, b�r �rdemes lehet ut�nan�zni a k�nyvt�r saj�t dokument�ci�j�ban vagy valamilyen m�s oktat�programban, hogy megtudjuk, hogyan haszn�ljunk egy adott k�nyvt�rat.

[<<< El�z�](objects.md) | [K�vetkez� >>>](magic.md)
