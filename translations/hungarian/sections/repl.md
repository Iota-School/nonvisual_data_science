[<<< El�z�](installation.md) | [K�vetkez� >>>](review.md)

# Az IPython REPL ind�t�sa

## A konzol ind�t�sa

Ezen a ponton m�r telep�tve kell lennie az NVDA-nak �s az Anacond�nak. (Ha nem, akkor [k�vesse az el�z� oldalon tal�lhat� utas�t�sokat](installation.md)).

A workshop sor�n v�gig be lesz kapcsolva az NVDA. Az NVDA bekapcsol�s�hoz nyomja meg a Windows gombot, �rja be az NVDA-t, �s nyomja le az Entert.

Az Anaconda Promptben fogunk dolgozni a Pythonnal. Az Anaconda Prompt megnyit�s�hoz nyomja meg a Windows gombot, �rja be az "anaconda prompt" sz�t, �s nyomja meg az Entert.

Ha az NVDA fut, amikor megnyitja az Anaconda promptot, akkor olyan kimenetet fog hallani, amely tartalmazza a 
C:\Users\ <az �n felhaszn�l�neve> kimenetet. �gy is ellen�rizheti, hogy j� helyen van-e, ha az NVDA gombot alap�rtelmez�s szerint insert) �s "t" lenyomva megkapja az alkalmaz�s c�m�t, amelynek Anaconda Promptnak kell lennie.

## Python ind�t�sa

Az Anaconda Prompt megnyit�sakor a Windowshoz tartoz� cmd parancssori fel�let egy speci�lis v�ltozat�val l�p�nk kapcsolatba. Ez a verzi� hozz�f�r�st biztos�t sz�mos, a Pythonhoz kapcsol�d� telep�tett seg�dprogramhoz.

A Python ind�t�s�hoz �rjuk be az al�bbi sort �s nyomjuk le az `Enter` billenty�t.

```cmd
ipython
```

Ez a `python` sz�, de egy `i` bet�vel az elej�n. Nincsenek sz�k�z�k, �s minden bet� kisbet�s. (Amint majd l�tni fogod, a parancssorban �s a Pythonnal val� munkav�gz�s sor�n a dolgokat pontosan meg kell hat�roznod).

Miut�n be�rtad ezt a parancsot, k�zvetlen�l egy fut� Python-folyamattal l�psz kapcsolatba, �s k�szen �llsz a k�vetkez� szakaszban elv�gzend� munk�ra. El�sz�r azonban ismerkedj�nk meg azzal, hogy mi is az a parancssor, �s mire val�.

## Mi az a REPL?

A parancssort sokf�lek�ppen fogjuk nevezni: termin�l, shell, CLI (a parancssori fel�let r�vid�t�se) �s konzol. Alapvet�en a parancssor a sz�m�t�g�ppel val� interakci� m�dja sz�veges parancsok seg�ts�g�vel. A parancssori interf�sz, vagy CLI, ellent�tben �llhat a grafikus felhaszn�l�i fel�lettel, vagy GUI-val, amelyet tal�n jobban ismer.

A programoz�sban a parancssort n�ha REPL-nek nevezik, ami a Read, Evaluate, Print, Loop (olvas�s, ki�rt�kel�s, nyomtat�s, ciklus) r�vid�t�se. Ez arra az alapvet� m�dra utal, ahogyan a parancssorral n�gy l�p�sben interakci�ba l�p�nk:

1. Olvassa be a felhaszn�l� bemenet�t. (A felhaszn�l� be�r egy parancsot, majd megnyomja az `Enter` billenty�t.)
2. A bemenet ki�rt�kel�se. (A parancssor �tveszi a bemenetet, �s v�grehajt valamilyen feladatot.)
3. Ki�rja a v�laszt. (A parancssor visszaad valamilyen inform�ci�t a felhaszn�l�nak.)
4. Visszat�r�s az els� l�p�shez, ahol a parancssor v�rja a felhaszn�l� bemenet�t.

Alapvet�en a megk�zel�t�s itt egy besz�lget�s a sz�m�t�g�ppel. �n be�r valamit, a sz�m�t�g�p pedig v�grehajt valamilyen folyamatot, �s v�laszt ad. Ezut�n folytathatja a besz�lget�st tov�bbi input megad�s�val, �s �gy tov�bb.

Ebben a workshopban v�gig a Python REPL-t fogjuk haszn�lni. Ez azt jelenti, hogy besz�lget�st folytatunk a g�ppel, ahol mi adjuk meg a bemenetet, a sz�m�t�g�p pedig a kimenetet.

## Megjegyz�s a Windowsr�l

A Windows alap�rtelmez�s szerint k�t parancssori fel�lettel rendelkezik. Az els�, a `cmd.exe` vagy parancssor m�r r�g�ta l�tezik. Ez a fel�let funkcion�lisan hasonl� a DOS oper�ci�s rendszer parancssori fel�let�hez. A Windows egy modernebb parancssori fel�lettel is rendelkezik, amelyet Powershellnek h�vnak.

Az Anaconda Prompt megnyit�sakor a `cmd.exe` egy olyan v�ltozat�val l�psz kapcsolatba, amelybe tov�bbi, a Pythonhoz kapcsol�d� parancsokat t�lt�ttek be. Nem l�p�nk k�zvetlen kapcsolatba a Pythonnal, am�g be nem �rjuk az `ipython` parancsot.

[<<< El�z�](installation.md) | [K�vetkez� >>>](review.md)
