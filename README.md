
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

## 🚀 Futtatás

A `adatbazisfeladat_v1.ipynb` Jupyter notebook-ot kell futtatni. A projekthez szükséges:
- Python 3.9+
- Könyvtárak: `pandas`, `pyodbc`

---

## 👥 Csoporttagok

- Név 1 (NEPTUN kód)
- Név 2 (NEPTUN kód)
- Név 3 (NEPTUN kód)

*(Töltsd ki a megfelelő nevekkel a beadás előtt.)*

---

## 📎 Fájlok a repository-ban

- `adatbazisfeladat_v1.ipynb` – a teljes megvalósítás
- `students.csv`, `instructors.csv`, `lessons.csv`, `vehicles.csv`, `exams.csv` – bemeneti adatok
- `README.md` – ez a fájl
