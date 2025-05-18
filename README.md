
# Autósiskola Adatbázis – SQL + Python projekt

Ez a projekt az SQL és Python összekapcsolására épül, egy fiktív autósiskola adatkezelési folyamatait modellezve.

## 📌 Projektfeladat (3. opció)

**SQL vagy NoSQL adatbázis létrehozása** (min. 4 tábla) adatok importálásával, majd kapcsolódás Pythonból, és legalább:
- 5 lekérdezés
- 5 CRUD művelet

---

## 🗃️ Adatbázis leírása

Az adatbázis egy autósiskola működését modellezi az alábbi táblákkal:

| Tábla       | Leírás |
|-------------|--------|
| `Students`  | Tanulók adatai (név, születési dátum, elérhetőségek, jelentkezés dátuma) |
| `Instructors` | Oktatók adatai (név, jogosítvány típusa, elérhetőség, kezdés) |
| `Lessons`   | Órák adatai (tanuló, oktató, időpont, típus, helyszín) |
| `Vehicles`  | Oktatókhoz rendelt járművek (rendszám, típus, évjárat, műszaki) |
| `Exams`     | Vizsgaeredmények (tanuló, vizsga típusa, eredmény) |

Kapcsolatok:
- `Lessons.tanulo_id` → `Students`
- `Lessons.oktato_id` → `Instructors`
- `Vehicles.oktato_id` → `Instructors`
- `Exams.tanulo_id` → `Students`

---

## ⚙️ Az adatbázis létrehozása

- Az adatokat `.csv` fájlokból importáltuk (`pandas` segítségével).
- Az adatbázist `sqlite3` és `pyodbc` modullal kezeltük.
- Az SQL parancsokat Python kódon keresztül futtattuk.
- A tábla-definíciók megfelelnek a 3. normálformának (3NF).
- Adatbázismotor: **SQL Server Express 2019**
- ODBC Driver: **ODBC Driver 17 for SQL Server**

---

## 🔍 Lekérdezések (példák)

- Tanulók születési dátum szerint rendezve
- Oktatók tanulóinak száma `GROUP BY`-val
- `JOIN` a tanulók és oktatók között
- `HAVING` szűrés legalább 2 tanulós oktatókra
- `ROLLUP` összesítés óra típus szerint
- `RANK()` használata születési sorrendhez

---

## ✏️ CRUD-műveletek (példák)

- Új tanuló beszúrása (`INSERT`)
- Tanuló adatok lekérdezése (`SELECT`)
- Cím módosítása (`UPDATE`)
- Törlés (`DELETE`)
- Feltételes beszúrás `IF EXISTS` vizsgálattal

---

## 👥 Csoporttagok

- Név 1 (NEPTUN kód)
- Név 2 (NEPTUN kód)
- Név 3 (NEPTUN kód)

---

## 🧩 ER Diagram és Dokumentáció

*(A diagram.png-t töltsd fel ide, hogy megjelenjen.)*

---

### 📋 Kényszerek összefoglalva

- **PRIMARY KEY**: minden táblában van elsődleges kulcs (pl. `tanulo_id`, `oktato_id`, stb.)
- **FOREIGN KEY**:
  - `Lessons.tanulo_id` → `Students`
  - `Lessons.oktato_id` → `Instructors`
  - `Vehicles.oktato_id` → `Instructors`
  - `Exams.tanulo_id` → `Students`
- **CHECK**:
  - `Instructors.jogositvany_tipus IN ('A', 'B', 'C', 'D')`
  - `Lessons.ora_tipus IN ('elméleti', 'gyakorlati')`
  - `Exams.eredmeny IN ('sikeres', 'sikertelen')`
  - `Vehicles.evjarat >= 1990`
- **NOT NULL**: kulcsmezők, dátumok, típusok
- **UNIQUE**: `Vehicles.rendszam`

---

### 🗃️ Táblák rövid leírása

- **Students**: A tanulók alapadatait tartalmazza (név, születési dátum, lakcím, elérhetőségek, jelentkezési dátum).
- **Instructors**: Az oktatók neve, jogosítványtípusa, munkaviszony kezdete és elérhetősége.
- **Lessons**: Tanuló és oktató közötti órák (dátum, időpont, típus, helyszín).
- **Vehicles**: Oktatókhoz tartozó oktató járművek (rendszám, típus, évjárat, műszaki).
- **Exams**: Vizsgaeredmények (tanuló, típus, dátum, eredmény).

---

### 🛠️ Adatbázis létrehozásának módja

- Az adatokat `.csv` fájlokból töltöttük be.
- A programozási környezet: **Python + pandas + pyodbc**
- Adatbázis motor: **SQL Server Express 2019**
- Kapcsolódás: **ODBC Driver 17 for SQL Server**
- Az adatbázis létrehozása, feltöltése és lekérdezése Jupyter notebookban történt.
