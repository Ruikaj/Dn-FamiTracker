
Dn-Famitracker 0.5.2 ExInst (Improve instrument overflow, Increase Instrument capacity)

Improvements・Changes (2026/04/06):
- Modified NSF file memory layout that allocates 3 pages for instrument data.

    It can hold up to 12KB of instrument data, reducing the possibility of instrument overflow during NSF export.

    (Originally, when using DPCM at 16KB or more, the Instrument has a limit of about 4KB.)

- The maximum number of instruments and DPCM samples has been increased to 127 each.

改善・変更点：
- インストルメントデータ用に3ページを割り当てるよう、NSFファイルのメモリレイアウトを変更

    最大12KBのインストルメントデータを格納でき、NSFエクスポート時のInstrument Oveflowの可能性を低減

    （元々は16KB以上のDPCMを使用する場合はインストルメントデータは約4KB以下に制限される）

- インストルメントとDPCMサンプルの最大数をそれぞれ127に拡張

Note 注意:
Instead of .dnm files from the official version, please load FamiTracker Text files exported from the official version.
The.dnm project save files for this fork version are no longer compatible with those from the official version.

公式バージョンからのプロジェクトのロードは、.dnmの代わりに公式バージョンからエクスポートしたFamitracker Textをロードして下さい。
このフォークの.dnmプロジェクトデータは公式版のものとは互換性はありません。


--------------------------------------------------------------------------------

     ___            ___ __ __  __ ___ _____ ___    __  ___ _  _____ ___
  /=|   \ _ _  ___ | __/_ |  \/  |_ _|_   _| _ \  /_ |/ __| |/ / __| _ \===/
 /  | |) | ' \|___|| _/ _ | |\/| || |  | | |   / / _ | (__| ' <| _||   /  /
/===|___/|_||_|    |_/_/ _|_|  |_|___| |_| |_|_\/_/ _|\___|_|\_\___|_|_\=/

Version 0.5.2 - August 18, 2025

--------------------------------------------------------------------------------

Dn-FamiTracker is a fork of 0CC-FamiTracker that incorporates numerous fixes and
features.

The meaning of the name "Dn" is "Derivative n", which alludes to this fork being
the nth derivative of the original FamiTracker program.



Notable additions
-----------------

- New effects: `Nxx`, `=xx`, `Kxx`
- Support for OPLL-as-VRC7
- NSF 2.0 and NSFe export support
- Fixed metadata support on NSF 2.0 and NSFe export
- Complete text import/export
- DPCM sample bit order reversal
- Multitrack per-channel .wav export
- More accessible DPCM pitch preview
- More accessible VRC7 patch and envelope editing
- Improved FDS, N163 VRC7 and 2A03 emulation
- Restored Help manual, now under maintenance at Dn-help
    - <https://github.com/Dn-Programming-Core-Management/Dn-help>



License
-------

The application and source code are distributed under the GPLv3+ license, or any
later version.

<https://www.gnu.org/licenses/gpl-3.0.en.html>

For more details, view the LICENSE.md file.


Uninstalling and misc.
----------------------

To uninstall, run "Dn-FamiTracker.exe /unregister". This will remove the file
association.

If you have problems viewing the help manual (Dn-FamiTracker.chm), right click 
it and open properties, then click the "Unblock" button in the general tab.



Contact and links
-----------------

GitHub repo: https://github.com/Dn-Programming-Core-Management/Dn-FamiTracker
Help manual repo: https://github.com/Dn-Programming-Core-Management/Dn-help
FamiTracker: http://famitracker.com/
FamiTracker.org community Discord: https://discord.gg/3fBEEyKfMn
