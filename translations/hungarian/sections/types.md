[<<< El�z�](math.md) | [K�vetkez� >>>](variables.md)

# T�pusok

A t�pusok olyan oszt�lyoz�sok, amelyek seg�ts�g�vel a sz�m�t�g�p megtudhatja, hogy a programoz� hogyan k�v�n felhaszn�lni egy adatot. Gondolhatunk r�juk �gy is, mint adatt�pusokra.

Az el�z� r�szben m�r l�ttunk egy t�pust: az eg�sz sz�mot. Ebben a szakaszban tov�bbi n�gyet ismer�nk meg: a lebeg�pontos sz�mot, a karakterl�ncot, a bool�t �s a list�t.

�rja be az al�bbi sorok mindegyik�t, nyomja le az `Enter` billenty�t, �s figyeljen a kimenetre:

```python
type(1)
```

(Ez a "type" sz�, egy nyit� z�r�jel, az 1-es sz�m �s egy z�r�jel).

```python
type(1.0)
```

(Ez a "type" sz�, egy nyit� z�r�jel, az 1-es sz�m, egy tizedesjegy, egy nulla, majd egy z�r� z�r�jel.)

```python
type("hello!")
```

(Ez a "type" sz�, egy nyit� z�r�jel, egy id�z�jel, a "hello" sz�, egy m�sik id�z�jel, majd egy z�r� z�r�jel.)

```python
type(True)
```

(Ez a `type` sz�, egy nyit� z�r�jel , a `True` sz� nagy T-vel, �s egy z�r� z�r�jel.)

```python
type([1, 2, 3])
```
```

(Ez a `t�pus` sz�, egy nyit� z�r�jel , egy nyit� sz�gletes z�r�jel, az 1-es sz�m, egy vessz�, a 2-es sz�m, egy vessz�, a 3-as sz�m, egy z�r� sz�gletes z�r�jel �s egy z�r� z�r�jel.


## T�pusle�r�sok

Ezek a sorok mindegyike m�s-m�s t�pust jel�l:

integer: `1`

Az eg�sz sz�mok tizedesjegy n�lk�li sz�mok, p�ld�ul 4 vagy 5.

Lebeg�: `1.0`

A lebeg�sz�mok tizedesjegyekkel rendelkez� sz�mok, �s egy kicsit m�sk�pp kezelend�k, mint az eg�sz sz�mok.

String: `"hello!"`

A karakterl�ncok karakterek tetsz�leges halmazai, p�ld�ul bet�k, sz�mok �s szimb�lumok. �gy gondolhatunk r�juk, mint a sz�veg t�rol�s�nak m�dj�ra.

Boolean: "Igaz" �s "Hamis".

A Boolean egy divatos kifejez�s az "igaz" vagy "hamis", illetve az "igazs�goss�got" �s a "hamiss�got" jelent� �rt�kekre.

Lista: `[1, 2, 3]`

A lista, �rt�kek rendezett gy�jtem�nye. B�rmilyen t�pus� �rt�ket betehetsz egy list�ba: `["r�zsa", "sz�zszorsz�p", "bogl�rka"]` is egy �rv�nyes lista. (Ez egy lista, amely h�rom karakterl�ncot tartalmaz.)

Ne agg�djon amiatt, hogy megpr�b�lja akt�van megjegyezni ezeket a t�pusokat. A k�vetkez� szakaszokban sorban mindegyik�kkel dolgozunk majd.

## Mi a helyzet a type()-val?

A fentebb haszn�lt z�r�jeles `type()` sz�veg egy f�ggv�ny. A f�ggv�nyekre Pythonban t�bbf�lek�ppen is gondolhatunk:

1. Egy m�dja annak, hogy valamit elv�gezz�nk Pythonban.
2. Egy m�d arra, hogy valamilyen k�dot elmentsenek �jrafelhaszn�l�sra.
3. A bemenet fogad�s�nak, a bemenet �talak�t�s�nak �s a kimenet visszaad�s�nak m�dja. A bemenet a z�r�jelek k�z� ker�l `()`.

Ezek mind �rv�nyes gondolkod�sm�dok a f�ggv�nyekr�l. Egyel�re tal�n csak �gy �rdemes a f�ggv�nyre gondolni, mint egy Pythonban v�gzett m�velet v�grehajt�s�ra.

[<<< El�z�](math.md) | [K�vetkez� >>>](variables.md)
