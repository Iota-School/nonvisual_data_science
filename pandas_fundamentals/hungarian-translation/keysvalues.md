[<<< El�z�](series.md) | [K�vetkez� >>>](creating_dataframe.md)

# Kulcsok �s �rt�kek

Az adattudom�nyban �s t�gabban a programoz�sban gyakori feladat az adatok keres�se. Az adatok keres�s�nek egyik technik�ja, amit kor�bban m�r tanultunk, a szeletel�s. A szeletel�s sor�n megadunk egy eg�sz sz�mot, amely egy elem hely�nek felel meg egy list�ban.

Az adatok keres�s�nek m�sik m�dja a kulcs-�rt�k p�ros, amelyben egy kulcs (egy c�mke) seg�ts�g�vel �rhet�nk el egy �rt�ket (egy adatot).

## Sz�t�rak

A sz�t�r egy olyan adatt�pus, amely lehet�v� teszi egy kulcs (egyedi c�mke) megad�s�t egy �rt�k (adat) megkeres�s�hez. 

Pr�b�lja meg a k�vetkez�ket be�rni, hogy l�trehozzon egy telefonk�nyvet sz�t�r form�j�ban. (Ha m�g sosem haszn�lt telefonk�nyvet, akkor az lehet�v� teszi, hogy egy szem�ly neve alapj�n telefonsz�mot keressen.)

```python
phone_book = {
    "Patrick": 9999999999,
    "Sarah": 3333333333,
    "Guido": 5555555555,
}
```

L�sd a dictionary.md nev� f�jlt.

A sz�t�r szintaxisa a k�vetkez�:

- A sz�t�rat sz�gletes z�r�jelek nyitj�k �s z�rj�k. Az angol billenty�zeten ezek a karakterek ugyanazon a billenty�n vannak, mint a sz�gletes z�r�jelek, �s a `Shift` lenyomva tart�s�t ig�nylik.
- A sz�t�r kulcsai leggyakrabban eg�sz sz�mok vagy karakterl�ncok.
- A sz�t�r �rt�kei b�rmilyen adatt�pus�ak lehetnek.
- A kulcsot az �rt�kt�l `:` (kett�spont) v�lasztja el. 
- Minden egyes kulcs-�rt�k p�rost vessz�vel v�lasztunk el a k�vetkez�t�l.

## Adatok keres�se a sz�t�rban

Az adatok keres�s�hez a sz�t�runkban a k�vetkez� szintaxist haszn�ljuk:

```python
phone_book["Patrick"]
```

Ez a sz�t�rv�ltoz�nk, majd egy nyit� sz�gletes z�r�jel, azt�n a kulcs karakterl�nck�nt, majd egy z�r�jel.

A fentiek kimenet�nek a mi �rt�k�nknek kell lennie, ebben az esetben `9999999999`.

[<<< El�z�](series.md) | [K�vetkez� >>>](creating_dataframe.md)