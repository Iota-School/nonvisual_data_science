[<<< Elõzõ](repl.md) | [Következõ >>>](math.md)

# Interakció és áttekintés

## IPython indítása

A workshop ezen szakaszához az IPython REPL-ben kell lennie. Ez azt jelenti, hogy a következõ lépéseket kell követnie:

1. Nyissa meg az Anaconda promptot a Start menübõl. Meg kell nyílnia egy konzolos ablaknak.
2. Írja be az `ipython` szót (csupa kisbetûvel), és nyomja meg az Entert.
3. Akkor folytathatja, ha a következõ üzenetet érzékeli:

	```
	Python 3.8.8 (alapértelmezett, 2021. ápr. 13.),
	15:08:03) [MSC v.1916 64 bit (AMD64)]

	További információkért írja be a copyright, credits vagy license szót.

	IPython 7.22.0 -- Egy továbbfejlesztett interaktív Python. A segítségért írja be a ? jelet.
	A [1]-ben:
	```

## Egy kis matek

Kezdjük a Pythonnal való beszélgetésünket egy kis matematikával. Írjuk be a következõket a promptba:

```
2 + 2
```

majd nyomjuk le az "Enter"-t. Valami olyasmit kell hallania, mint a következõ:

```
Out[1]: 4

In [2]: 
```

A kimenet elsõre kissé zavaró lehet, mivel a hallott számok egy része azzal függ össze, hogy hol tartunk a Pythonnal folytatott beszélgetésünkben. A kimenet, amit vissza tudunk állítani, három sorból áll. Az elsõ ilyen a következõképpen hangzik:

```
Out[1]: 4
```

Az `Out[1]` rész azt mondja, hogy ez a Python-folyamat elsõ interakciójának kimenete. A `4` a mi kimenetünk, a `2 + 2` összeadásának eredménye.

Az eredményünk után egy üres sor következik. Ezután az IPython további bemenetet kér tõlünk a következõkkel: A [2]-ben: `.

Próbáljunk meg egy másik bemenetet. Írjunk be egy idézõjelet, majd írjuk le a `hello` szót, majd írjunk be még egy idézõjelet. A bemenetünknek a következõnek kell lennie:

```
"hello"
```

Most a következõt kell hallania:

```
Out[2]: 'hello'

In [3]: 
```

Itt a `"hello"-t adtuk meg bemenetként. A Python visszhangozta a bemenetünket.

Az IPython REPL-lel való minden interakció két részbõl áll: egy bemenetbõl és egy kimenetbõl. A bemenetet tartalmazó sorok a `In` szóval és egy zárójelben lévõ számmal kezdõdnek. A kimenettel rendelkezõ sorok a `Out` szóval és egy zárójelben lévõ számmal kezdõdnek. A szám azt jelzi, hogy hol vagyunk a munkamenetben, az `1` számmal kezdve és felfelé számolva.

Az IPython és a Jupyter ökoszisztémában a bemenet és a kimenet párosítását `celláknak` nevezik. Az IPythonban az egyes cellákat (bemenet és kimenet) egy üres sor választja el egymástól.

## A kimenet felfedezése

Használjuk az NVDA áttekintõ kurzorát, hogy megvizsgáljuk, mit írtunk eddig. Ez a készség egyre fontosabb lesz, ahogy a Python egyre összetettebb kimenetet küld vissza nekünk.

Az NVDA-nak két üzemmódja van, az asztali és a laptop. Az asztali üzemmód megköveteli, hogy a gépünkön legyen numpad, vagy hogy külsõ numpadot csatlakoztassunk. Úgy találom, hogy az asztali parancsikonok általában intuitívabbak. A laptopos elrendezés azonban minden gépen mûködik, és nem igényel numpadot. 

Alapértelmezés szerint az NVDA billentyû a "Insert". Ez azonban megváltoztatható az NVDA beállításaiban. Szerintem a laptopokon a `Capslock` billentyû jó NVDA-billentyû. A gyorsbillentyûk leírásakor egyszerûen csak az NVDA billentyût mondom.

Az elsõ három gyorsbillentyû, amelyet használni fogunk, lehetõvé teszi a soronkénti áttekintést. 

Az aktuális sor áttekintéséhez:

NVDA + shift + .
NVDA + NUMPAD 8

Ez NVDA, shift, pont laptopos elrendezés esetén, illetve NVDA és numpad 8 asztali elrendezés esetén. Ez a parancs hangosan felolvassa azt a sort, ahol az áttekintõ kurzor éppen áll.

Az áttekintõ kurzor egy sorral feljebb mozgatása:

NVDA + fel
NVDA + NUMPAD7
az érintõképernyõn felfelé pöccintés

Laptopon nyomja meg az NVDA és a felfelé nyíl billentyût. Asztali számítógépen nyomja meg az NVDA és a numpad 7 billentyût. Ha érintõképernyõje van, akkor egyszer felfelé is pöccinthet.

Az áttekintõ kurzor egy sorral lejjebb mozgatása:

NVDA + le
NVDA + NUMPAD9
érintõképernyõn lefelé pöccintés

Laptopon ez az NVDA plusz a lefelé nyíl. Asztali számítógépen ez az NVDA és a 9-es szám. Érintõképernyõn egyszer lefelé öccintés.

## 1. gyakorlat: A REPL felfedezése

Most szánjunk öt percet arra, hogy ezekkel a parancsikonokkal felfedezzük az aktuális REPL-t. Két "cellának" kell lennie, az egyikben egy kis matematika, a másikban pedig a "hello" szó, mint input és output. Ne feledje, hogy a bemeneti/kimeneti párokat (cellákat) egy üres sor választja el egymástól (az NVDA-ban a `blank` szót fogja hallani az áttekintéskor). Ha elég messzire megy vissza, akkor a REPL munkamenet indulásakor megjelenõ szöveget kezdheti megtekinteni. A legfelsõ sorban meg kell találnia, hogy a Python aktuális verzióját használod.

A mûhelymunka során megtanulunk még néhány áttekintõ gyorsbillentyût, de ha már ismer más NVDA áttekintõ parancsokat, nyugodtan használhatja azokat. 

[<<< Elõzõ](repl.md) | [Következõ >>>](math.md)
