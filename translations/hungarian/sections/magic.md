[<<< El�z�](motivation.md) | [K�vetkez� >>>](resources.md)

# A k�dunk ment�se IPython var�zsl�val

M�helymunk�nk v�g�re �rt�nk, �s �rdemes meg�rizni a munkamenet sor�n az IPythonba be�rt parancsokat. Mivel IPython-t haszn�lunk, ezt egy magic parancs seg�ts�g�vel tehetj�k meg.

A m�gikus parancsok az IPythonba �s a Jupyter Notebooksba �p�tett hasznos seg�dprogramok. Ha m�s programb�l haszn�lja a Pythont, akkor nem f�rhet hozz� a m�gikus parancsokhoz - ezek csak az IPythonra �s a Jupyterre jellemz�ek.

## Munkamenet ment�se

A munkamenet�nk sz�veges f�jlba t�rt�n� ment�s�hez futtathatjuk a k�vetkez�t:

```python
%save nonvisual.py 1-40
```

Ez egy sz�zal�kjel, a `save` sz�, egy sz�k�z, egy f�jln�v, egy sz�k�z, az 1, egy k�t�jel �s a 40-es sz�m. Az utols� sz�mnak az utols� kimeneti sor sz�m�nak kell lennie.

Ha a j�v�ben szeretn�d folytatni a munkamenetet, akkor haszn�lhatod a `%load` var�zsl�t:

```python
%load nonvisual.py
```

## Egy�b hasznos var�zsl� parancsok

Az IPython rendelkezik [sz�mos var�zsl�paranccsal](https://ipython.readthedocs.io/en/stable/interactive/magics.html). N�h�ny tov�bbi hasznos parancs:

- `%run` Ha van egy k�ls� Python f�jlod, akkor ezzel a paranccsal lefuttathatod �s bet�ltheted az �sszes f�ggv�ny�t �s v�ltoz�j�t az aktu�lis REPL-be. Ez messze az �ltalam leggyakrabban haszn�lt m�gikus parancs.
- `%notebook`: Ez egy nagyszer� parancs, ha l�t� munkat�rsakkal dolgozol. Fogja a REPL munkamenetet, �s l�trehoz bel�le egy Jupyter Notebookot. A notebookot megoszthatod l�t� munkat�rsakkal. Ha szerkeszteni kell a notebookot, jelenleg a Google Colab jobban el�rhet� az NVDA-val, mint a Jupyter Notebook.
- `%edit`: Megnyit egy sz�vegszerkeszt�t. Ezut�n �rhat Pythont, mentheti �s bez�rhatja a f�jlt, �s a k�d lefut a REPL-ben. Alap�rtelmez�s szerint ez a parancs Windowson a Notepadot nyitja meg, de be�ll�that egy m�sik szerkeszt�t is alap�rtelmezettnek.
- `%who`: Kinyomtatja az �sszes olyan v�ltoz�t, amelyet defini�lt�l, �s amely a munkamenetben el�rhet�.
- `%whos`: Mint a who, de t�bb inform�ci�t kap minden egyes v�ltoz�r�l.
- `%xmode`: Ez a m�d hat�rozza meg, hogy mennyi inform�ci� ker�l ki�r�sra a visszak�vet�si hiba sor�n. A `%xmode minimal` j� lehet a k�perny�olvas� felhaszn�l�knak, akik nem akarnak b� kimenetet.

[<<< El�z�](motivation.md) | [K�vetkez� >>>](resources.md)
