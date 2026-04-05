# cls-lizard

**cls-lizard** is an implementation of the **Lizard (LZ5)** compression algorithm for **FreeArc**.

Based on **Lizard v1.0** from the official repository:  
https://github.com/inikep/lizard

---

## Lizard Overview

Lizard (formerly **LZ5**) is a lossless compression algorithm with four operating modes:

- `fastLZ4`  
  Compression levels `-10 ... -19`  
  Designed for faster decompression than LZ4 (over 2000 MB/s)

- `LIZv1`  
  Compression levels `-20 ... -29`  
  Provides better compression than LZ4 while maintaining ~75% of its decompression speed

- `fastLZ4 + Huffman`  
  Compression levels `-30 ... -39`  
  Adds Huffman coding to `fastLZ4`

- `LIZv1 + Huffman`  
  Compression levels `-40 ... -49`  
  Achieves the best compression (comparable to `zlib` and lower levels of `zstd`/`brotli`) with ~1000 MB/s decompression speed

---

## Options

| Parameter | Description |
|------------|------------|
| `l=<level>` | Compression level `[10..49]` (default: `17`) |
| `b=<block_size>` | Block size used for compression (default: `2mb`) |

**Note**

Parameters can be specified without the `=` separator.

---

## Memory Requirements

Requires: 2 × block_size + 64 KB

---

## Support the Project

[![Support on Patreon](https://c5.patreon.com/external/logo/become_a_patron_button.png)](https://www.patreon.com/Shegorat)

If you find this project useful, consider supporting development on Patreon.
