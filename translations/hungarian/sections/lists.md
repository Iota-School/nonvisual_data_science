[<<< El�z�](variables.md) | [K�vetkez� >>>](conditionals.md)

# List�k

## List�k

Eml�kszel a list�kra? �gy n�znek ki:

```python
flowers = ['rose', 'violet', 'buttercup']
```

Menj el�re, �s �rd be a fenti sort, hogy a `flowers` v�ltoz�hoz hozz�rendelj egy list�t, amelyben h�rom karakterl�nc van. Ne feledje, hogy mindh�rom karakterl�nc k�r� id�z�jelet tegyen, �s a lista elemeit vessz�vel v�lassza el egym�st�l.

Ellen�rizze a list�t a `vir�gok` v�ltoz� nev�nek be�r�s�val. A kimenetk�nt a `['r�zsa', 'ibolya', 'bogl�rka']-t kell hallania.

## A hossz megad�sa

Eddig ebben a workshopban csak egy f�ggv�nyt haszn�ltunk, a `type()` f�ggv�nyt. Pr�b�ljunk ki egy m�sikat. �rjuk be a k�vetkez� sort:

```python
len(flowers)
```

Ez a `len` sz� (a hossz r�vid�t�se), egy nyit� z�r�jel, a flowers v�ltoz�nk �s egy z�r�jel.

Ha a fentieket futtatjuk, akkor a `3` eg�sz sz�mot kell hallanunk kimenetk�nt. Ez azt jelenti, hogy a list�nkban h�rom elem van. 

## Listaszeletel�s

A Pythonban a list�k egyik hasznos tulajdons�ga a listaszeletel�s, amely lehet�v� teszi, hogy a list�n bel�l egy bizonyos helyen l�v� konkr�t elemeket kiemelj�nk. Pr�b�ljuk ki a k�vetkez�t:

```python
flowers[0]
```

Ez a `vir�gok` v�ltoz� neve, egy nyit� sz�gletes z�r�jel, az eg�sz sz�m `0` �s egy z�r� sz�gletes z�r�jel. Kimenetk�nt a `rose`-t kell kapnod, mivel ez az els� (vagy nulladik) elem a list�ban. (Zavar� m�don a Pythonban �s a legt�bb m�s programoz�si nyelvben is null�r�l kezd�dik a sz�ml�l�s.)

Pr�b�ljuk meg el�rni a lista t�bbi elem�t (`violet` �s `buttercup`).

A lista v�g�t�l visszafel� sz�molhatunk negat�v sz�mokkal. P�ld�ul a lista utols� eleme a `-` lenne.

```python
flowers[-1]
```

## Mi a helyzet a ciklusokkal?

A Pythonban a dolgok elv�gz�s�nek gyakori m�dja az �gynevezett ciklus �r�sa, ami l�nyeg�ben egy olyan k�d, amely egy lista vagy listaszer� objektum minden egyes elem�re lefut. A j�v�beli workshopokon a Pandas-t, egy adattudom�nyi k�nyvt�rat (eszk�zt) fogjuk haszn�lni. B�r a Pandas n�mileg t�mogatja a ciklusok haszn�lat�t, saj�t megk�zel�t�sei vannak a list�kkal �s listaszer� objektumokkal val� munk�hoz, ez�rt a Python bevezet�j�ben nem foglalkozunk a ciklusokkal. 

B�r ebben a workshop-sorozatban nem fogunk ciklussal dolgozni, ezek a Python alapvet� r�sz�t k�pezik. Ha t�bbet szeretne megtudni a for ciklusokr�l, itt tal�l n�h�ny linket tov�bbi anyagokhoz:

[Loops on the DHRI Curriculum](https://github.com/DHRI-Curriculum/python/blob/v2.0/sections/08-loops.md)  
[Iteration on Python for Everybody](https://www.py4e.com/html3/05-iterations)  


[<<< El�z�](variables.md) | [K�vetkez� >>>](conditionals.md)
