# Displaykollen – Releases / Utgåvor

Färdiga installationspaket för **Displaykollen** (macOS) och **Displaykollen Samsung** (Android).
Källkoden finns i privata förråd; detta förråd innehåller enbart färdiga paket och uppdateringsmetadata.

Ready-to-install packages for **Displaykollen** (macOS) and **Displaykollen Samsung** (Android).
Source code lives in private repositories; this repository contains release artifacts and update metadata only.

---

## Svenska

### macOS – Displaykollen

- **Nedladdning:** Hämta senaste `.dmg`-fil i mappen [`mac/`](mac/).
- **Installation:** Öppna DMG-filen och dra **Displaykollen.app** till **Program** (`/Applications`).
- **Första start (Gatekeeper):** Byggen utan Apple Developer ID är ad hoc-signerade och onotariserade. Om macOS blockerar första starten:
  1. Öppna *Systeminställningar → Integritet och säkerhet* och klicka på **Öppna ändå**, eller
  2. Kör i Terminal efter att appen flyttats till `/Applications`:
     ```zsh
     xattr -dr com.apple.quarantine /Applications/Displaykollen.app
     ```
- **Uppdateringar:** Öppna **Displaykollen → Sök efter uppdateringar…** eller **Inställningar → Avancerat → Uppdateringar → Sök efter uppdatering**. Inga bakgrundskontroller görs automatiskt.
- **Behörigheter och hjälptjänst efter uppdatering:** Eftersom ad hoc-signerade byggen får en ny kodidentitet (CDHash) vid varje utgåva kan macOS kräva att **Hjälpmedel** och **Skärminspelning** godkänns på nytt under *Systeminställningar → Integritet och säkerhet*, och att hjälptjänsten (`DisplaykollenHelper`) godkänns på nytt under *Systeminställningar → Allmänt → Inloggningsobjekt* (eller ominstalleras via *Inställningar → Avancerat → Hjälptjänst*).

### Android – Displaykollen Samsung

- **Nedladdning:** Hämta senaste `.apk`-fil i mappen [`android/`](android/).
- **Första installation:** Öppna APK-filen på plattan. Första gången ber Android om tillåtelsen **"Installera okända appar"** för webbläsaren/filhanteraren (och för **Displaykollen Samsung** första gången appen ska uppdatera sig själv).
- **Uppdateringar:** Öppna **Inställningar → Sök efter uppdatering** i appen. Appen hämtar bara över HTTPS från detta förråd och verifierar SHA-256, paketnamn, versionskod och signeringscertifikat innan Androids installationsruta öppnas. Inga bakgrundskontroller körs.

### Bra att veta

- `raw.githubusercontent.com` kan cacha `appcast.xml` och `android.json` i några minuter efter att en ny version har publicerats. Vänta en stund och försök igen om en helt ny version inte syns direkt.
- De 3 senaste versionerna ligger kvar i `mac/` och `android/`. Äldre filer tas bort ur arbetskatalogen men ligger kvar i git-historiken.

---

## English

### macOS – Displaykollen

- **Download:** Get the latest `.dmg` file in [`mac/`](mac/).
- **Install:** Open the DMG and drag **Displaykollen.app** to **Applications** (`/Applications`).
- **First launch (Gatekeeper):** Builds without an Apple Developer ID are ad hoc signed and unnotarized. If macOS blocks the first launch:
  1. Open *System Settings → Privacy & Security* and click **Open Anyway**, or
  2. Run in Terminal after moving the app to `/Applications`:
     ```zsh
     xattr -dr com.apple.quarantine /Applications/Displaykollen.app
     ```
- **Updates:** Use **Displaykollen → Check for Updates…** or **Settings → Advanced → Updates → Check for update**. No automatic background checks run.
- **Permissions and helper after updating:** Because ad hoc signed builds receive a new code identity (CDHash) on every release, macOS may require re-approving **Accessibility** and **Screen Recording** in *System Settings → Privacy & Security*, and re-approving or reinstalling `DisplaykollenHelper` in *System Settings → General → Login Items* (or *Settings → Advanced → Privileged Helper*).

### Android – Displaykollen Samsung

- **Download:** Get the latest `.apk` file in [`android/`](android/).
- **First install:** Open the APK on your tablet. The first time, Android asks for the **"Install unknown apps"** permission for the browser/file manager (and for **Displaykollen Samsung** the first time the app updates itself).
- **Updates:** Open **Settings → Check for update** in the app. Downloads only happen over HTTPS from this repository and verify SHA-256, package name, version code, and signing certificate before opening Android's installer. No background checks run.

### Good to know

- `raw.githubusercontent.com` may cache `appcast.xml` and `android.json` for a few minutes after a new release is published. Wait a few minutes and try again if a brand-new version does not appear immediately.
- The 3 most recent versions are kept in `mac/` and `android/`. Older files are removed from the working tree but remain in git history.
