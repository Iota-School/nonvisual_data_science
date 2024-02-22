[<<< Elõzõ](math.md) | [Következõ >>>](variables.md)

# Típusok

A típusok olyan osztályozások, amelyek segítségével a számítógép megtudhatja, hogy a programozó hogyan kíván felhasználni egy adatot. Gondolhatunk rájuk úgy is, mint adattípusokra.

Az elõzõ részben már láttunk egy típust: az egész számot. Ebben a szakaszban további négyet ismerünk meg: a lebegõpontos számot, a karakterláncot, a boolét és a listát.

Írja be az alábbi sorok mindegyikét, nyomja le az `Enter` billentyût, és figyeljen a kimenetre:

```python
type(1)
```

(Ez a "type" szó, egy nyitó zárójel, az 1-es szám és egy zárójel).

```python
type(1.0)
```

(Ez a "type" szó, egy nyitó zárójel, az 1-es szám, egy tizedesjegy, egy nulla, majd egy záró zárójel.)

```python
type("hello!")
```

(Ez a "type" szó, egy nyitó zárójel, egy idézõjel, a "hello" szó, egy másik idézõjel, majd egy záró zárójel.)

```python
type(True)
```

(Ez a `type` szó, egy nyitó zárójel , a `True` szó nagy T-vel, és egy záró zárójel.)

```python
type([1, 2, 3])
```
```

(Ez a `típus` szó, egy nyitó zárójel , egy nyitó szögletes zárójel, az 1-es szám, egy vesszõ, a 2-es szám, egy vesszõ, a 3-as szám, egy záró szögletes zárójel és egy záró zárójel.


## Típusleírások

Ezek a sorok mindegyike más-más típust jelöl:

integer: `1`

Az egész számok tizedesjegy nélküli számok, például 4 vagy 5.

Lebegõ: `1.0`

A lebegõszámok tizedesjegyekkel rendelkezõ számok, és egy kicsit másképp kezelendõk, mint az egész számok.

String: `"hello!"`

A karakterláncok karakterek tetszõleges halmazai, például betûk, számok és szimbólumok. Úgy gondolhatunk rájuk, mint a szöveg tárolásának módjára.

Boolean: "Igaz" és "Hamis".

A Boolean egy divatos kifejezés az "igaz" vagy "hamis", illetve az "igazságosságot" és a "hamisságot" jelentõ értékekre.

Lista: `[1, 2, 3]`

A lista, értékek rendezett gyûjteménye. Bármilyen típusú értéket betehetsz egy listába: `["rózsa", "százszorszép", "boglárka"]` is egy érvényes lista. (Ez egy lista, amely három karakterláncot tartalmaz.)

Ne aggódjon amiatt, hogy megpróbálja aktívan megjegyezni ezeket a típusokat. A következõ szakaszokban sorban mindegyikükkel dolgozunk majd.

## Mi a helyzet a type()-val?

A fentebb használt zárójeles `type()` szöveg egy függvény. A függvényekre Pythonban többféleképpen is gondolhatunk:

1. Egy módja annak, hogy valamit elvégezzünk Pythonban.
2. Egy mód arra, hogy valamilyen kódot elmentsenek újrafelhasználásra.
3. A bemenet fogadásának, a bemenet átalakításának és a kimenet visszaadásának módja. A bemenet a zárójelek közé kerül `()`.

Ezek mind érvényes gondolkodásmódok a függvényekrõl. Egyelõre talán csak úgy érdemes a függvényre gondolni, mint egy Pythonban végzett mûvelet végrehajtására.

[<<< Elõzõ](math.md) | [Következõ >>>](variables.md)
