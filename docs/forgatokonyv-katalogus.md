# OSINT tudatossági forgatókönyv-katalógus (vázlat jóváhagyásra)

Oktatási segédanyag kiberbiztonsági mesterszakos hallgatóknak. A cél az, hogy a hallgató a saját nyilvános adatain keresztül lássa meg, mit tud róla egy idegen, és ebből tanulja meg a védekezést.

> **Alapszabály:** minden gyakorlat kizárólag a hallgató saját adatain vagy fiktív, oktató által készített személyen végezhető. Más ember adatainak gyűjtése engedély nélkül sértheti a GDPR-t és a magánszférát. Az eszközök célja az önellenőrzés.

---

## Egységes forgatókönyv-séma

| Mező | Tartalom |
|---|---|
| Azonosító, cím, nehézség | pl. F1 · Saját digitális lábnyom · Kezdő |
| Helyzetleírás | rövid, életszerű kiinduló történet |
| Tanulási cél | mit ért meg a hallgató a végére |
| Jogi és etikai keret | mit szabad és mit nem |
| 1. Tervezés | mit akarok megtudni magamról, milyen adatokból indulok |
| 2. Gyűjtés | lépések és ajánlott eszközök linkkel |
| 3. Elemzés | mit jelentenek az eredmények, mi a kockázat |
| 4. Jelentés | rövid saját kockázati összefoglaló |
| Mit árul el rólad, és hogyan védekezz | a sebezhetőség és a konkrét teendők |
| Ellenőrző kérdések | 3–4 reflexiós kérdés |

Az *(gy)* jelölésű eszközök az osint4all és az OSINT Framework gyűjteményekből valók, ezeket a 3. lépésben egyenként ellenőrzöm.

---

## F1 · Saját digitális lábnyom · Kezdő

**Helyzet:** Állásinterjú előtt állsz, és kíváncsi vagy, mit talál rólad a HR-es fél óra keresgélés után.

**Tanulási cél:** belátni, hogy az egyenként ártalmatlan adatok együtt részletes képet adnak rólad.

**Keret:** csak a saját adataiddal.

1. **Tervezés:** írd össze, milyen neveken, felhasználóneveken és e-mail címeken vagy jelen az interneten.
2. **Gyűjtés:**
   - Keress rá a saját felhasználónevedre: **revealer.us**, **fingerprint.to**, WhatsMyName *(gy)*. Megmutatják, hány oldalon fordul elő ugyanaz a név.
   - Keress rá a nevedre egy keresőben idézőjelek között.
   - Fordított képkeresés a saját profilképeddel: Google Lens, TinEye *(gy)*.
   - Nézd meg a régi oldalaid archív változatát: Wayback Machine *(gy)*.
3. **Elemzés:** mely fiókjaid köthetők össze? Kiderül-e a lakóhelyed, a munkahelyed, a napirended? Kitalálható-e valamelyik biztonsági kérdésed válasza?
4. **Jelentés:** táblázat: adat, hol található, ki látja, mennyire kockázatos.

**Védekezés:** szigorúbb adatvédelmi beállítások, régi fiókok törlése, eltérő felhasználónevek a magán- és szakmai fiókokhoz, a Google „Rólad szóló találatok” eltávolítási kérelme.

**Ellenőrző kérdések:** Mi lepett meg a legjobban? Melyik adatot törölnéd elsőként? Miért kockázatos mindenhol ugyanazt a felhasználónevet használni?

---

## F2 · Érintett vagyok-e adatszivárgásban? · Kezdő

**Helyzet:** Hírt olvasol egy webáruház adatszivárgásáról, ahol neked is volt fiókod.

**Tanulási cél:** megérteni, hogyan veszélyeztet egyetlen szivárgás több fiókot is, ha ugyanazt a jelszót használod.

**Keret:** csak a saját e-mail címeiddel.

1. **Tervezés:** írd össze az e-mail címeidet, és hogy hol használsz azonos jelszót.
2. **Gyűjtés:**
   - **breachdirectory.org**: szerepel-e az e-mail címed ismert szivárgásban.
   - **revealer.us**: milyen szivárgásokban és milyen adatmezőkkel (dátum, adattípus; jelszót nem mutat).
   - Have I Been Pwned *(gy)*: a szivárgások listája.
3. **Elemzés:** milyen adataid szivárogtak ki (jelszó, telefonszám, lakcím)? Mely más fiókjaid vannak veszélyben?
4. **Jelentés:** szivárgás, dátum, érintett adatok, megtett lépés.

**Védekezés:** jelszókezelő, minden oldalon egyedi jelszó, kétlépcsős azonosítás (lehetőleg passkey vagy hardverkulcs), e-mail aliasok a regisztrációkhoz.

**Ellenőrző kérdések:** Miért nem elég egy bonyolult jelszó, ha mindenhol ugyanaz? Mit teszel elsőként, ha érintett vagy?

---

## F3 · Adathalász üzenet felismerése · Középhaladó

**Helyzet:** E-mailt kapsz, amely a bankod nevében sürgős jelszócserét kér egy linken keresztül.

**Tanulási cél:** megtanulni nyilvános forrásokból ellenőrizni, hogy egy üzenet és egy link megbízható-e, mielőtt rákattintasz.

**Keret:** csak a saját postafiókodba érkezett gyanús üzenettel, a linkre kattintás nélkül.

1. **Tervezés:** mit kell ellenőrizni: feladó, link célja, domain kora, hangnem.
2. **Gyűjtés:**
   - Nézd meg a feladó valódi címét és a levél fejlécét (SPF, DKIM, DMARC eredmény).
   - Másold ki a linket kattintás nélkül, és ellenőrizd: VirusTotal, urlscan.io *(gy)*.
   - Nézd meg a domain regisztrációs dátumát WHOIS-szal *(gy)*. A pár napos domain gyanús.
3. **Elemzés:** egyezik-e a domain a bank valódi domainjével? Van-e benne betűcsere (pl. „rn” az „m” helyett)?
4. **Jelentés:** jelek listája, döntés (adathalász vagy valódi), és bejelentés a banknak vagy a CERT-nek.

**Mit árul el rólad és védekezés:** a nyilvános adataidból (F1) a támadó személyre szabott üzenetet írhat. Teendők: soha ne a levélben lévő linken lépj be, hanem a bank oldalát magad írd be; jelentsd a gyanús leveleket.

**Ellenőrző kérdések:** Melyik három jel árulja el leggyorsabban az adathalászatot? Hogyan segíti a támadót a nyilvános lábnyomod?

---

## F4 · Közösségi média adatvédelmi átvilágítás · Kezdő

**Helyzet:** Nyaralásról posztolsz képeket, és szeretnéd tudni, mit lát belőlük egy idegen.

**Tanulási cél:** megérteni, hogy a fotók, a helymegjelölések és az ismerőslista mennyit elárul.

**Keret:** csak a saját profiljaiddal.

1. **Tervezés:** listázd a közösségimédia-fiókjaidat.
2. **Gyűjtés:**
   - Nézd meg a profilodat kijelentkezve vagy „megtekintés másként” nézetben.
   - Ellenőrizd a saját fotóid metaadatait (helyadat, készülék): ExifTool vagy egy online EXIF-néző *(gy)*.
   - Nézd át, kik látják az ismerőslistádat, a születésnapodat, a munkahelyedet.
3. **Elemzés:** kiderül-e a lakcímed, mikor vagy távol otthonról, ki a családod?
4. **Jelentés:** beállítás, régi érték, új érték.

**Védekezés:** helymeghatározás kikapcsolása a kamerában, utólagos posztolás nyaralásról, ismerőslista és személyes adatok elrejtése, rendszeres beállítás-ellenőrzés.

**Ellenőrző kérdések:** Melyik beállításod volt a legnyitottabb? Miért veszélyes valós időben posztolni a tartózkodási helyedet?

---

## Gyakorlókörnyezet

A gyakorlati, kézzelfogható biztonsági képzéshez a **pwn.college** ingyenes, irányított oktatási platformot ajánlja az alkalmazás kiegészítő forrásként.

---

**Következő lépés jóváhagyás után:** a 2. lépésben ebből a katalógusból készül a böngészőben futó interaktív, lépésről lépésre vezető alkalmazás.
