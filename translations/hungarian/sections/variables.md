[<<< El�z�](types.md) | [K�vetkez� >>>](lists.md)

# V�ltoz�k

A v�ltoz� egy olyan szimb�lum, amely egy objektumra, p�ld�ul egy karakterl�ncra, eg�sz sz�mra vagy list�ra utal. Alapvet�en ez egy m�dja annak, hogy nevet adjunk az adatoknak. Ha az adatnak egyszer nevet adtunk, a Python a tov�bbiakban nyomon k�veti azt.

Pr�b�ljuk meg be�rni ezt a sort:

```python
x = 5
```

Ez egy x, egy sz�k�z, egy egyenl�s�gjel, egy sz�k�z �s egy 5.

Ebb�l a sorb�l nem hallhatunk semmilyen kimenetet. (Vagyis csak a `In` sz�t �s egy sz�mot fogsz hallani, mik�zben a Python �j bemenetre v�r.)

Most �rjuk be az `x` bet�t, �s nyomjuk meg az `Enter` billenty�t. Hallanunk kell az `5`-�t, ami az `x` v�ltoz�ba mentett adat.

Pr�b�ljuk ki ezeket a sorokat:

```python
x + 10
```

Kimenetk�nt a `15` �rt�ket kell hallanod.

Ments�nk el egy sztringet `y` v�ltoz�k�nt:

```python
y = "hello"
```

Most pr�b�ljuk meg el�rni az adatokat az `y` be�r�s�val �s az `Enter` lenyom�s�val. Kimenetk�nt a `"hello"-t kell hallanunk.

Pr�b�lja meg a k�vetkez� sor be�r�s�t:

```python
y + " �s viszl�t"
```

Ez egy `y`, egy sz�k�z, egy plusz, egy sz�k�z, egy id�z�jel, a `"�s viszl�t"` szavak, �s egy �jabb id�z�jel. Kimenetk�nt a `"hello �s viszl�t"-t kell hallanod.


## Magyar�zat

A `=` jel seg�ts�g�vel olyan szimb�lumokat rendelhet�nk adatokhoz, mint az `x` �s az `y`.

A v�ltoz�k hosszabb szavak is lehetnek:

```
reggeli = ["sonka", "toj�s", "pir�t�s"]
```

Ha a fenti sort futtatjuk, akkor egy h�rom karakterl�ncot tartalmaz� list�t rendel�nk a `reggeli` v�ltoz�hoz.

A v�ltoz�k tartalmazhatnak bet�ket, sz�mokat �s al�h�z�sokat, de bet�vel kell kezd�dni�k. 

## K�rd�s: Hol laknak a v�ltoz�k?

Amikor hozz�rendel�nk egy v�ltoz�t, a Python elkezdi sz�mon tartani azt. A v�ltoz� neve �s a hozz� tartoz� adatok a sz�m�t�g�p mem�ri�j�ban t�rol�dnak. Ha bez�rja az IPython folyamatot, az �sszes v�ltoz� �s egy�b hozz�rendel�s t�rl�dik, �s �j munkamenetet kezd. Vannak m�dok a munkamenet ment�s�re, hogy k�s�bb folytathassa, de ezekr�l k�s�bb besz�l�nk err�l.

## K�rd�s: Mi a helyzet a sz�k�z�kkel?

A fenti v�ltoz� hozz�rendel�si sorokban az egyenl�s�gjel el�tt �s ut�n sz�k�zt tettem be. Ezek a sorok teljesen m�k�dnek sz�k�z�k n�lk�l is. A l�t� emberek azonban �gy tal�lj�k, hogy a sz�k�z�k megk�nny�tik a sorok olvas�s�t, �s j� st�lusnak sz�m�t, ha ezeket a sz�k�z�ket beillesztj�k. J� lehet, ha szok�ss� v�lik a sz�k�z�k hozz�ad�sa, mivel �gy k�nnyebben olvashat�v� �s professzion�lisabb� v�lik a k�d. Ha azonban saj�t magadnak �rsz k�dot, vagy egy eszk�zzel (az �gynevezett linterrel) akarod rendbe tenni a k�dodat �r�s ut�n, �gy d�nthetsz, hogy elhagyod a sz�k�z�ket, �s azt vettem �szre, hogy sok vak programoz� elhagyja ezeket a sz�k�z�ket.

[<<< El�z�](types.md) | [K�vetkez� >>>](lists.md)
