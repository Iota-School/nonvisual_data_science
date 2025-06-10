[Következő >>>](representing_data.md)

# Adattípusok

Az előző részben megismertük, hogyan kezeli a Pandas az egy- és kétdimenziós adatokat, és olyan statisztikai módszereket használtunk, mint az átlag, a medián és a szórás, hogy betekintést nyerjünk az egydimenziós adatokba, például az Airbnb-adatkészletünk ár oszlopába. Eddig a pontig többnyire numerikus adatokkal dolgoztunk, például árakkal vagy költségvetési tételekkel. Itt az ideje, hogy megnézzünk néhány más adattípust, és azt, hogyan dolgozhatunk velük a Pandasban.

## Adattípusok

Íme néhány adattípus, amellyel ebben a munkamenetben találkozunk. 

- `Kategorikus` - A kategorikus adatok olyan szöveges vagy numerikus adatok formájában jelennek meg, amelyek gyakran ismétlődnek. A kategorikus adatokat arra használjuk, hogy jelezzük, hogy az entitás egy adott kategóriába tartozik. Az Airbnb-adatkészletünkben a `szomszédság_csoport` oszlop jó példa a kategorikus adatokra. Az oszlop öt értékből álló halmazból áll (New York City öt kerülete), és azt jelzi, hogy egy adott hirdetés melyik kerülethez tartozik.

- `idő` - Az adatok ezen formája időpontokat jelöl. Ez egy dátum, egy időpont vagy egy dátum és egy időpont formáját öltheti, és többféle formátumban is megjelenhet.

- `Numerikus` - Ezek olyan adatok, amelyek esetében olyan statisztikai módszerek, mint az átlag vagy a szórás értelmezhetőek.

- "Leíró" vagy "nominális" - Az adatok ezen formája nem értelmezhető (mint a numerikus vagy az idő), és nem jelentenek értelmes kategóriákat. Gyakran egyedi vagy majdnem egyedi. Ezt az adatformát gyakran használják egy sor azonosítására. Az e-mail címek, az azonosítószámok vagy az Airbnb-listánk neve ebbe a kategóriába tartoznak.

A fentieken kívül vannak olyan adattípusok, amelyekkel egy adathalmazban találkozhatunk, de amelyeket még nagyobb valószínűséggel hozunk létre magunknak más adatformák elemzése során.

- `számlálás` - A számlálások úgy jönnek létre, hogy megszámláljuk, hogy az egyes értékek hányszor fordulnak elő. Ha például kategorikus adataink vannak, amelyek azt jelzik, hogy egy állathalmaz macska, kutya vagy madár-e, a számlálási adatokból megtudhatjuk, hogy mindegyikből hány fordul elő az adathalmazban.

- `Bináris` vagy `Boolean` - Az adatok ezen formája lehetővé teszi számunkra, hogy megtudjuk, hogy valami igaz-e vagy sem az egyes entitások esetében. Például az Airbnb-adatkészletünkben létrehozhatunk egy `is_brooklyn` oszlopot, amelyből megtudhatjuk, hogy egy hirdetés Brooklynban van-e, vagy egy `is_expensive` oszlopot, amelyből megtudhatjuk, hogy az ár 500 dollár felett van-e éjszakánként. A legtöbb más adatformát is át lehet alakítani bináris vagy boolean adatokká, ha úgy döntünk.

Az adattípusok nincsenek hivatalos kifejezésekkel ellátva az adattudományban, és az adattípusok kategorizálására különböző elnevezéseket és szervezeti rendszereket hallani. Egyes adattudósok például az adatokat numerikusnak vagy kategorikusnak tekintik. 

## Adattípusok a Python adattípusaihoz képest

A műhelysorozat első ülésén megismerkedtünk a Python adattípusaival, például a karakterláncokkal, listákkal és Boolean-típusokkal. A fentebb ismertetett adattípusok tág fogalmak, míg a Python adattípusok a Pythonra jellemzőek. A kategorikus adatok például karakterlánc vagy egész szám formájában is megjelenhetnek, akárcsak az időadatok.

[Következő >>>](representing_data.md)
