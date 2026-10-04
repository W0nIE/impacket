# impacket patches

My small fixes for [impacket](https://github.com/fortra/impacket).
This repository keeps only my changes, not the full impacket source.

## Contents

| File | What it does |
|------|--------------|
| `patches/0001-Fixed-a-typecast-issue-in-ImpactPacket.py.patch` | Fixes `TypeError: cannot use a str to initialize an array with typecode 'B'` in `impacket/ImpactPacket.py` (`set_bytes_from_string` now encodes the string to bytes). |
| `patches/0002-ReAdd-a-file-uncrc32.py.patch` | Adds `examples/uncrc32.py` back to impacket. |
| `examples/uncrc32.py` | The CRC32 "reversing" script itself (append 4 bytes to data to get a chosen CRC32). Based on *Reversing CRC – Theory and Practice*, HU Berlin, SAR-PR-2006-05. |

## How to apply

```bash
git clone https://github.com/fortra/impacket
cd impacket
git am /path/to/patches/*.patch
```

The patches were made on top of impacket commit `3c6713e` (July 2022).
On newer versions they may need small changes.

To check first without changing anything:

```bash
git apply --check /path/to/patches/*.patch
```
