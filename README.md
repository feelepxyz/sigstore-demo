# sigstore-demo

```
[demo] ➔ cat provenance.json
{
  "_type": "https://in-toto.io/Statement/v0.1",
  "subject": [
    {
      "name": "pkg:npm/sigstore@1.3.0",
      "digest": {
        "sha512": "76176ffa33808b54602c7c35de5c6e9a4deb96066dba6533f50ac234f4f1f4c6b3527515dc17c06fbe2860030f410eee69ea20079bd3a2c6f3dcf3b329b10751"
      }
    }
  ],
  "predicateType": "https://slsa.dev/provenance/v0.2",
  "predicate": {
    "buildType": "https://github.com/npm/cli/gha/v2",
    "builder": {
      "id": "https://github.com/actions/runner"
    },
    "invocation": {
      "configSource": {
        "uri": "git+https://github.com/sigstore/sigstore-js@refs/heads/main",
        "digest": {
          "sha1": "dae8bd8eb433a4147b4655c00fe73e0f22bc0fb1"
        },
        "entryPoint": ".github/workflows/release.yml"
      },
      "parameters": {},
      "environment": {
        "GITHUB_EVENT_NAME": "push",
        "GITHUB_REF": "refs/heads/main",
        "GITHUB_REPOSITORY": "sigstore/sigstore-js",
        "GITHUB_REPOSITORY_ID": "495574555",
        "GITHUB_REPOSITORY_OWNER_ID": "71096353",
        "GITHUB_RUN_ATTEMPT": "1",
        "GITHUB_RUN_ID": "4735384265",
        "GITHUB_SHA": "dae8bd8eb433a4147b4655c00fe73e0f22bc0fb1",
        "GITHUB_WORKFLOW_REF": "sigstore/sigstore-js/.github/workflows/release.yml@refs/heads/main",
        "GITHUB_WORKFLOW_SHA": "dae8bd8eb433a4147b4655c00fe73e0f22bc0fb1"
      }
    },
    "metadata": {
      "buildInvocationId": "4735384265-1",
      "completeness": {
        "parameters": false,
        "environment": false,
        "materials": false
      },
      "reproducible": false
    },
    "materials": [
      {
        "uri": "git+https://github.com/sigstore/sigstore-js@refs/heads/main",
        "digest": {
          "sha1": "dae8bd8eb433a4147b4655c00fe73e0f22bc0fb1"
        }
      }
    ]
  }
}%                                                                                                                                    

[demo] ➔ npx sigstore attest provenance.json "application/vnd.in-toto+json" > bundle.sigstore
Your browser will now be opened to: https://oauth2.sigstore.dev/auth/auth?response_type=code&client_id=sigstore&client_secret=&scope=openid+email&redirect_uri=http%3A%2F%2Flocalhost%3A55577&code_challenge=-4d-l0_RzFbEX9hEmypUNPVhfNPeoTs2ZWV9TAXZl80&code_challenge_method=S256&state=4VU0Xylnwg0T1s6ssmjFUA&nonce=XcmVjyg_8fyTxS9_MzuaPQ

[demo] ➔ npx sigstore verify bundle.sigstore
Verified OK
```
