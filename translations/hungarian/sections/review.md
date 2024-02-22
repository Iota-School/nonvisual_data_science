[<<< El�z�](repl.md) | [K�vetkez� >>>](math.md)

# Interakci� �s �ttekint�s

## IPython ind�t�sa

A workshop ezen szakasz�hoz az IPython REPL-ben kell lennie. Ez azt jelenti, hogy a k�vetkez� l�p�seket kell k�vetnie:

1. Nyissa meg az Anaconda promptot a Start men�b�l. Meg kell ny�lnia egy konzolos ablaknak.
2. �rja be az `ipython` sz�t (csupa kisbet�vel), �s nyomja meg az Entert.
3. Akkor folytathatja, ha a k�vetkez� �zenetet �rz�keli:

	```
	Python 3.8.8 (alap�rtelmezett, 2021. �pr. 13.),
	15:08:03) [MSC v.1916 64 bit (AMD64)]

	Tov�bbi inform�ci�k�rt �rja be a copyright, credits vagy license sz�t.

	IPython 7.22.0 -- Egy tov�bbfejlesztett interakt�v Python. A seg�ts�g�rt �rja be a ? jelet.
	A [1]-ben:
	```

## Egy kis matek

Kezdj�k a Pythonnal val� besz�lget�s�nket egy kis matematik�val. �rjuk be a k�vetkez�ket a promptba:

```
2 + 2
```

majd nyomjuk le az "Enter"-t. Valami olyasmit kell hallania, mint a k�vetkez�:

```
Out[1]: 4

In [2]: 
```

A kimenet els�re kiss� zavar� lehet, mivel a hallott sz�mok egy r�sze azzal f�gg �ssze, hogy hol tartunk a Pythonnal folytatott besz�lget�s�nkben. A kimenet, amit vissza tudunk �ll�tani, h�rom sorb�l �ll. Az els� ilyen a k�vetkez�k�ppen hangzik:

```
Out[1]: 4
```

Az `Out[1]` r�sz azt mondja, hogy ez a Python-folyamat els� interakci�j�nak kimenete. A `4` a mi kimenet�nk, a `2 + 2` �sszead�s�nak eredm�nye.

Az eredm�ny�nk ut�n egy �res sor k�vetkezik. Ezut�n az IPython tov�bbi bemenetet k�r t�l�nk a k�vetkez�kkel: A [2]-ben: `.

Pr�b�ljunk meg egy m�sik bemenetet. �rjunk be egy id�z�jelet, majd �rjuk le a `hello` sz�t, majd �rjunk be m�g egy id�z�jelet. A bemenet�nknek a k�vetkez�nek kell lennie:

```
"hello"
```

Most a k�vetkez�t kell hallania:

```
Out[2]: 'hello'

In [3]: 
```

Itt a `"hello"-t adtuk meg bemenetk�nt. A Python visszhangozta a bemenet�nket.

Az IPython REPL-lel val� minden interakci� k�t r�szb�l �ll: egy bemenetb�l �s egy kimenetb�l. A bemenetet tartalmaz� sorok a `In` sz�val �s egy z�r�jelben l�v� sz�mmal kezd�dnek. A kimenettel rendelkez� sorok a `Out` sz�val �s egy z�r�jelben l�v� sz�mmal kezd�dnek. A sz�m azt jelzi, hogy hol vagyunk a munkamenetben, az `1` sz�mmal kezdve �s felfel� sz�molva.

Az IPython �s a Jupyter �kosziszt�m�ban a bemenet �s a kimenet p�ros�t�s�t `cell�knak` nevezik. Az IPythonban az egyes cell�kat (bemenet �s kimenet) egy �res sor v�lasztja el egym�st�l.

## A kimenet felfedez�se

Haszn�ljuk az NVDA �ttekint� kurzor�t, hogy megvizsg�ljuk, mit �rtunk eddig. Ez a k�szs�g egyre fontosabb lesz, ahogy a Python egyre �sszetettebb kimenetet k�ld vissza nek�nk.

Az NVDA-nak k�t �zemm�dja van, az asztali �s a laptop. Az asztali �zemm�d megk�veteli, hogy a g�p�nk�n legyen numpad, vagy hogy k�ls� numpadot csatlakoztassunk. �gy tal�lom, hogy az asztali parancsikonok �ltal�ban intuit�vabbak. A laptopos elrendez�s azonban minden g�pen m�k�dik, �s nem ig�nyel numpadot. 

Alap�rtelmez�s szerint az NVDA billenty� a "Insert". Ez azonban megv�ltoztathat� az NVDA be�ll�t�saiban. Szerintem a laptopokon a `Capslock` billenty� j� NVDA-billenty�. A gyorsbillenty�k le�r�sakor egyszer�en csak az NVDA billenty�t mondom.

Az els� h�rom gyorsbillenty�, amelyet haszn�lni fogunk, lehet�v� teszi a soronk�nti �ttekint�st. 

Az aktu�lis sor �ttekint�s�hez:

NVDA + shift + .
NVDA + NUMPAD 8

Ez NVDA, shift, pont laptopos elrendez�s eset�n, illetve NVDA �s numpad 8 asztali elrendez�s eset�n. Ez a parancs hangosan felolvassa azt a sort, ahol az �ttekint� kurzor �ppen �ll.

Az �ttekint� kurzor egy sorral feljebb mozgat�sa:

NVDA + fel
NVDA + NUMPAD7
az �rint�k�perny�n felfel� p�ccint�s

Laptopon nyomja meg az NVDA �s a felfel� ny�l billenty�t. Asztali sz�m�t�g�pen nyomja meg az NVDA �s a numpad 7 billenty�t. Ha �rint�k�perny�je van, akkor egyszer felfel� is p�ccinthet.

Az �ttekint� kurzor egy sorral lejjebb mozgat�sa:

NVDA + le
NVDA + NUMPAD9
�rint�k�perny�n lefel� p�ccint�s

Laptopon ez az NVDA plusz a lefel� ny�l. Asztali sz�m�t�g�pen ez az NVDA �s a 9-es sz�m. �rint�k�perny�n egyszer lefel� �ccint�s.

## 1. gyakorlat: A REPL felfedez�se

Most sz�njunk �t percet arra, hogy ezekkel a parancsikonokkal felfedezz�k az aktu�lis REPL-t. K�t "cell�nak" kell lennie, az egyikben egy kis matematika, a m�sikban pedig a "hello" sz�, mint input �s output. Ne feledje, hogy a bemeneti/kimeneti p�rokat (cell�kat) egy �res sor v�lasztja el egym�st�l (az NVDA-ban a `blank` sz�t fogja hallani az �ttekint�skor). Ha el�g messzire megy vissza, akkor a REPL munkamenet indul�sakor megjelen� sz�veget kezdheti megtekinteni. A legfels� sorban meg kell tal�lnia, hogy a Python aktu�lis verzi�j�t haszn�lod.

A m�helymunka sor�n megtanulunk m�g n�h�ny �ttekint� gyorsbillenty�t, de ha m�r ismer m�s NVDA �ttekint� parancsokat, nyugodtan haszn�lhatja azokat. 

[<<< El�z�](repl.md) | [K�vetkez� >>>](math.md)
