# Cadastral Divisions Plus

Kengaytirilgan QGIS Processing plagini bo‘lib, poligonlarni (kadastr uchastkalarini) chiziq bo‘yicha bir nechta bo‘lakka ajratadi. Ushbu fork original **Cadastral Divisions** plaginini takomillashtirib, yangi “Plus” funksiyalarini qo‘shadi va boshqa o‘rnatilgan versiyalar bilan to‘qnashuvni oldini oladi.

---

## 🔧 O‘rnatish

### Variant 1 – ZIP’dan
1. Repository papkasini ZIP qiling (yoki Github’dan “Download ZIP”).
2. QGIS’ni oching → `Plugins ▸ Manage and Install Plugins ▸ Install from ZIP`.
3. Zip faylni ko‘rsating va “Install Plugin” tugmasini bosing.

### Variant 2 – Qo‘lda ko‘chirish
1. `Cadastral_Divisions-main` papkasini quyidagi katalogga nusxa qiling:
   - **Windows:** `%APPDATA%\QGIS\QGIS3\profiles\default\python\plugins`
   - **Linux:** `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins`
   - **macOS:** `~/Library/Application Support/QGIS/QGIS3/profiles/default/python/plugins`
2. QGIS’ni ishga tushiring (`Plugins ▸ Manage and Install Plugins`) va **Cadastral Divisions Plus** ni yoqing.

Qo‘shimcha `pip` paketlari talab qilinmaydi — plagin QGIS bilan birga keladigan `qgis.core` va `qgis.PyQt` modullarini ishlatadi.

---

## 🆕 Plus imkoniyatlari
- **Residual (qoldiq) boshqaruvi:** maqsad yuzasi bilan kesilganda ortiqcha yoki yetishmaydigan maydonni kerakli bo‘lakka qo‘shish yoki alohida qoldirish.
- **Ko‘p til:** italiyan/ispan/inglizdan tashqari ruscha va o‘zbekcha matnlar.
- **Rebrending:** yagona identifikator (`Cadastral Divisions Plus`) bilan ro‘yxatga olinadi, original plugin bilan parallel o‘rnatiladi.
- **Yangi natija prefiksi:** yaratiladigan qatlamlar `FractPlus_YYYY-MM-DD HH:MM:SS` nomi bilan saqlanadi.
- **Barqarorlik:** original atributlar + `sub`, `part`, `area` maydonlari avtomatik qo‘shiladi.

---

## 🧭 Qanday ishlatish

1. `Processing Toolbox` dan **Cadastral Plus ▸ Cadastral Divisions Plus** algoritmini tanlang.
2. Quyidagi parametrlarni to‘ldiring:

| Parametr | Tavsif |
| --- | --- |
| **Input Poly layer** | Bo‘linadigan poligon(yar). |
| **Input Line layer** | Bo‘luvchi chiziq. Algoritm chiziqni poligon diagonaliga tenglashtirib, markazlashtiradi. |
| **Split with divider manually positioned** | `True` bo‘lsa, chiziq aynan berilgan holatida ishlatiladi. |
| **Denominator fraction or 1/n parts** | n ta teng bo‘lak soni yoki kasr maxraji (`1/n`). |
| **Splitting into equal parts** | `n > 2` bo‘lganda ketma-ket kesish rejimi. |
| **Surface area to be obtained** | Maqsad yuzasi (kvadrat birlik). Berilsa, ulush o‘rniga shu maydon kesiladi. |
| **Invert parts** | Chiziqqa nisbatan yuqori/pastki yoki chap/o‘ng qismlarni almashtiradi. |
| **Residual handling mode** | Qoldiqni oxirgi/ birinchi/ tanlangan bo‘lakka qo‘shish yoki alohida qoldirish. |
| **Residual target part** | “Manual” rejimda qoldiq biriktiriladigan bo‘lak raqami (1 dan). |

3. Run tugmasini bosing. Natija qatlamiga har bir bo‘lak uchun:
   - `sub …` (masalan, `sub 1`, `sub qoldiq`)
   - `…_part` (foizdagi ulush)
   - `…_area` (yuzaning sonli qiymati) maydonlari qo‘shiladi.

---

## 📁 Chiqish
- Yangi qatlam nomi: `FractPlus_<sana_vaqt>`.
- Qoldiq logi: `Processing` panelidagi `Feedback` oynasida `Residual assigned to part …` yoki `Residual kept as standalone part` xabarlari ko‘rinadi.

---

## 📄 Hujjatlar
- Brauzer uchun HTML hujjat: `docs_readme.html`.
- Rasmiy repo linklari (original loyiha):  
  - GitHub: <https://github.com/Korto19/Cadastral_Divisions>
  - Bug tracker: <https://github.com/Korto19/Cadastral_Divisions/issues>

---

## 🧑‍💻 Mualliflik
- Asosiy muallif: **Giulio Fattori** – `giulio.fattori@tin.it`
- “Plus” forki o‘zgarishlari: residual boshqaruvi, yangi lokalizatsiyalar, fayl nomlari va dokumentatsiya.

---

## 📝 Changelog (asosiy nuqtalar)
| Versiya | O‘zgarish |
| --- | --- |
| 1.2 Plus | Residual rejimlari, rus/uz lokalizatsiyasi, qayta nomlash. |
| 1.2 | Ispan tiliga tarjima. |
| 1.1 | Tarjimalar va hujjatga havola qo‘shildi. |
| 1.0 | Frazionamenti Processing’dan migratsiya. |

---

## ℹ️ Qisqa FAQ
- **Plugin Reloader ro‘yxatida ko‘rinmasachi?** Toolbar’dagi yangi drop-down menyudan tanlang yoki katalog nomi `CadastralDivisionsPlus` ekanini tekshiring.
- **Qo‘shimcha python paketlari kerakmi?** Yo‘q, QGIS bilan birga keladigan kutubxonalar yetarli.
- **Bir vaqtning o‘zida original plugin ishlatsam bo‘ladimi?** Ha, nomlari va modul identifikatorlari farqli.

Savollar bo‘lsa, GitHub issues yoki muallif emaili orqali bog‘laning. Omad! 🎉

