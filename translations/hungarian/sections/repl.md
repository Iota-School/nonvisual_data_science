[<<< Elõzõ](installation.md) | [Következõ >>>](review.md)

# Az IPython REPL indítása

## A konzol indítása

Ezen a ponton már telepítve kell lennie az NVDA-nak és az Anacondának. (Ha nem, akkor [kövesse az elõzõ oldalon található utasításokat](installation.md)).

A workshop során végig be lesz kapcsolva az NVDA. Az NVDA bekapcsolásához nyomja meg a Windows gombot, írja be az NVDA-t, és nyomja le az Entert.

Az Anaconda Promptben fogunk dolgozni a Pythonnal. Az Anaconda Prompt megnyitásához nyomja meg a Windows gombot, írja be az "anaconda prompt" szót, és nyomja meg az Entert.

Ha az NVDA fut, amikor megnyitja az Anaconda promptot, akkor olyan kimenetet fog hallani, amely tartalmazza a 
C:\Users\ <az Ön felhasználóneve> kimenetet. Úgy is ellenõrizheti, hogy jó helyen van-e, ha az NVDA gombot alapértelmezés szerint insert) és "t" lenyomva megkapja az alkalmazás címét, amelynek Anaconda Promptnak kell lennie.

## Python indítása

Az Anaconda Prompt megnyitásakor a Windowshoz tartozó cmd parancssori felület egy speciális változatával lépünk kapcsolatba. Ez a verzió hozzáférést biztosít számos, a Pythonhoz kapcsolódó telepített segédprogramhoz.

A Python indításához írjuk be az alábbi sort és nyomjuk le az `Enter` billentyût.

```cmd
ipython
```

Ez a `python` szó, de egy `i` betûvel az elején. Nincsenek szóközök, és minden betû kisbetûs. (Amint majd látni fogod, a parancssorban és a Pythonnal való munkavégzés során a dolgokat pontosan meg kell határoznod).

Miután beírtad ezt a parancsot, közvetlenül egy futó Python-folyamattal lépsz kapcsolatba, és készen állsz a következõ szakaszban elvégzendõ munkára. Elõször azonban ismerkedjünk meg azzal, hogy mi is az a parancssor, és mire való.

## Mi az a REPL?

A parancssort sokféleképpen fogjuk nevezni: terminál, shell, CLI (a parancssori felület rövidítése) és konzol. Alapvetõen a parancssor a számítógéppel való interakció módja szöveges parancsok segítségével. A parancssori interfész, vagy CLI, ellentétben állhat a grafikus felhasználói felülettel, vagy GUI-val, amelyet talán jobban ismer.

A programozásban a parancssort néha REPL-nek nevezik, ami a Read, Evaluate, Print, Loop (olvasás, kiértékelés, nyomtatás, ciklus) rövidítése. Ez arra az alapvetõ módra utal, ahogyan a parancssorral négy lépésben interakcióba lépünk:

1. Olvassa be a felhasználó bemenetét. (A felhasználó beír egy parancsot, majd megnyomja az `Enter` billentyût.)
2. A bemenet kiértékelése. (A parancssor átveszi a bemenetet, és végrehajt valamilyen feladatot.)
3. Kiírja a választ. (A parancssor visszaad valamilyen információt a felhasználónak.)
4. Visszatérés az elsõ lépéshez, ahol a parancssor várja a felhasználó bemenetét.

Alapvetõen a megközelítés itt egy beszélgetés a számítógéppel. Ön beír valamit, a számítógép pedig végrehajt valamilyen folyamatot, és választ ad. Ezután folytathatja a beszélgetést további input megadásával, és így tovább.

Ebben a workshopban végig a Python REPL-t fogjuk használni. Ez azt jelenti, hogy beszélgetést folytatunk a géppel, ahol mi adjuk meg a bemenetet, a számítógép pedig a kimenetet.

## Megjegyzés a Windowsról

A Windows alapértelmezés szerint két parancssori felülettel rendelkezik. Az elsõ, a `cmd.exe` vagy parancssor már régóta létezik. Ez a felület funkcionálisan hasonló a DOS operációs rendszer parancssori felületéhez. A Windows egy modernebb parancssori felülettel is rendelkezik, amelyet Powershellnek hívnak.

Az Anaconda Prompt megnyitásakor a `cmd.exe` egy olyan változatával lépsz kapcsolatba, amelybe további, a Pythonhoz kapcsolódó parancsokat töltöttek be. Nem lépünk közvetlen kapcsolatba a Pythonnal, amíg be nem írjuk az `ipython` parancsot.

[<<< Elõzõ](installation.md) | [Következõ >>>](review.md)
