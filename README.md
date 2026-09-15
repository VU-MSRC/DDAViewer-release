# DDA Viewer — downloads

**[⬇ Download the latest release](../../releases/latest)**

DDA Viewer is a Windows desktop application from the Vanderbilt Mass
Spectrometry Research Center for viewing, searching and analysing
data-dependent-acquisition (DDA) proteomics experiments from Bruker `.d` and
Thermo `.raw` files. This repository holds only the installers; it exists so
the downloads are public while the source stays in the lab's private
repository.

## What to download

| File | What it is | Do you need it? |
|---|---|---|
| `DDAViewer-Setup-<version>.exe` | The application. Python, Qt, the Thermo reader and both search engines (SAGE and Comet) are bundled — **no prerequisites**, and your own Python or R installations are not touched. | Yes |
| `DDAViewer-MSstats-Payload-<version>.exe` | A private copy of R with MSstats, for running new differential-abundance analyses inside the application. R is GPL-licensed, so it ships as a separate optional download. | Only if you want to *run* MSstats. Results already stored in a `.ddaa` file display without it. |
| `SHA256SUMS-*.txt` | Checksums of the files above. | To verify a download (see below). |
| `latest.json` | Machine-readable description of the release. | Used by automated update checks; not for people. |

Install the application first, then the MSstats payload if you want it — the
payload finds the application through its uninstall entry and installs beside
it. To upgrade, run the new `DDAViewer-Setup` over the existing installation;
settings and files are kept.

## Windows SmartScreen

The installer is not code-signed, so the first time you run it Windows shows
**"Windows protected your PC"**. Click **More info**, then **Run anyway**. If
you would rather check the file before trusting it, compare its checksum with
the published one:

```powershell
Get-FileHash .\DDAViewer-Setup-0.1.5.exe -Algorithm SHA256
Get-Content .\SHA256SUMS-full.txt
```

The two hex strings must match.

## Requirements

Windows 10 or 11, 64-bit. About 700 MB of disk for the application and a
further 500 MB for the MSstats payload. Reading Thermo `.raw` files uses the
.NET Framework already built into Windows.

## Licences

DDA Viewer itself is MIT-licensed. The installer includes the Thermo Fisher
Scientific RawFileReader libraries under the RawFileReader Software Licence
Agreement of Thermo Finnigan LLC: you may use them within this application on
computers you control, but you may **not** extract, repackage or redistribute
them — direct colleagues here rather than sending them a copy. The full terms
are shown by the installer and in the application's About box. Third-party
Python components are listed with their licences in `THIRD-PARTY-NOTICES.md`,
installed alongside the application.

## Problems

Open an issue in this repository with the version (shown bottom-right in the
application), your Windows version, and what you were doing. Do not attach
raw data files to issues.
