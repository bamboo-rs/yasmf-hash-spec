# YASMF-Hash

> Yet-Another-Smol-Multi-Format - Hash

Forked from [YAMF Hash](https://github.com/AljoschaMeyer/yamf-hash) but with smol 32 bit digest length using blake3.

Self-describing cryptographic hashes. Unlike the [multiformats](https://github.com/multiformats/multihash) one, this does not try to capture as many hash functions as possible, rather it starts out with a single one and will add new ones only when the old one gets broken.

A yamf-hash is a pair of a numeric identifier for a hash function, and a hash digest. The currently supported functions:

| Hash Function                                  | Numeric Id | Digest Length (Bytes) |
|------------------------------------------------|------------|-----------------------|
| [Blake3](https://github.com/BLAKE3-team/BLAKE3/) | 0          | 32                    |

## Binary Encoding

The binary encoding of a yamf-hash is the binary [stlv](https://github.com/AljoschaMeyer/stlv) encoding with the numeric id from the above table as the type, and the digest as the value.

A *canonic binary yamf-hash* uses the canonic binary encoding of the stlv.
