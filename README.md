# ネット備蓄いかすみ（Ikasumi Offline Net）

ネットが切れても、日本語で調べられる備えです。Windows 11 のアプリです（Microsoft Store で配布予定）。

- 紹介：https://ikasumiworks.com/ikasumi/
- サポート・問い合わせ：https://ikasumiworks.com/ikasumi/support
- プライバシーポリシー：https://ikasumiworks.com/ikasumi/privacy

不具合や読みにくい所は、この Issues か ikasumi.works@gmail.com に知らせてください。安全の穴（脆弱性）は、公開の場ではなくメールで知らせてください。

---

Ikasumi Offline Net keeps Wikipedia-style references, maps and an optional local AI usable during internet outages. Windows 11 app (Microsoft Store, coming soon).

- About: https://ikasumiworks.com/ikasumi/en/
- Support: https://ikasumiworks.com/ikasumi/en/support
- Privacy: https://ikasumiworks.com/ikasumi/en/privacy

Report bugs here in Issues or to ikasumi.works@gmail.com. Please report security issues by email, not in public Issues.

---

## Source code of the programs shipped with the app

The app ships `kiwix-serve.exe` and `kiwix-manage.exe` from kiwix-tools 3.8.1 (GPL-3.0), unchanged, taken from
https://download.kiwix.org/release/kiwix-tools/kiwix-tools_win-x86_64-3.8.1.zip

| File in `source/` | Program | License | Taken from |
|---|---|---|---|
| `kiwix-tools-3.8.1.tar.xz` | kiwix-tools 3.8.1 | GPL-3.0 | https://download.kiwix.org/release/kiwix-tools/ |
| `libkiwix-14.1.1.tar.xz` | libkiwix 14.1.1 | GPL-3.0 | https://download.kiwix.org/release/libkiwix/ |
| `libzim-9.4.0.tar.xz` | libzim 9.4.0 | GPL-2.0 | https://download.openzim.org/release/libzim/ |
| `xapian-core-1.4.26.tar.xz` | Xapian (xapian-core) 1.4.26 | GPL-2.0-or-later | https://oligarchy.co.uk/xapian/1.4.26/ |
| `libmicrohttpd-0.9.76.tar.gz` | GNU libmicrohttpd 0.9.76 | LGPL-2.1-or-later | https://ftpmirror.gnu.org/libmicrohttpd/ |

The SHA-256 of each file is in `source/SHA256SUMS.txt`. The kiwix-tools file also matches the MD5 published by Kiwix.

The versions above are the ones kiwix-build used for the kiwix-tools 3.8.1 release (kiwix-build commit `6f3a27d`, `kiwixbuild/versions.py`). The Windows build of Xapian comes from [openzim/xapian-meson](https://github.com/openzim/xapian-meson) (commit `d3efba1`), which is Xapian 1.4.26 with Meson build files and small changes in `common/io_utils.cc` and `common/safesysstat.h` (plus its tests). The Meson build files are not in `source/`; the build is done with [kiwix-build](https://github.com/kiwix/kiwix-build). Kiwix also patches libmicrohttpd with Meson files, which are not in `source/` either.

The other libraries built into those programs (curl, pugixml, zstd, zlib, ICU, docopt.cpp and mustache) use permissive licenses that do not require shipping source, and are listed in `THIRD-PARTY-NOTICES.txt` inside the app. Their source is available from the upstream projects, and from the author on request by e-mail: ikasumi.works@gmail.com

## アプリに同梱しているプログラムのソース

アプリには、kiwix-tools 3.8.1（GPL-3.0）の `kiwix-serve.exe` と `kiwix-manage.exe` を、手を加えずに入れています。入手元：
https://download.kiwix.org/release/kiwix-tools/kiwix-tools_win-x86_64-3.8.1.zip

上の表のファイルを `source/` に置いています。各ファイルの SHA-256 は `source/SHA256SUMS.txt` にあります。kiwix-tools のファイルは、Kiwix が公開している MD5 とも一致します。

上の版は、kiwix-tools 3.8.1 のリリースで kiwix-build が使った版です（kiwix-build のコミット `6f3a27d`、`kiwixbuild/versions.py`）。Windows 版の Xapian は [openzim/xapian-meson](https://github.com/openzim/xapian-meson)（コミット `d3efba1`）から作られます。これは Xapian 1.4.26 に Meson の組み立て用ファイルと、`common/io_utils.cc`・`common/safesysstat.h`（とテスト）の小さな修正を足したものです。Meson の組み立て用ファイルは `source/` に入れていません。組み立ては [kiwix-build](https://github.com/kiwix/kiwix-build) で行います。libmicrohttpd に Kiwix が足している Meson 用ファイルも入れていません。

そのほかに組み込まれているライブラリ（curl、pugixml、zstd、zlib、ICU、docopt.cpp、mustache）は、ソースの写しを付けなくてよい許諾のものです。アプリ内の `THIRD-PARTY-NOTICES.txt` に載せています。ソースは各開発元から入手できます。作者へのメール（ikasumi.works@gmail.com）でも請求できます。
