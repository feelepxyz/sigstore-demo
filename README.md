# sigstore-demo

```bash
gh repo clone feelepxyz/sigstore-demo && cd sigstore-demo

cat provenance.json

npx sigstore attest provenance.json "application/vnd.in-toto+json" > bundle.sigstore
```

```
> Your browser will now be opened to sigstore.dev to login
```

```bash
cat bundle.sigstore | jq

npx sigstore verify bundle.sigstore
```

```
> Verified OK
```

