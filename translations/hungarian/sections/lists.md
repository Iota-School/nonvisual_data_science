[<<< Elõzõ](variables.md) | [Következõ >>>](conditionals.md)

# Listák

## Listák

Emlékszel a listákra? Így néznek ki:

```python
flowers = ['rose', 'violet', 'buttercup']
```

Menj elõre, és írd be a fenti sort, hogy a `flowers` változóhoz hozzárendelj egy listát, amelyben három karakterlánc van. Ne feledje, hogy mindhárom karakterlánc köré idézõjelet tegyen, és a lista elemeit vesszõvel válassza el egymástól.

Ellenõrizze a listát a `virágok` változó nevének beírásával. A kimenetként a `['rózsa', 'ibolya', 'boglárka']-t kell hallania.

## A hossz megadása

Eddig ebben a workshopban csak egy függvényt használtunk, a `type()` függvényt. Próbáljunk ki egy másikat. Írjuk be a következõ sort:

```python
len(flowers)
```

Ez a `len` szó (a hossz rövidítése), egy nyitó zárójel, a flowers változónk és egy zárójel.

Ha a fentieket futtatjuk, akkor a `3` egész számot kell hallanunk kimenetként. Ez azt jelenti, hogy a listánkban három elem van. 

## Listaszeletelés

A Pythonban a listák egyik hasznos tulajdonsága a listaszeletelés, amely lehetõvé teszi, hogy a listán belül egy bizonyos helyen lévõ konkrét elemeket kiemeljünk. Próbáljuk ki a következõt:

```python
flowers[0]
```

Ez a `virágok` változó neve, egy nyitó szögletes zárójel, az egész szám `0` és egy záró szögletes zárójel. Kimenetként a `rose`-t kell kapnod, mivel ez az elsõ (vagy nulladik) elem a listában. (Zavaró módon a Pythonban és a legtöbb más programozási nyelvben is nulláról kezdõdik a számlálás.)

Próbáljuk meg elérni a lista többi elemét (`violet` és `buttercup`).

A lista végétõl visszafelé számolhatunk negatív számokkal. Például a lista utolsó eleme a `-` lenne.

```python
flowers[-1]
```

## Mi a helyzet a ciklusokkal?

A Pythonban a dolgok elvégzésének gyakori módja az úgynevezett ciklus írása, ami lényegében egy olyan kód, amely egy lista vagy listaszerû objektum minden egyes elemére lefut. A jövõbeli workshopokon a Pandas-t, egy adattudományi könyvtárat (eszközt) fogjuk használni. Bár a Pandas némileg támogatja a ciklusok használatát, saját megközelítései vannak a listákkal és listaszerû objektumokkal való munkához, ezért a Python bevezetõjében nem foglalkozunk a ciklusokkal. 

Bár ebben a workshop-sorozatban nem fogunk ciklussal dolgozni, ezek a Python alapvetõ részét képezik. Ha többet szeretne megtudni a for ciklusokról, itt talál néhány linket további anyagokhoz:

[Loops on the DHRI Curriculum](https://github.com/DHRI-Curriculum/python/blob/v2.0/sections/08-loops.md)  
[Iteration on Python for Everybody](https://www.py4e.com/html3/05-iterations)  


[<<< Elõzõ](variables.md) | [Következõ >>>](conditionals.md)
