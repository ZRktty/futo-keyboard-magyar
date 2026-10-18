# Magyar hangalapú gépelés a FUTO Keyboardban

Ez az útmutató lépésről lépésre megmutatja, hogyan tudsz **magyarul diktálni** Android telefonon a
[FUTO Keyboard](https://keyboard.futo.tech/) billentyűzettel, egy kifejezetten magyarra tanított Whisper modell segítségével.

Miért jó ez?

- **Teljesen offline működik:** a hangod nem hagyja el a telefont, nincs felhő, nincs adatgyűjtés.
- **Pontosabb a magyar szövegfelismerés,** mint az általános, sok nyelvet tudó modellekkel.
- **Ingyenes és nyílt:** a modell Apache-2.0 licencű.

> A modellt nem én tanítottam: ez [sarpba magyar Whisper modellje](https://huggingface.co/sarpba/whisper-hu-small-finetuned),
> amit átalakítottam a FUTO Keyboard által használt formátumra. Minden érdem az övé és az OpenAI-é.

---

## Amire szükséged lesz

- Egy Android telefon (én Samsung Galaxy S23-on teszteltem)
- Kb. **300 MB szabad hely**
- Wi-Fi a letöltéshez (a modell 252 MB)

---

## 1. lépés: Telepítsd a FUTO Keyboardot

Válassz egyet az alábbi telepítési módok közül. Mindegyik ugyanazt az alkalmazást adja; a különbség csak az,
honnan kapod a frissítéseket.

> **Fontos:** maradj egyetlen forrásnál. A különböző helyekről telepített verziók nem feltétlenül frissíthetők
> egymásra, ilyenkor előbb el kell távolítani a régit.

### A) F-Droid (ajánlott)

A FUTO Keyboard nem a hivatalos F-Droid katalógusban van, hanem a **FUTO saját F-Droid tárolójában**, ezt egyszer
hozzá kell adni.

1. Telepítsd az [F-Droid](https://f-droid.org/) alkalmazást, ha még nincs meg.
2. A telefonodon nyisd meg ezt a linket, és válaszd a megnyitást az F-Droiddal:
   **[FUTO F-Droid tároló hozzáadása](https://fdroid.link/#https://app.futo.org/fdroid/repo?fingerprint=39D47869D29CBFCE4691D9F7E6946A7B6D7E6FF4883497E6E675744ECDFA6D6D)**
3. Ha a link nem működik, add hozzá kézzel: F-Droid → **Beállítások → Tárolók → +**, és írd be:
   ```text
   https://app.futo.org/fdroid/repo
   ```
   Ellenőrizd, hogy az ujjlenyomat (fingerprint) egyezik:
   ```text
   39 D4 78 69 D2 9C BF CE 46 91 D9 F7 E6 94 6A 7B 6D 7E 6F F4 88 34 97 E6 E6 75 74 4E CD FA 6D 6D
   ```
4. Frissítsd a tárolókat (húzd le a listát), keress rá a **FUTO Keyboard**-ra, és telepítsd.

### B) Obtainium (közvetlenül a fejlesztő GitHub kiadásaiból)

Az [Obtainium](https://github.com/ImranR98/Obtainium) közvetlenül a fejlesztők kiadási oldaláról telepít és frissít
alkalmazásokat, áruház nélkül.

1. Telepítsd az Obtainiumot (F-Droidról vagy a [GitHub kiadási oldaláról](https://github.com/ImranR98/Obtainium/releases/latest)).
2. Nyisd meg, és válaszd az **Add App** (Alkalmazás hozzáadása) fület.
3. Az **App Source URL** mezőbe írd be:
   ```text
   https://github.com/futo-org/android-keyboard
   ```
4. Koppints az **Add** gombra, majd az **Install** gombbal telepítsd.
5. Ha az Android rákérdez, engedélyezd az Obtainiumnak az **ismeretlen forrásból származó alkalmazások telepítését**.

Az Obtainium ezután magától szól, ha új verzió jelenik meg.

### C) Google Play

Ha a fentiek közül egyiket sem szeretnéd:
[FUTO Keyboard a Google Playen](https://play.google.com/store/apps/details?id=org.futo.inputmethod.latin.playstore)

### Beállítás

Telepítés után a FUTO Keyboard végigvezet a beállításon. Állítsd be **alapértelmezett billentyűzetnek**.

## 2. lépés: Kapcsold be a magyar nyelvet

1. Nyisd meg a **FUTO Keyboard beállításait**.
2. Menj a **Languages & Models** (Nyelvek és modellek) menübe.
3. Add hozzá a **Magyar** nyelvet.

Ez azért fontos, mert a FUTO Keyboard **mindig az éppen kiválasztott nyelvhez tartozó hangmodellt** használja.
A magyar modellt tehát a magyar nyelvhez fogjuk hozzárendelni.

## 3. lépés: Töltsd le a modellt a telefonodra

A telefonod böngészőjében nyisd meg ezt a linket, és a letöltés elindul:

**[whisper-hu-small-finetuned_q8_0.bin letöltése](https://huggingface.co/ZRktty/whisper-hu-small-finetuned-ggml-q8_0/resolve/main/whisper-hu-small-finetuned_q8_0.bin?download=true)** (252 MB)

A modell oldala, további részletekkel: [huggingface.co/ZRktty/whisper-hu-small-finetuned-ggml-q8_0](https://huggingface.co/ZRktty/whisper-hu-small-finetuned-ggml-q8_0)

A fájl a **Letöltések** mappába kerül. Ne nevezd át, a végén maradjon `.bin`.

## 4. lépés: Importáld a modellt a FUTO Keyboardba

1. Nyisd meg a **Saját fájlok** (vagy bármelyik fájlkezelő) alkalmazást, és menj a **Letöltések** mappába.
2. Koppints a `whisper-hu-small-finetuned_q8_0.bin` fájlra.
3. Válaszd a **Megnyitás ezzel → FUTO Keyboard** lehetőséget.
4. Amikor a FUTO Keyboard rákérdez, **rendeld a modellt a Magyar nyelvhez.**

Ha a fájlkezelő nem ajánlja fel a FUTO Keyboardot, nézd meg a FUTO Keyboard beállításaiban a
**Languages & Models** menüt: ott is lehet modellt importálni fájlból.

> **Tipp:** a menüpontok neve a telefonod nyelvétől és az alkalmazás verziójától függően kicsit eltérhet.

## 5. lépés: Diktálás

1. Nyiss meg bármilyen alkalmazást, ahol gépelni lehet (pl. üzenetek, jegyzetek).
2. Győződj meg róla, hogy a billentyűzeten a **magyar nyelv** van kiválasztva.
3. Koppints a **mikrofon** gombra, és beszélj.

Kész! 🎉

---

## Tippek

- **Automatikus leállás csendnél:** a FUTO Keyboard hangbeviteli beállításaiban kapcsold be az
  *Auto-stop on silence* opciót, és a felvétel magától leáll, amikor abbahagyod a beszédet.
- **30 másodperces korlát:** alapból egy diktálás legfeljebb 30 másodperc. A *Long-form voice input* opcióval ez
  feloldható, de hosszú felvételeknél romolhat a minőség (pl. ismétlődő szavak).
  Inkább diktálj rövidebb részletekben.
- **Beszélj természetesen,** nem kell tagolni vagy lassítani.

## Korlátok

- **Az angol szavakat fonetikusan írja le.** Ha magyar mondatba angol szót keversz, azt gyakran úgy írja le,
  ahogy hallja. Például a *„coworking irodából”* nálam *„Covercing irodából”* lett. Ezeket kézzel kell javítani.
- **Méret és sebesség:** a 252 MB-os modell egy modern telefonon gyorsan fut, régebbi vagy gyengébb
  készülékeken lassabb lehet.

## Hibaelhárítás

| Probléma | Megoldás |
| --- | --- |
| A fájlkezelő nem ajánlja fel a FUTO Keyboardot | Próbáld meg a FUTO Keyboard beállításaiból importálni (4. lépés), vagy próbálj egy másik fájlkezelőt. |
| Nem magyarul ír, vagy rossz a felismerés | Ellenőrizd, hogy a billentyűzeten a **Magyar** nyelv van kiválasztva, és hogy a modellt ahhoz rendelted. |
| Az importálás hibát jelez | Lehet, hogy a letöltés megszakadt. Töröld a fájlt, és töltsd le újra (a helyes méret: 264 464 624 bájt). |
| Új verziót szeretnék betenni | Importáld ugyanígy az új fájlt: felülírja a régit. |

---

## Köszönet és licenc

- **[OpenAI Whisper](https://huggingface.co/openai/whisper-small):** az eredeti beszédfelismerő modell (Apache-2.0)
- **[sarpba](https://huggingface.co/sarpba/whisper-hu-small-finetuned):** a magyar finomhangolás (Apache-2.0)
- **[whisper.cpp](https://github.com/ggml-org/whisper.cpp):** az átalakításhoz használt eszközök (MIT)
- **[FUTO](https://keyboard.futo.tech/):** a billentyűzet

Ez egy nem hivatalos útmutató, a FUTO-hoz, az OpenAI-hoz és sarpbához nincs köze.
A modell licence a [Hugging Face oldalon](https://huggingface.co/ZRktty/whisper-hu-small-finetuned-ggml-q8_0) található.
