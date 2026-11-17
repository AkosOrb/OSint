# Eszközválogatás a két gyűjteményből (2026. november 16.)

Forrás: az OSINT4ALL start.me oldal Ákos által feltöltött mentése (77 kategória, kb. 1450 link), valamint az OSINT Framework nyilvános listája (`lockfale/OSINT-Framework`, `public/arf.json`, 1170 eszköz).

**Válogatási elv:** csak olyan eszköz került az alkalmazásba, amellyel a hallgató a **saját** kitettségét méri fel, vagy amely a **védekezést** segíti. Ez a projekt célja (tudatosság a sebezhetőségek bemutatásával) és a megbeszélt, védekezés-központú hatókör.

## Bekerült az alkalmazásba

| Eszköz | Forrás | Hová került |
|---|---|---|
| Namechk | mindkettő | F1 Gyűjtés: saját felhasználónév |
| Cover Your Tracks (EFF), BrowserLeaks, IPLeak, Social Media Fingerprint | OSINT Framework (OpSec), start.me | F1 Gyűjtés: böngésző-önteszt; új PET-kártya |
| MXToolbox Email Header Analyzer | start.me (EMAIL) | F3 Gyűjtés: fejléc elemzése |
| PhishTank | OSINT Framework (Phishing) | F3 Gyűjtés: ismert adathalász linkek |
| Who.is | mindkettő (WHOIS) | F3 Gyűjtés: domain kora |
| Image Scrubber | start.me (PRIVACY / SECURITY) | F4 Gyűjtés és PET: böngészőben futó metaadat-törlés |
| Just Delete Me | OSINT Framework (Privacy / Clean Up) | Új PET-kártya: fióktörlés |
| AnonAddy, SimpleLogin | start.me | PET: e-mail alias példák |
| Signal, Element, Briar | start.me (SECURE COMMUNICATION) | PET: titkosított üzenetküldők |
| Privacy Guides, EFF Surveillance Self-Defense, Security Planner, Security in a Box | start.me, OSINT Framework | PET-gyűjtemény: útmutatók |

Már korábban is bent volt, és mindkét forrásban szerepel: WhatsMyName, Have I Been Pwned, TinEye, Wayback Machine, VirusTotal, urlscan.io, ExifTool, MAT2, Tor Browser.

## Szándékosan kimaradt

- **Hamis személyazonosság- és okmánygenerátorok, eldobható SMS-számok** (start.me: ID GENERATOR, THROWAWAY CONTACT egy része; OSINT Framework: Persona Creation): visszaélésre alkalmasak, a tudatossági célhoz nem kellenek.
- **Személykereső, nyilvántartási és adatbázis-kategóriák** (PEOPLE, PUBLIC RECORDS, VOTER DATABASES, SEX OFFENDER, DATA DUMP, DARKNET stb.): mások adatainak gyűjtésére szolgálnak.
- **Infrastruktúra-felderítés és sérülékenységvizsgálat** (Shodan, Censys, online Nmap, Heartbleed-ellenőrző stb.): támadó jellegű, engedély nélkül jogi kockázatot jelent; nem része a megbeszélt hatókörnek.
- **Országspecifikus (amerikai, kanadai) források**: magyar hallgatóknak nem relevánsak.
