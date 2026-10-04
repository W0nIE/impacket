## impacket patches

My two small fixes for [impacket](https://github.com/fortra/impacket).

**Problem:** `examples/nmapAnswerMachine.py` does not work in impacket on Python 3.
It crashes with `TypeError: cannot use a str to initialize an array with typecode 'B'`,
and it needs `uncrc32.py`, which was removed from impacket.
The script is deprecated, so it will not be fixed upstream
([issue #1406](https://github.com/fortra/impacket/issues/1406)).
These patches make it work again.

- **0001** — fixes the `TypeError` in `ImpactPacket.py`.
- **0002** — adds `uncrc32.py` (CRC32 reversing script) back to impacket.

`uncrc32.py` is also here as a separate file.

### How to use

```bash
git clone https://github.com/fortra/impacket
cd impacket
git am /path/to/patches/*.patch
```
