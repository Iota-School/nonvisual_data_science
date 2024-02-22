[<<< Elõzõ](motivation.md) | [Következõ >>>](resources.md)

# A kódunk mentése IPython varázslóval

Mûhelymunkánk végére értünk, és érdemes megõrizni a munkamenet során az IPythonba beírt parancsokat. Mivel IPython-t használunk, ezt egy magic parancs segítségével tehetjük meg.

A mágikus parancsok az IPythonba és a Jupyter Notebooksba épített hasznos segédprogramok. Ha más programból használja a Pythont, akkor nem férhet hozzá a mágikus parancsokhoz - ezek csak az IPythonra és a Jupyterre jellemzõek.

## Munkamenet mentése

A munkamenetünk szöveges fájlba történõ mentéséhez futtathatjuk a következõt:

```python
%save nonvisual.py 1-40
```

Ez egy százalékjel, a `save` szó, egy szóköz, egy fájlnév, egy szóköz, az 1, egy kötõjel és a 40-es szám. Az utolsó számnak az utolsó kimeneti sor számának kell lennie.

Ha a jövõben szeretnéd folytatni a munkamenetet, akkor használhatod a `%load` varázslót:

```python
%load nonvisual.py
```

## Egyéb hasznos varázsló parancsok

Az IPython rendelkezik [számos varázslóparanccsal](https://ipython.readthedocs.io/en/stable/interactive/magics.html). Néhány további hasznos parancs:

- `%run` Ha van egy külsõ Python fájlod, akkor ezzel a paranccsal lefuttathatod és betöltheted az összes függvényét és változóját az aktuális REPL-be. Ez messze az általam leggyakrabban használt mágikus parancs.
- `%notebook`: Ez egy nagyszerû parancs, ha látó munkatársakkal dolgozol. Fogja a REPL munkamenetet, és létrehoz belõle egy Jupyter Notebookot. A notebookot megoszthatod látó munkatársakkal. Ha szerkeszteni kell a notebookot, jelenleg a Google Colab jobban elérhetõ az NVDA-val, mint a Jupyter Notebook.
- `%edit`: Megnyit egy szövegszerkesztõt. Ezután írhat Pythont, mentheti és bezárhatja a fájlt, és a kód lefut a REPL-ben. Alapértelmezés szerint ez a parancs Windowson a Notepadot nyitja meg, de beállíthat egy másik szerkesztõt is alapértelmezettnek.
- `%who`: Kinyomtatja az összes olyan változót, amelyet definiáltál, és amely a munkamenetben elérhetõ.
- `%whos`: Mint a who, de több információt kap minden egyes változóról.
- `%xmode`: Ez a mód határozza meg, hogy mennyi információ kerül kiírásra a visszakövetési hiba során. A `%xmode minimal` jó lehet a képernyõolvasó felhasználóknak, akik nem akarnak bõ kimenetet.

[<<< Elõzõ](motivation.md) | [Következõ >>>](resources.md)
