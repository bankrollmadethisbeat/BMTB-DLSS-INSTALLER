# BMTB FiveM DLSS 5 Installer

Unofficial community utility that installs the bundled DLSS 5 files into FiveM.

**BMTB â€” Better Mechanics. Trusted Builds.**

## Official download

**https://github.com/bankrollmadethisbeat/BMTB-DLSS-INSTALLER/releases/latest**

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

---

# âš–ï¸ Disclaimer

**BMTB FiveM DLSS 5 Installer is an unofficial community utility.**

This project is **not affiliated with, sponsored by, approved by, or endorsed by**:

- NVIDIA Corporation
- Rockstar Games
- Take-Two Interactive
- Cfx.re
- FiveM

NVIDIA, GeForce, RTX, DLSS, GTA, Grand Theft Auto, FiveM, ReShade, and other names, technologies, logos, and trademarks belong to their respective owners.

Third-party files, libraries, technologies, and components included with or supported by this utility remain the property of their respective owners and may be subject to their own respective licenses and terms.

BMTB does not claim ownership of third-party technologies distributed or used with the installer.

---

# ðŸ“¢ Important Notice

Use of graphics modifications, injected DLLs, ReShade components, or other modifications may be affected by future updates to:

```text
FiveM
GTA V
Windows
NVIDIA Drivers
ReShade
Other Graphics Mods
```

A configuration that works today may require repair or updates in the future.

BMTB cannot guarantee compatibility with every system or every combination of graphics modifications.

---

## Third-party authors and communities

The bundled DLSS 5 payload is built from work by these projects and communities. BMTB packages and automates their plug-and-play layout; it does not replace or claim their authorship.

| Component | Author / project | Links |
|-----------|------------------|-------|
| **RenoDX DLSS 5** (experimental DLSS add-on) | **shortfuse** (CLShortFuse) | [RenoDX Discord](https://discord.gg/renodx) Â· [Patreon](https://www.patreon.com/CLShortFuse) |
| **ReShade** (add-on framework, `dxgi.dll`) | **crosire** | [ReShade Discord](https://discord.com/invite/PrwndfH) Â· [Patreon](https://www.patreon.com/crosire) |
| **FiveM DLSS 5 plug-and-play packages** | **Marius PCMR** | [Discord](https://discord.gg/9w9JE24TWm) Â· [Patreon](https://www.patreon.com/pcmrmods) |
| **DLSS / Streamline** (`nvngx_*`, `sl.*` libraries) | **NVIDIA Corporation** | NVIDIA technology â€” not owned by BMTB |

Using RenoDX DLSS 5 and custom DLSS DLLs in FiveM involves DirectX pipeline injection. Some server anti-cheats or server rules may flag modified `.addon64` / `.dll` files. Check your server's modding rules before joining. Do not use these files in official GTA Online.
