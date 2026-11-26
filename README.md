# Displaykollen – LÄS MIG / README

Färdiga installationspaket för **Displaykollen** (macOS) och **Displaykollen Samsung** (Android).
Källkoden ligger i privata förråd; här finns bara färdiga installationsfiler och uppdateringsfiler.

Ready-to-install packages for **Displaykollen** (macOS) and **Displaykollen Samsung** (Android).
Source code lives in private repositories; this repository contains release packages and update metadata only.

---

## Svenska

### Vad är apparna?

- **Displaykollen (macOS 26+, Apple Silicon):** En menyradsapp för fönsterfästning, skärmstyrning (upplösning, HiDPI, ljusstyrka, RGB och finstegad DDC-volym, XDR, virtuella skärmar och bild-i-bild), skärmdumpar med snabb lupp, redigerare, OCR och färgväljare, samt valfria drag-och-släpp-hyllor och stöd för Samsung-platta som extra skärm.
- **Displaykollen Samsung (Android):** Gör din Samsung Galaxy-platta till en extra skärm för Macen via USB eller Wi-Fi, med stöd för touch och S Pen.

### Installera och uppdatera på Mac (Displaykollen)

1. **Hämta:** Ladda ner den senaste `.dmg`-filen i mappen [`mac/`](mac/).
2. **Installera:** Öppna `.dmg`-filen och dra **Displaykollen.app** till **Program** (`/Applications`).
3. **Första starten (Gatekeeper):** Appen är inte signerad med ett Apple Developer-konto. Om macOS stoppar appen första gången gör du något av följande:
   - Öppna *Systeminställningar → Integritet och säkerhet* och klicka på **Öppna ändå**, eller
   - Kör detta i Terminal efter att appen lagts i `/Applications`:
     ```zsh
     xattr -dr com.apple.quarantine /Applications/Displaykollen.app
     ```
4. **Uppdatera:** Klicka på **Sök efter uppdatering** i menyns sidfot, i appmenyn (*Displaykollen → Sök efter uppdateringar…*) eller under *Inställningar → Avancerat → Uppdateringar*. Appen söker aldrig efter uppdateringar i bakgrunden.
5. **Behörigheter efter en uppdatering:** Eftersom varje ny osignerad version räknas som en ny app av macOS kan du behöva godkänna **Hjälpmedel** och **Skärminspelning** på nytt under *Systeminställningar → Integritet och säkerhet*. Om du använder hjälptjänsten (för HiDPI/EDID) kan den också behöva godkännas igen under *Systeminställningar → Allmänt → Inloggningsobjekt* eller installeras om under *Inställningar → Avancerat → Hjälptjänst*.

### Installera och uppdatera på Samsung-platta (Displaykollen Samsung)

1. **Hämta:** Ladda ner den senaste `.apk`-filen i mappen [`android/`](android/).
2. **Första installationen:** Öppna `.apk`-filen på plattan. Första gången ber Android om tillåtelsen **"Installera okända appar"** för webbläsaren eller filhanteraren (och senare för **Displaykollen Samsung** när appen ska uppdatera sig själv).
3. **Uppdatera:** Öppna **Inställningar → Sök efter uppdatering** i appen. Appen hämtar bara över HTTPS från det här förrådet och kontrollerar kontrollsumma (SHA-256), paketnamn, version och certifikat innan Androids installationsruta öppnas. Inga bakgrundskontroller körs.

### Integritet och felrapporter

Apparna samlar aldrig in statistik, använder inga egna servrar och skickar aldrig något i bakgrunden. På Mac (*Skicka felrapport…* i Om/Hjälp-menyn eller *Inställningar → Allmänt*) samlas appversion, macOS-version, Mac-modell, skärmuppställning (antal, upplösning och Hz utan serienummer), aktiverade funktioner, senaste 30 minuters loggar samt senaste tvättade Displaykollen-kraschrapporterna (`.ips`); allt innehåll visas i sin helhet först och skickas via e-post eller sparas som ZIP enbart när du själv väljer det. På Android (*Skicka felrapport…* i Displaykollen Samsung 1.6.2) visas hela innehållet först och skickas bara om du själv väljer att spara eller dela det.

### Bra att veta

- GitHub kan cacha uppdateringsfilerna (`appcast.xml` och `android.json`) i några minuter efter en ny utgåva. Vänta en liten stund och försök igen om en nyss släppt version inte syns direkt.
- De 3 senaste versionerna ligger kvar i `mac/` och `android/`. Äldre filer tas bort ur mapparna men finns kvar i git-historiken.

---

## English

### What are these apps?

- **Displaykollen (macOS 26+, Apple Silicon):** A menu bar app for window snapping, display control (resolution, HiDPI, brightness, RGB and fine-stepped DDC volume, XDR, virtual displays, picture-in-picture), screenshots with a smooth loupe, editor, OCR and color picker, plus optional drag-and-drop shelves and Samsung tablet display support.
- **Displaykollen Samsung (Android):** Turns your Samsung Galaxy tablet into an extra Mac display over USB or Wi-Fi, with touch and S Pen support.

### Install and update on Mac (Displaykollen)

1. **Download:** Get the latest `.dmg` file in [`mac/`](mac/).
2. **Install:** Open the `.dmg` and drag **Displaykollen.app** to **Applications** (`/Applications`).
3. **First launch (Gatekeeper):** Builds without an Apple Developer ID are ad hoc signed and unnotarized. If macOS blocks the first launch:
   - Open *System Settings → Privacy & Security* and click **Open Anyway**, or
   - Run this in Terminal after moving the app to `/Applications`:
     ```zsh
     xattr -dr com.apple.quarantine /Applications/Displaykollen.app
     ```
4. **Updates:** Click **Check for update** in the menu footer, in the app menu (*Displaykollen → Check for Updates…*), or under *Settings → Advanced → Updates*. No automatic background checks run.
5. **Permissions after updating:** Because each ad hoc signed build gets a new code identity in macOS, you may need to re-approve **Accessibility** and **Screen Recording** in *System Settings → Privacy & Security*, and re-approve or reinstall the helper in *System Settings → General → Login Items* (or *Settings → Advanced → Privileged Helper*).

### Install and update on Samsung tablet (Displaykollen Samsung)

1. **Download:** Get the latest `.apk` file in [`android/`](android/).
2. **First install:** Open the `.apk` on your tablet. The first time, Android asks for the **"Install unknown apps"** permission for your browser or file manager (and later for **Displaykollen Samsung** when updating itself).
3. **Updates:** Open **Settings → Check for update** in the app. Downloads only happen over HTTPS from this repository and verify SHA-256, package name, version code, and signing certificate before opening Android's installer. No background checks run.

### Privacy and bug reports

Neither app collects telemetry, uses any servers, or sends data in the background. On Mac (*Send Bug Report…* in the About/Help menu or *Settings → General*), a report gathers app version, macOS version, Mac model, display setup (count, resolution, and Hz without serial numbers), enabled features, the last 30 minutes of app logs, and recent scrubbed Displaykollen crash reports (`.ips`); all contents are shown in full first and are only emailed or saved as a ZIP when you explicitly choose to do so. On Android (*Send bug report…* in Displaykollen Samsung 1.6.2), the full report is previewed first and only saved or shared if you choose to do so.

### Good to know

- `raw.githubusercontent.com` may cache `appcast.xml` and `android.json` for a few minutes after a new release is published. Wait a few minutes and try again if a brand-new version does not appear immediately.
- The 3 most recent versions are kept in `mac/` and `android/`. Older files are removed from the folders but remain in git history.
