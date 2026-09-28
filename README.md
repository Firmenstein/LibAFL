# LibAFL for GuestWeave

This repository contains the LibAFL version maintained by
[Firmenstein](https://github.com/Firmenstein) for
[GuestWeave](https://github.com/Firmenstein/GuestWeave), its guest intervention runtime.

It is based on LibAFL **0.16.1** with a byte-preserving QEMU command-line API.
GuestWeave uses this API to pass non-UTF-8 guest arguments without lossy String
conversion. Existing String-based callers remain supported.

The QEMU bridge and libvharness build dependencies point to pinned source
snapshots maintained in the same organization. Use GuestWeave's dependency
preparation script and build guide to obtain the matched set; no manual patch
application is needed.

See [UPSTREAM.md](UPSTREAM.md) for exact provenance and changes, and the
[upstream README](README.upstream.md) for general LibAFL documentation.
Upstream [Apache-2.0](LICENSE-APACHE) and [MIT](LICENSE-MIT) license texts and
file-specific notices are preserved.
