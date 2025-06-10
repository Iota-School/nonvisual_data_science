[<<< Elõzõ](series.md) | [Következõ >>>](creating_dataframe.md)

# Kulcsok és értékek

Az adattudományban és tágabban a programozásban gyakori feladat az adatok keresése. Az adatok keresésének egyik technikája, amit korábban már tanultunk, a szeletelés. A szeletelés során megadunk egy egész számot, amely egy elem helyének felel meg egy listában.

Az adatok keresésének másik módja a kulcs-érték páros, amelyben egy kulcs (egy címke) segítségével érhetünk el egy értéket (egy adatot).

## Szótárak

A szótár egy olyan adattípus, amely lehetõvé teszi egy kulcs (egyedi címke) megadását egy érték (adat) megkereséséhez. 

Próbálja meg a következõket beírni, hogy létrehozzon egy telefonkönyvet szótár formájában. (Ha még sosem használt telefonkönyvet, akkor az lehetõvé teszi, hogy egy személy neve alapján telefonszámot keressen.)

```python
phone_book = {
    "Patrick": 9999999999,
    "Sarah": 3333333333,
    "Guido": 5555555555,
}
```

Lásd a dictionary.md nevû fájlt.

A szótár szintaxisa a következõ:

- A szótárat szögletes zárójelek nyitják és zárják. Az angol billentyûzeten ezek a karakterek ugyanazon a billentyûn vannak, mint a szögletes zárójelek, és a `Shift` lenyomva tartását igénylik.
- A szótár kulcsai leggyakrabban egész számok vagy karakterláncok.
- A szótár értékei bármilyen adattípusúak lehetnek.
- A kulcsot az értéktõl `:` (kettõspont) választja el. 
- Minden egyes kulcs-érték párost vesszõvel választunk el a következõtõl.

## Adatok keresése a szótárban

Az adatok kereséséhez a szótárunkban a következõ szintaxist használjuk:

```python
phone_book["Patrick"]
```

Ez a szótárváltozónk, majd egy nyitó szögletes zárójel, aztán a kulcs karakterláncként, majd egy zárójel.

A fentiek kimenetének a mi értékünknek kell lennie, ebben az esetben `9999999999`.

[<<< Elõzõ](series.md) | [Következõ >>>](creating_dataframe.md)