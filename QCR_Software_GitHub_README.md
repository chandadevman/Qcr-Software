# QCR Software

Offline color-code generation, scanning and Ed25519 signature verification. Native Android app, Python reference implementation, development APK and encrypted source archive.

## Repository files

| File | Purpose | Bytes |
|---|---|---:|
| `QcR_Android_0.1.0_debug.apk` | Installable Android 13+ development build | 16863473 |
| `QCR_Software_Encrypted.zip` | AES-256 encrypted copy of the complete source ZIP | 19199382 |

Save this document as `README.md` in the repository. Upload the APK and encrypted
ZIP as separate files. Keep `QCR_PRIVATE_KEY_DO_NOT_UPLOAD.txt` outside the repository.
Also keep the original unencrypted source ZIP and extracted source outside the
public repository if you intend to restrict source access.

## Current capabilities

- Native Java color-code encoding and decoding, compatible with the Python reference.
- CameraX scanning pipeline, image import, unsigned generation and PNG export.
- Ed25519 signature verification using explicitly imported public issuer keys.
- Local history and trust settings; no Internet permission in this development APK.

## Status and evidence

REAL: Android 0.1.0-debug built, signed, installed and exercised on an Android API 35
emulator. Python reference remains 0.4.0. The previous source archive is unchanged.

| Validation | Result |
|---|---:|
| Python regression | 136 tests passed |
| Native codec | 513 assertions passed |
| JVM security and camera helpers | 21 tests passed |
| Python/Java interoperability | 255 mandatory + 1 exploratory checks passed |
| Android instrumentation | 8 tests passed |

SIMULATED: Android emulator hardware and generated/transformed image fixtures.
NOT PROVEN: physical Galaxy A56 camera reliability, printed-code qualification,
phone performance or production/store readiness. PLANNED: physical-device acceptance.
ESTIMATED: no overall completion percentage or phone latency estimate is claimed.
QcR remains separate from VciC.

## Open the encrypted source

Use an archive application that supports AES-256 encrypted ZIP, such as
[7-Zip](https://www.7-zip.org/). Enter the separately supplied archive key as its
password. Extract `QcR_Android_Runtime_Pass_1.zip`, then extract that ZIP normally.
The inner ZIP includes source, tests, build instructions, manifests, samples and
rollback archives. The outer ZIP exposes only the inner ZIP's filename and size;
the source contents and internal source filenames are inside the encrypted entry.

The source archive successfully decrypted byte-for-byte to its original SHA-256.
Missing keys, an incorrect key and modified ciphertext were rejected in testing.

The public APK is not encrypted by this source-archive password and can be run
and analyzed independently. It uses a public development signing key, not a
production release identity. Archive encryption does not rotate Android signing
or issuer keys and does not grant or revoke access to copies already decrypted.

## SHA-256

```text
7ebc9db38ecc9012268e029474beda3bd6e88917aebd2901e3086c91694b3c3d  QcR_Android_0.1.0_debug.apk
3fe9d6891180ff1ea8a429259f437f5c0bb03e83dc5b81799fc19d1c3550a8ce  QCR_Software_Encrypted.zip
011c5381e271803f74633cfe98c17771f71f3fe5ef21f880a0bab5a377324bdf  QcR_Android_Runtime_Pass_1.zip (after decryption)
```

Packaging date: November 18, 2026 (America/Chicago).
