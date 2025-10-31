
**Dn-Famitracker 0.5.2 (improve instrument overflow)**

This clone is a version with a modified NSF file memory layout that allocates 4 pages for instrument data.

It can hold up to 16KB of instrument data, reducing the possibility of instrument overflow during NSF export.

(Originally, when using DPCM at 16KB or more, the Instrument has a limit of about 4KB.)
 
 

**File memory map for NSFtype:bankswitched**

Official Implementation:
| PRG-ROM size | CPU Address | Data type | Bank capabilities |
| --- | --- | --- | --- |
|  | $8000 | Famitrakcer Driver  | Non-bankswitched ($8000 ~ $9FFF, 8KB) |
| 8KB |  |  |  |
|  | $A000 | Seqence+Instrument | 4KB Non-bankswitched |
| 16KB  | $B000 | flame + pattern data |  4KB bankswitching |
|  | $C000 | DPCM | 4KB bankswitching x 3pages ($C000 ~ $EFFF, 12KB) |
| 24KB |  |  | |
|  | $E000 |  |  |
| 32KB |  |  | (Non-bankswitched for TNS cart) |

Modified Implementation 

v20251031:
(This layout does not play NSF files using DPCM correctly on TNS and Everdrive flashcarts.)
| PRG-ROM size | CPU Address | Data type | Bank capabilities |
| --- | --- | --- | --- |
|  | $8000 | Famitrakcer Driver | Non-bankswitched ($8000 ~ $9FFF, 8KB) |
| 8KB |  |  |  |
|  | $A000 | Seqence+Instrument | Non-bankswitched ($A000 ~ $DFFF, 16KB) |
| 16KB  |  |  |  |
|  | $C000 |  |  |
| 24KB |  |  |  |
|  | $E000 | flame + pattern data | 4KB bankswitching |
| 32KB | $F000 | DPCM | 4KB bankswitching |

 
v20251101 later:
| PRG-ROM size | CPU Address | Data type | Bank capabilities |
| --- | --- | --- | --- |
|  | $8000 | Famitrakcer Driver | Non-bankswitched ($8000 ~ $9FFF, 8KB) |
| 8KB |  |  |  |
|  | $A000 | Seqence+Instrument | Non-bankswitched ($A000 ~ $CFFF, 12KB) |
| 16KB  |  |  |  |
|  | $C000 |  |  |
| 24KB | $D000 | flame + pattern data | 4KB bankswitching |
|  | $E000 | DPCM | 4KB bankswitching |
| 32KB | $F000 |  | (Non-bankswitched for TNS and Everdrive flashcarts) |


---

# ![Dn-FamiTracker banner logotype](docs/dn_logo.svg)

Dn-FamiTracker is a fork of 0CC-FamiTracker that incorporates numerous fixes and
features.

---

## About

The meaning of the name "Dn" is "Derivative n", which alludes to this fork being
the nth derivative of the original FamiTracker program.

## Notable additions

- New effects: `Nxx`, `=xx`, `Kxx`
- Support for OPLL-as-VRC7
- NSF 2.0 and NSFe export support
- Fixed metadata support on NSF 2.0 and NSFe export
- Complete text import/export
- DPCM sample bit order reversal
- Multitrack per-channel `.wav` export
- More accessible DPCM pitch preview
- More accessible VRC7 patch and envelope editing
- Improved FDS, N163 VRC7 and 2A03 emulation
- Restored Help manual, now under maintenance at
  [Dn-help](https://github.com/Dn-Programming-Core-Management/Dn-help)
- and more to come, see the
  [release page](https://github.com/Dn-Programming-Core-Management/Dn-FamiTracker/releases)
  and the [changelog](docs/CHANGELOG.md) for more info

## Downloads

- Latest release:
	- [![Latest release](https://img.shields.io/github/v/release/Dn-Programming-Core-Management/Dn-FamiTracker?sort=semver&display_name=release&logo=github&style=flat-square)](https://github.com/Dn-Programming-Core-Management/Dn-FamiTracker/releases/latest)
- GitHub Actions automated builds:
	- [![GitHub Actions](https://img.shields.io/github/actions/workflow/status/Dn-Programming-Core-Management/Dn-FamiTracker/build-artifact.yml?logo=github&style=flat-square)](https://github.com/Dn-Programming-Core-Management/Dn-FamiTracker/actions/workflows/build-artifact.yml)

### AppVeyor CI build notice

- Due to delayed AppVeyor reintegration, builds for commits `dc4c9e86` to
  `21413603` are not available.
- Due to delayed AppVeyor branch reconfiguration, builds for commits `bc46c86c`
  to `a591d154` are not available.
- Due to less reliability, AppVeyor builds beyond `2c997736` are not available.

### Legacy AppVeyor automated builds

- Legacy AppVeyor automated D.P.C.M. builds:
	- [![AppVeyor](https://img.shields.io/appveyor/build/Gumball2415/dn-famitracker?logo=appveyor&style=flat-square)](https://ci.appveyor.com/project/Gumball2415/dn-famitracker/history)
- Legacy AppVeyor Gumball2415 builds:
	- [![AppVeyor](https://img.shields.io/appveyor/build/Gumball2415/dn-famitracker-legacy?logo=appveyor&style=flat-square)](https://ci.appveyor.com/project/Gumball2415/dn-famitracker-legacy/history)

## Licenses

The application is distributed under the
[GPLv3+ license](https://www.gnu.org/licenses/gpl-3.0.en.html), or any later
version.

For more details, view the [license](LICENSE.md).

## Contributing

[Contributing and compiling](./docs/CONTRIBUTING.md)

## Program lineage

- nyanpasu64 0CC-FamiTracker (archived): <https://github.com/nyanpasu64/j0CC-FamiTracker/>
- 0CC-FamiTracker: <https://github.com/HertzDevil/0CC-FamiTracker/>
- FamiTracker: <https://famitracker.com/>
