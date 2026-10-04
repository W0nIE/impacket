# impacket patches

My two small fixes for [impacket](https://github.com/fortra/impacket).

- **0001** — fixes a Python 3 error in `ImpactPacket.py`.
- **0002** — adds `uncrc32.py` (CRC32 reversing script) back to impacket.

`uncrc32.py` is also here as a separate file.

## How to use

```bash
git clone https://github.com/fortra/impacket
cd impacket
git am /path/to/patches/*.patch
```
