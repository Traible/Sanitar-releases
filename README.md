# Sanitar

**Finds and removes malware that has dug into Windows — hidden miners, RDP backdoors, antivirus blockers.**

[Русская версия](README.ru.md)

Sanitar does not hunt for viruses by signature. It looks for the ways malware keeps itself alive and protected: scheduled tasks, autostart entries, services, fake system files, a disabled Microsoft Defender, AppLocker and IFEO blocks, the hosts file and RDP Wrapper.

One portable `.exe` for Windows 10/11 x64 — nothing to install.

## Download

**[Sanitar.exe — latest version](https://github.com/Traible/Sanitar-releases/releases/latest/download/Sanitar.exe)**

This link always points to the newest build, so you can bookmark it or send it to colleagues. The changelog and SHA-256 of every version are on the [releases page](https://github.com/Traible/Sanitar-releases/releases).

## How to use

1. Download `Sanitar.exe`, ideally to a USB stick: an infected PC may refuse to open websites.
2. Run it and accept the administrator prompt.
3. Choose **Scan and clean** (`Проверить и вылечить`). Sanitar shows what it found before it changes anything.
4. Didn't help? Choose **Collect log for analysis** (`Собрать лог для анализа`) and send the zip to whoever reviews the logs. User and computer names are masked in the log.

Everything removed goes to quarantine (`C:\Sanitar`), every change is written to a journal, and a cleanup can be undone from the menu. A system restore point is created before cleaning.

## Verify the file

```powershell
(Get-FileHash .\Sanitar.exe -Algorithm SHA256).Hash
```

Compare it with the hash in the release notes or in `Sanitar.exe.sha256`.

The file is not code-signed, so SmartScreen may warn about an unknown publisher: **More info** → **Run anyway**.

Sanitar does not replace a regular antivirus. The source code is closed; this repository only publishes ready-made builds.
