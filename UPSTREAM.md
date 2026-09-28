# Upstream provenance

- Source: [AFLplusplus/LibAFL](https://github.com/AFLplusplus/LibAFL)
- Version: `0.16.1`
- Imported upstream commit: `92ad89454765440c7c03b87b11d5dbde753f9633`
- This repository starts with a source snapshot; upstream history is not imported.
  Original authorship, file headers and license texts are retained.

## Maintained changes

1. `crates/libafl_qemu/src/qemu/mod.rs`: add `QemuParams::CliBytes`,
   `QemuCliBytes` and `to_cli_bytes`, preserving arbitrary non-NUL argument bytes
   through QEMU initialization. The String API is retained. The source patch is
   documented in GuestWeave's `patches/libafl-qemu-cli-bytes.patch` and is already
   integrated in this repository; do not apply it again.
2. `crates/libafl_qemu/libafl_qemu_build/src/build.rs`: pin the maintained
   Firmenstein QEMU bridge URL and snapshot revision.
3. `crates/libafl_qemu/libvharness_sys/build.rs`: pin the maintained Firmenstein
   libvharness URL and snapshot revision.
4. Preserve the upstream README as `README.upstream.md`, add maintenance docs
   and local output ignore rules, and omit the inherited GitHub build workflow.

No other upstream runtime implementation is changed in the initial snapshot.
Only the Linux/glibc usermode build used by GuestWeave is validated here.

## Updating

Keep local changes reviewable against the upstream commit above. Update QEMU
and libvharness pins deliberately, run GuestWeave's cold offline build and real
guest contract matrix, and then update its dependency manifest with the new
LibAFL commit and changed-file hashes. Preserve upstream licenses and notices.

The upstream workspace uses `MIT OR Apache-2.0`; see LICENSE-MIT,
LICENSE-APACHE and file-specific notices. QEMU carries its own GPL and
component licenses; this repository's license does not replace them.
