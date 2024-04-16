# Key Transition Statement

Date: 2024/04/16

New primart key generated due to loss of YubiKey.

Normally, only the secondary key should be revoked, but we decided to execute the primary key as a safety measure.

The old key was:

```
pub   ed25519/002AEC385BEAEBCF 2023-03-13
Key fingerprint = CDD5837D99D6BC1D6F5F5CB2002AEC385BEAEBCF
```

And the new key is:

```
pub   ed25519/198F1B4D8D77678F 2024-04-16 [expires: never]
Key fingerprint = ABB3904C7263155D9F5C34A3198F1B4D8D77678F
```

To fetch the full key from a public key server, you can simply do:

```
gpg --keyserver keys.openpgp.org --recv-key 'ABB3904C7263155D9F5C34A3198F1B4D8D77678F'
```

If you already know my old key, you can now verify that the new key is
signed by the old one:

```
gpg --check-sigs 'ABB3904C7263155D9F5C34A3198F1B4D8D77678F'
```

If you don't already know my old key, or you just want to be double
extra paranoid, you can check the fingerprint against the one above:

```
gpg --fingerprint 'ABB3904C7263155D9F5C34A3198F1B4D8D77678F'
```

If you are satisfied that you've got the right key, and the UIDs match
what you expect, I'd appreciate it if you would sign my key. You can
do that by issuing the following command:

**
NOTE: if you have previously signed my key but did a local-only
signature (lsign), you will not want to issue the following, instead
you will want to use --lsign-key, and not send the signatures to the
keyserver
**

```
gpg --sign-key 'ABB3904C7263155D9F5C34A3198F1B4D8D77678F'
```

I'd like to receive your signatures on my key. You can either send me
an e-mail with the new signatures (if you have a functional MTA on
your system):

```
gpg --export 'ABB3904C7263155D9F5C34A3198F1B4D8D77678F' | gpg --encrypt -r 'ABB3904C7263155D9F5C34A3198F1B4D8D77678F' --armor | mail -s 'OpenPGP Signatures' <me@m1sk9.dev>
```

Please let me know if you have any questions, or problems, and sorry
for the inconvenience.

Sho Sakuma
