[<<< El�z�](indexing.md) | [K�vetkez� >>>](line.md)

# Korrel�ci�

Az adattudom�nyban gyakori technika k�t numerikus v�ltoz� k�z�tti korrel�ci� vagy line�ris kapcsolat meghat�roz�sa. Ha azt mondjuk, hogy egy kapcsolat line�ris, az azt jelenti, hogy a kapcsolat egy meredeks�ggel vagy egyenessel jelezhet�. Egyszer�bben fogalmazva, a korrel�ci� megmutatja, hogy az egyik v�ltoz� kapcsolatban van-e azzal, hogy egy m�sik v�ltoz� n�vekszik, cs�kken vagy nem v�ltozik, �s azt is, hogy mennyivel.

## Numerikus oszlopok korrel�ci�ja

A Pearson-korrel�ci� k�t v�ltoz� k�z�tti kapcsolat ir�ny�t �s er�ss�g�t �rja le. 

Az ir�nyt tekintve a korrel�ci� lehet:

- Pozit�v: Az egyik v�ltoz� n�veked�se korrel�l a m�sik v�ltoz� n�veked�s�vel.
- Negat�v: Az egyik v�ltoz� n�veked�se a m�sik v�ltoz� cs�kken�s�vel korrel�l.
- Nincs korrel�ci�: Az egyik v�ltoz� nem f�gg �ssze a m�sik v�ltoz� n�veked�s�vel vagy cs�kken�s�vel.

A Pearson-korrel�ci�t -1,0 �s 1,0 k�z�tti tizedes sz�mmal fejezik ki. Ha a sz�m negat�v, a korrel�ci� negat�v. Ha a sz�m pozit�v, a korrel�ci� pozit�v. Az 1,0 azt jelzi, hogy a k�t v�ltoz� t�k�letesen korrel�l egym�ssal, a nulla pedig azt, hogy a k�t v�ltoz� egy�ltal�n nem korrel�l egym�ssal.

## A korrel�ci� megtal�l�sa

A Pandas seg�ts�g�vel kisz�m�thatjuk a Pearson-korrel�ci�t k�t numerikus adatokat tartalmaz� oszlop k�z�tt. Pr�b�ljuk ki ezt most k�t olyan oszlopon, amelyek �gy t�nik, hogy kapcsolatban lehetnek egym�ssal. 

```python
df.number_of_reviews.corr(df.reviews_per_month)
```

A fentiekben a `corr()` m�dszert haszn�ljuk az egyik oszlopunkon, majd hozz�adunk egy m�sodik oszlopot. Ez a k�t oszlop k�pviseli a k�t v�ltoz�t.

A kimenet, `0,5498675063773879`, k�zepes vagy er�s korrel�ci�t sugall a k�t v�ltoz� k�z�tt. Ennek intuit�v �rtelme van: �gy t�nik, hogy a sok havi �rt�kel�s t�bb teljes �rt�kel�st eredm�nyez. A v�ltoz�k val�sz�n�leg nem teljesen korrel�lnak egym�ssal m�s relev�ns t�nyez�k miatt, mint p�ld�ul a list�z�s ideje.

Pr�b�ljuk meg a korrel�ci�t k�t tov�bbi v�ltoz�val: az �rral �s az �rt�kel�sek sz�m�val.

```python
df.price.corr(df.number_of_reviews)
```

Az eredm�ny, `-0,04795422658266219`, arra utal, hogy a k�t v�ltoz� nem korrel�l egym�ssal, vagy nagyon gyenge negat�v korrel�ci�ban van.

A sz�r�sdiagramokat gyakran haszn�lj�k k�t v�ltoz� k�z�tti korrelat�v kapcsolatok szeml�ltet�s�re. Azonban a k�t v�ltoz� k�z�tti korrel�ci� kisz�m�t�sa, mint a fentiekben, szint�n jelent�s inform�ci�t adhat a kapcsolatr�l. A vizu�lis sz�r�sdiagram n�ha m�s mint�zatokat is jelezhet, p�ld�ul a kiugr� �rt�kek jelenl�t�t. A variabilit�si m�rt�kek, p�ld�ul a sz�r�s, a variancia �s az interkvartilis tartom�ny (IQR) kisz�m�t�sa szint�n hasznos lehet a numerikus adatok felt�r�sa sor�n. 

[<<< El�z�](indexing.md) | [K�vetkez� >>>](line.md)
