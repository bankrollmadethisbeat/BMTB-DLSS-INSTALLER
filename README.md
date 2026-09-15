# BMTB FiveM DLSS 5 Installer

Unofficial community utility that installs the bundled DLSS 5 files into FiveM.

BMTB does **not** own the DLSS, Streamline, RenoDX, or ReShade files. Credits: RenoDX by shortfuse, ReShade by crosire, FiveM plug-and-play package by Marius PCMR. Not affiliated with NVIDIA, Rockstar Games, Take-Two, Cfx.re, or FiveM.

**BMTB â€” Better Mechanics. Trusted Builds.**

## Requirements

- Windows 10 / 11 x64
- .NET 8 SDK (to build)
- End users do **not** need the .NET runtime â€” the published EXE is self-contained

## Layout

```text
bmtb_installeR/
  BMTB.FiveMDLSSInstaller.sln
  BMTB.FiveMDLSSInstaller/          WPF app
  BMTB.FiveMDLSSInstaller.Tests/    Safety tests (FakeFiveM only)
  TestData/FakeFiveM/               Debug install target
  tools/prepare-payload.ps1         Copies packages into Resources\Payload
  build-release.ps1                 Tests + publish
  dist/                             Published EXE
```

## Payload

The original ZIP files are **not** embedded. `tools\prepare-payload.ps1` copies files from the sibling package folders:

- Shared files â†’ `Resources\Payload\Common\`
- `nvngx_dlssnr.dll` â†’ `RTX20_30_40\` and `RTX50\`
- `desktop.ini` and `Tutorial Install.txt` are excluded
- SHA-256 hashes are written to `hashes.json`

The app streams those files from the assembly. Nothing is downloaded at install time.

To replace the DLSS files, drop updated packages next to this folder, run `tools\prepare-payload.ps1 -Force`, then rebuild.

## Detection

- **FiveM:** `%LOCALAPPDATA%\FiveM\FiveM.app` in Release. Debug builds default to `TestData\FakeFiveM\FiveM.app` so live FiveM is never touched by tests.
- **GPU:** local WMI `Win32_VideoController`. RTX 20/30/40 vs RTX 50. Manual override always available.

## Backup / restore

- Original backup: `FiveM.app\BMTB_DLSS5_Backup\original\` â€” written once, never overwritten by repair
- Session snapshot: used only to roll back a failed install
- Restore Original FiveM Files puts back pre-BMTB files and deletes only files this installer added
- Unrelated plugins and shaders are never deleted

## Version

Bump **only** `<Version>` in `BMTB.FiveMDLSSInstaller.csproj`. The UI, About page, install fingerprint, and updater all read the assembly version. About also shows `Build 100` from `AppConstants.BuildNumber`.

## Official download

**https://github.com/bankrollmadethisbeat/BMTB-DLSS-INSTALLER/releases/latest**

The old `bankrollmadethisbeat313/BMTB-FiveM-DLSS5-Installer` repo is redirect-only and must not be used for downloads.

## GitHub updates

Edit `BMTB.FiveMDLSSInstaller\UpdateConfig.cs`:

```csharp
public const string GitHubOwner = "bankrollmadethisbeat";
public const string GitHubRepository = "BMTB-DLSS-INSTALLER";
```

Public repo only. No token is embedded. The app checks `GET /repos/{owner}/{repo}/releases/latest` in the background, at most every 6 hours. Offline use is unaffected.

Release asset must be named exactly:

```text
BMTB_FiveM_DLSS5_Installer.exe
```

### Publishing a GitHub Release

1. Bump `<Version>` in the csproj (for example `1.1.0`)
2. Run `.\build-release.ps1`
3. Create a GitHub Release tagged `v1.1.0`
4. Title: `BMTB FiveM DLSS 5 v1.1.0`
5. Paste release notes
6. Upload `dist\BMTB_FiveM_DLSS5_Installer.exe`
7. Publish the release (stable, not prerelease)

Existing installers will then see **UPDATE AVAILABLE**.

Code signing is not required for development. `UpdateVerificationService` already verifies SHA-256 when GitHub provides a digest. Authenticode can be enabled later without rewriting the updater. Leave `RequireAuthenticodeSignature` off until every future release is signed.

## Build (Debug)

```powershell
dotnet test .\BMTB.FiveMDLSSInstaller.sln -c Debug
dotnet build .\BMTB.FiveMDLSSInstaller\BMTB.FiveMDLSSInstaller.csproj -c Debug
```

Debug builds use FakeFiveM and show an Advanced debug panel. Release builds never do.

## Publish

```powershell
.\build-release.ps1
```

Output:

```text
dist\BMTB_FiveM_DLSS5_Installer.exe
```

The EXE is large because the DLSS payload is embedded. That is expected.
