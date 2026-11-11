# SAIF AI — Ownership Declaration, Licence Position & Buyer Assignment / Relicensing Instrument

**Document Version:** 2.0  
**Effective Date:** 2026-11-11  
**Software Product:** SAIF AI (Android Application, Workspace Daemon, Agent Runtime, Studio & Cloud Builder)  
**Canonical Source & Release Repository:** <https://github.com/juwadipro73-svg/Saif>

---

## Part 1 — Executive Summary & Legal Architecture

1. **100% Original Application Codebase:**  
   Every application package in SAIF AI (`app/src/main/java/com/example/**` across `ui`, `llm`, `agent`, `studio`, `saifagent`, `saifcore`, `saiflive`, `live`, `stt`, `builder`, `compiler`, `terminal`, `cloud`, `data`, `github`, `audio`, `utils`, and `util`), the `:apprunner` Android module, and the pure-Go local workspace daemon (`termux-daemon/server.go`) are original works authored for SAIF AI (`Copyright (c) SAIF AI. All rights reserved.`).
2. **Verified Zero Upstream GPLv3 Survival:**  
   Automated file-by-file provenance verification (`tools/licence/provenance.py --upstream <antigem> --write`, scanning both source extensions and extensionless scripts) across all **426** source/script files confirms:
   - **408** original SAIF AI files (`330` `.kt`/`.java`/`.go` files stamped with SAIF AI's copyright header; `0` unstamped; `0` header violations).
   - **18** standard Android/Gradle/repository-root paths (`AndroidManifest.xml`, `build.gradle.kts`, `settings.gradle.kts`, `ic_launcher.xml`, etc.), of which **0 are identical** (`0` lines), **0 are modified** (`0` lines), and **0 are renamed copies** (maximum similarity **0.455** on a 9-line Android `<adaptive-icon>` XML wrapper).
   - Four unused shell scripts previously left under `app/src/main/assets/bin/` (`backup_projects`, `backup_proot_ubuntu`, `git_clone`, `restore_projects`) have been permanently deleted.
3. **Full Freedom to Relicense or Assign:**  
   Because zero third-party GPLv3 code exists in the SAIF AI codebase and every third-party component is either permissively licensed, dynamically linked unmodified under LGPL-2.1 (`sora-editor`), or invoked across an OS process boundary as a separate standalone program (`proot` — mere aggregation under GPL-2.0 §2), **SAIF AI (or any Assignee acquiring rights under Part 3 below) may distribute, commercialize, white-label, or relicense SAIF AI's own source code and APK under any proprietary, commercial, dual, or open-source licence of its choosing**, subject only to keeping intact the third-party notices and source offer summarized in Part 2.

---

## Part 2 — Non-Transferable Third-Party Components & Ongoing Obligations

Neither SAIF AI nor any Assignee claims copyright ownership over the unmodified third-party open-source components below. Any redistributed APK or white-label build that continues to include these components must preserve their notices (already automated inside `assets/legal/`, `assets/licences/`, and **Settings → Licences & open source**):

| Component | Location / Coordinate | Licence | Required Action When Shipping Binary APK |
|---|---|---|---|
| **Rosemoe sora-editor** (`0.23.6`) | Maven Central AAR (`io.github.Rosemoe.sora-editor:*`) | **LGPL-2.1** | Keep unmodified dynamic AAR dependency; retain LGPL-2.1 notice in `THIRD_PARTY_NOTICES.md` and `WRITTEN_SOURCE_OFFER.txt`, and allow library replacement/relinking. |
| **Termux `terminal-emulator` & `terminal-view`** (`v0.118.1`) | JitPack AAR (`com.github.termux.termux-app:*`) | **Apache-2.0** (per `termux-app` `LICENSE.md` Exceptions) | Retain Apache-2.0 attribution in `THIRD_PARTY_NOTICES.md`. Do **not** add `termux-shared` (which is GPL-3.0). |
| **Termux PRoot** (`proot`, `loader`) | `assets/bin/{proot,loader}` & `lib/arm64-v8a/{libproot.so,libprootloader.so}` | **GPL-2.0-or-later** | Invoke strictly as a separate OS process (`execvp` / `ProcessBuilder` — mere aggregation under GPL-2.0 §2; never link into JVM/JNI). Retain `assets/licences/WRITTEN_SOURCE_OFFER.txt` and provide upstream PRoot source on request for 3 years. |
| **Samba `libtalloc`** (`libtalloc.so.2`) | `assets/{bin,lib}/libtalloc.so.2` & `lib/arm64-v8a/libtalloc.so` | **LGPL-3.0-or-later** | Loaded dynamically only by `proot`. Retain `WRITTEN_SOURCE_OFFER.txt`. |
| **GNU C Library subset** | `assets/glibc-min-arm64.tar` | **LGPL-2.1-or-later** | Unpacked only inside guest Linux rootfs. Retain `WRITTEN_SOURCE_OFFER.txt`. |
| **JSch** (`0.2.20`) | `com.github.mwiede:jsch:0.2.20` | **BSD-3-Clause** (+ JZlib BSD, jBCrypt ISC) | Retain verbatim `assets/licences/JSCH_LICENSE.txt` inside APK. |
| **Go Standard Library Runtime** | Linked into `lib/arm64-v8a/libsaifdaemon.so` (built from SAIF AI's `termux-daemon/server.go`) | **BSD-3-Clause** | Retain Go BSD-3-Clause attribution in `THIRD_PARTY_NOTICES.md`. |
| **Vosk, JNA, OkHttp, Coil, Commons-Compress, XZ, jsoup, AndroidX, Compose, Kotlin, Firebase** | Gradle dependencies (`app/build.gradle.kts`) | **Apache-2.0 / MIT / Public Domain / Google Terms** | Retain `assets/legal/THIRD_PARTY_NOTICES.md`. |
| **Debian 13 ("Trixie") rootfs** | Downloaded at runtime on device (`proot-distro` `v4.29.0`) | **Debian DFSG package licences** | Not bundled in the APK; downloaded directly by the end-user device at runtime. |

---

## Part 3 — Copyright Assignment / Relicensing Instrument (Fill-In Template for Buyer Transfer)

> *To transfer full ownership or grant an unrestricted commercial/proprietary relicensing right over the SAIF AI codebase to a buyer or acquiring entity, complete and sign the schedule below.*

### Schedule A — Parties & Effective Date

- **Assignor (Current Copyright Holder):** `________________________________________` ("Assignor")  
- **Assignee (Acquiring Owner / Licensee):** `________________________________________` ("Assignee")  
- **Assignment Effective Date:** `____ / ____ / 20____`  
- **Transferred Repository Commit / Release Tag:** `________________________________________`

### Schedule B — Grant of Rights

1. **Assignment of SAIF AI Owned Works:**  
   For good and valuable consideration (receipt and sufficiency of which are hereby acknowledged), Assignor hereby irrevocably assigns, transfers, and conveys to Assignee all right, title, and interest worldwide — including all copyrights, moral-right waivers to the fullest extent permitted by law, trade secrets, and rights to sue for past, present, and future infringement — in and to all original SAIF AI source code, build scripts, workspace daemon (`termux-daemon/server.go`), architecture, UI assets, and documentation listed in `tools/licence/saif_owned_files.txt` and `LICENSE` (collectively, the **"Assigned Software"**).
2. **Unrestricted Right to Rebrand & Relicense:**  
   Upon execution, Assignee is the sole copyright owner of the Assigned Software and may:
   - Replace `"Copyright (c) SAIF AI. All rights reserved."` in the 330 stamped source files and `LICENSE` with Assignee's own copyright notice and proprietary, EULA, SaaS, or open-source licence;
   - Change the Android `applicationId` (`com.saifai.app`), app name, icons, signing keys, and `SAIF_SOURCE_URL`; and
   - Distribute modified or unmodified binaries commercially without owing royalties or source-disclosure obligations on the Assigned Software.
3. **Preservation of Third-Party Notices:**  
   Assignee acknowledges that the unmodified third-party open-source components enumerated in **Part 2** remain governed by their respective upstream licences, and agrees to keep `THIRD_PARTY_NOTICES.md`, `assets/licences/JSCH_LICENSE.txt`, and `assets/licences/WRITTEN_SOURCE_OFFER.txt` (updated solely to reflect Assignee's contact URL for the 3-year source offer if Assignee distributes binaries containing `proot`, `libtalloc`, `glibc-min-arm64.tar`, or `sora-editor`) in binary distributions that include those components.

### Signatures

| **ASSIGNOR** | **ASSIGNEE** |
|---|---|
| Signature: `___________________________` | Signature: `___________________________` |
| Name: `________________________________` | Name: `________________________________` |
| Title: `_______________________________` | Title: `_______________________________` |
| Date: `________________________________` | Date: `________________________________` |
