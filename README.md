<img src="https://hacktoberfest.com/_next/static/media/opengraph.da6e44c0.png">

# <div align=center> DumprX </div>

## What this really is

You might've used firmware extractor via dumpyara from https://github.com/AndroidDumps/. This toolkit is revamped edition of the tools with some improvements and feature additions.

## The improvements over dumpyara

- [x] dumpyara's and firmware_extractor's scripts are merged with handpicked shellcheck-ed and pylint-ed improvements
- [x] The script can download and dump firmware from different filehosters such as Mega.NZ, Mediafire.com, AndroidFileHost.com and from Google Drive URLs
- [x] File as-well-as Folder as an input is processed thoroughly to check all kinds of supported firmware types
- [x] All the external tools are now inherited into one place and unnesessary files removed
- [x] Binary tools are updated to latest available source
- [x] LG KDZ utilities are updated to support latest firmwares
- [x] Installation requirements are narrowed down to minimal for playing with this toolkit
- [x] Recovery Dump is made too

## Recommendations before Playing with Firmware Dumper

This toolkit can run in any Debian/Ubuntu distribution, Ubuntu Bionic and Focal would be best, other versions are not tested.

Support for Alpine Linux is added and tested. You can give it a try.

For any other UNIX Distributions, please refer to internal [Setup File](setup.sh) and install the required programs via their own package manager.

## Prepare toolkit dependencies / requirements

To prepare for this toolkit, run [Setup File](setup.sh) at first, which is needed only one time. After that, run [Main Script](dumper.sh) with proper argument.

## Usage

Run this toolkit with proper firmware file/folder path or URL

```bash
./dumper.sh 'Firmware File/Extracted Folder -OR- Supported Website Link'
```

Help Context:

```text
  >> Supported Websites:
        1. Directly Accessible Download Link From Any Website
        2. Filehosters like - mega.nz | mediafire | gdrive | onedrive | androidfilehost
         >> Must Wrap Website Link Inside Single-quotes ('')
  >> Supported File Formats For Direct Operation:
         *.zip | *.rar | *.7z | *.tar | *.tar.gz | *.tgz | *.tar.md5
         *.ozip | *.ofp | *.ops | *.kdz | ruu_*exe
         system.new.dat | system.new.dat.br | system.new.dat.xz
         system.new.img | system.img | system-sign.img | UPDATE.APP
         *.emmc.img | *.img.ext4 | system.bin | system-p | payload.bin
         *.nb0 | .*chunk* | *.pac | *super*.img | *system*.sin
```

## How to use it to Upload the Dump in GitHub

- Copy your GITHUB_TOKEN in a file named .github_token and add your GitHub Organization name in another file named .github_orgname inside the project directory.
  - If only Token is given but Organization is not, your Git Username will be used.
- Copy your Telegram Token in a file named .tg_token and Telegram Chat/Channel ID in another file named .tg_chat file if you want to publish the uploading info in Telegram.

## Main Scripture Credit

As mentioned above, this toolkit is entirely focused on improving the Original Firmware Dumper available:  [Dumpyara](https://github.com/AndroidDumps/) [Phoenix Firmware Dumper](https://github.com/DroidDumps)

Credit for those tools goes to everyone whosoever worked hard to put all those programs in one place to make an awesome project.

## Download Utilities Credits

- mega-media-drive_dl.sh (for downloading from mega.nz, mediafire.com, google drive)
  - shell script, most of it's part belongs to badown by @stck-lzm
- afh_dl (for downloading from androidfilehosts.com)
  - python script, by @kade-robertson
- aria2c
- wget

## Internal Utilities Credits

- sdat2img.py (system-dat-to-img v1.2, python script)
  - by @xpirt, @luxi78, @howellzhu
- simg2img (Android sparse-to-raw images converter, binary built from source)
  - by @anestisb
- unsin (Xperia Firmware Unpacker v1.13, binary)
  - by @IgorEisberg
- extract\_android\_ota\_payload.py (OTA Payload Extractor, python script)
  - by @cyxx, with metadata update from [Android's update_engine Git Repository](https://android.googlesource.com/platform/system/update_engine/)
- extract-dtb.py (dtbs extractor v1.3, python script)
  - by @PabloCastellano
- dtc (Device Tree Compiler v1.6, binary built from source)
  - by kernel.org, from their [dtc Git Repository](https://git.kernel.org/pub/scm/utils/dtc/dtc.git)
- vmlinux-to-elf and kallsyms_finder (kernel binary to analyzable ELF converter, python scripts)
  - by @marin-m
- ozipdecrypt.py (Oppo/Oneplus .ozip Firmware decrypter v1.2, python script)
  - by @bkerler
- ofp\_qc\_extract.py and ofp\_mtk\_decrypt.py (Oppo .ofp firmware extractor, python scripts)
  - by @bkerler
- opscrypto.py (OnePlus/Oppo ops firmware extractor, python script)
  - by @bkerler
- lpunpack (OnePlus/Other super.img unpacker, binary built from source)
  - by @LonelyFool
- splituapp.py (UPDATE.APP extractor, python script)
  - by @superr
- pacextractor (Extractor of SpreadTrum firmware files with extension pac. See)
  - by @HemanthJabalpuri
- nb0-extract (Nokia/Sharp/Infocus/Essential nb0-extract, binary built from source)
  - by Heineken @Eddie07 / "FIH mobile"
- kdztools' unkdz.py and undz.py (LG KDZ and DZ Utilities, python scripts)
  - Originally by IOMonster (thecubed on XDA), Modified by @ehem (Elliott Mitchell) and improved by @steadfasterX
- RUU\_Decrypt\_Tool (HTC RUU/ROM Decryption Tool v3.6.8, binary)
  - by @nkk71 and @CaptainThrowback
- extract-ikconfig (.config file extractor from kernel image, shell script)
  - From within linux's source code by @torvalds
- unpackboot.sh (bootimg and ramdisk extractor, modified shell script)
  - Originally by @xiaolu and @carlitros900, stripped to unpack functionallity, by me @rokibhasansagar
- twrpdtgen by @SebaUbuntu

# Hacktoberfest

## What is Hacktoberfest?

A month-long celebration from October 1st - 31st sponsored by [Digital Ocean](https://hacktoberfest.digitalocean.com/) and [GitHub](https://github.com/blog/2433-celebrate-open-source-this-october-with-hacktoberfest) to get people involved in [Open Source](https://github.com/open-source). Create your very first pull request to any public repository on GitHub and contribute to the open source developer community.

[https://hacktoberfest.digitalocean.com/](https://hacktoberfest.digitalocean.com/)

## Getting started

- Fork this repository (Click the Fork button in the top right of this page, click your Profile Image)
- Clone your fork down to your local machine

```markdown
git clone https://github.com/your-username/python_codes.git
```

- Make your changes ( eg: Add Some python code )
- Commit and push

```markdown
git add .
git commit -m 'Commit message'
git push origin branch-name
```

## How to Participate

- Create a new pull request from your forked repository (Click the `New Pull Request` button located at the top of your repo)
- Wait for your PR review and merge approval!
- **Star this repository** 
- Enjoy & Wait for your free swags!
