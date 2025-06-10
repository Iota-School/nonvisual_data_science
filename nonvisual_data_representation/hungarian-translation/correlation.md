[<<< Elõzõ](indexing.md) | [Következõ >>>](line.md)

# Korreláció

Az adattudományban gyakori technika két numerikus változó közötti korreláció vagy lineáris kapcsolat meghatározása. Ha azt mondjuk, hogy egy kapcsolat lineáris, az azt jelenti, hogy a kapcsolat egy meredekséggel vagy egyenessel jelezhetõ. Egyszerûbben fogalmazva, a korreláció megmutatja, hogy az egyik változó kapcsolatban van-e azzal, hogy egy másik változó növekszik, csökken vagy nem változik, és azt is, hogy mennyivel.

## Numerikus oszlopok korrelációja

A Pearson-korreláció két változó közötti kapcsolat irányát és erõsségét írja le. 

Az irányt tekintve a korreláció lehet:

- Pozitív: Az egyik változó növekedése korrelál a másik változó növekedésével.
- Negatív: Az egyik változó növekedése a másik változó csökkenésével korrelál.
- Nincs korreláció: Az egyik változó nem függ össze a másik változó növekedésével vagy csökkenésével.

A Pearson-korrelációt -1,0 és 1,0 közötti tizedes számmal fejezik ki. Ha a szám negatív, a korreláció negatív. Ha a szám pozitív, a korreláció pozitív. Az 1,0 azt jelzi, hogy a két változó tökéletesen korrelál egymással, a nulla pedig azt, hogy a két változó egyáltalán nem korrelál egymással.

## A korreláció megtalálása

A Pandas segítségével kiszámíthatjuk a Pearson-korrelációt két numerikus adatokat tartalmazó oszlop között. Próbáljuk ki ezt most két olyan oszlopon, amelyek úgy tûnik, hogy kapcsolatban lehetnek egymással. 

```python
df.number_of_reviews.corr(df.reviews_per_month)
```

A fentiekben a `corr()` módszert használjuk az egyik oszlopunkon, majd hozzáadunk egy második oszlopot. Ez a két oszlop képviseli a két változót.

A kimenet, `0,5498675063773879`, közepes vagy erõs korrelációt sugall a két változó között. Ennek intuitív értelme van: úgy tûnik, hogy a sok havi értékelés több teljes értékelést eredményez. A változók valószínûleg nem teljesen korrelálnak egymással más releváns tényezõk miatt, mint például a listázás ideje.

Próbáljuk meg a korrelációt két további változóval: az árral és az értékelések számával.

```python
df.price.corr(df.number_of_reviews)
```

Az eredmény, `-0,04795422658266219`, arra utal, hogy a két változó nem korrelál egymással, vagy nagyon gyenge negatív korrelációban van.

A szórásdiagramokat gyakran használják két változó közötti korrelatív kapcsolatok szemléltetésére. Azonban a két változó közötti korreláció kiszámítása, mint a fentiekben, szintén jelentõs információt adhat a kapcsolatról. A vizuális szórásdiagram néha más mintázatokat is jelezhet, például a kiugró értékek jelenlétét. A variabilitási mértékek, például a szórás, a variancia és az interkvartilis tartomány (IQR) kiszámítása szintén hasznos lehet a numerikus adatok feltárása során. 

[<<< Elõzõ](indexing.md) | [Következõ >>>](line.md)
