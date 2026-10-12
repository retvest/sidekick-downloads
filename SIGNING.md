# Verify a Sidekick download

The Linux 0.16.2-preview.2 AppImage has a **detached OpenPGP signature**: a
separate `.asc` file signed with Retvest's release key. The AppImage itself
is unchanged. The release checksum manifest also has a detached signature.

This lets you check that the downloaded file matches what the holder of that
key signed. It does not certify the software's safety, independently verify
Retvest's legal identity, or establish that the application works. The preview
remains **UNVERIFIED**. Windows has no Authenticode signature; Mac has no
Developer ID signature or notarization. GPG does not remove those OS warnings.

## Release key

Identity: `Retvest Sidekick releases <cliffordprince257@gmail.com>`

RSA-3072 primary key fingerprint:

```text
8C21 A0CF 3C63 9636 5F9A 2252 0652 2F43 9578 25FD
```

Download the [public key](retvest-sidekick-signing-key.asc). Compare its **full
fingerprint** with the one published at https://retvest.com/sidekick/#downloads
before relying on it. A name or short key ID alone is insufficient. This is a
new release identity; the website and this repository publish its fingerprint.

## Linux verification

Install GnuPG from your Linux distribution's package manager if needed. Download
these three files from the [release assets](https://github.com/retvest/sidekick-downloads/releases/tag/v0.16.2-preview.2)
into the same directory:

- `Sidekick-0.16.2-preview.2-linux-x86_64.AppImage`
- `Sidekick-0.16.2-preview.2-linux-x86_64.AppImage.asc`
- `retvest-sidekick-signing-key.asc`

First display the key and compare the fingerprint above with the website:

```sh
gpg --show-keys --with-fingerprint retvest-sidekick-signing-key.asc
```

Only after the fingerprint matches, import the key and verify the download:

```sh
gpg --import retvest-sidekick-signing-key.asc
gpg --verify Sidekick-0.16.2-preview.2-linux-x86_64.AppImage.asc Sidekick-0.16.2-preview.2-linux-x86_64.AppImage
```

Expect `Good signature` from the release key. GPG may also warn that the key is
not certified with a trusted signature: importing a key does not independently
establish its owner's identity. Do not mark it ultimately trusted just to hide
that warning. If the fingerprint differs or signature verification fails,
stop and contact cliffordprince257@gmail.com.

After verification, follow [the installation instructions](INSTALLING.md).

## Signed checksum manifest

`SHA256SUMS.txt.asc` signs the existing `SHA256SUMS.txt` file, which lists the
three installers and the third-party source bundle. With the release key
imported, verify the manifest before comparing your download's SHA-256 digest:

```sh
gpg --verify SHA256SUMS.txt.asc SHA256SUMS.txt
```

On Linux use `sha256sum FILE`; on Mac use `shasum -a 256 FILE`; on Windows use
PowerShell `Get-FileHash FILE -Algorithm SHA256`. Compare the complete digest
with the matching filename in the signed manifest. An authenticated checksum
for Windows or Mac is not a native publisher signature.

## Key changes and reports

Future keys and any revocation will be announced on the Retvest download page
and in this repository. Report unexpected key changes or signature failures
privately to the support email above.
