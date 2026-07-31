# Submission Details

## Campaign

Build a Simple Lock tutorial using OffCKB and CKB devnet.

## What I Completed

- Installed and ran OffCKB locally.
- Cloned the Nervos docs tutorial project.
- Built the JavaScript `hash-lock` smart contract.
- Deployed `hash-lock.bc` to local devnet.
- Ran the tutorial frontend dApp.
- Deposited CKB into the generated hash-lock address.
- Unlocked/transferred CKB from the hash-lock address through the frontend.

## Proof Links

Use these files as the main proof set:

```text
proofs/screenshots/01-offckb-devnet-running.png
proofs/screenshots/02-contract-build-success.png
proofs/screenshots/03-lock-script-deployed.png
proofs/screenshots/04-frontend-running.png
proofs/screenshots/05-deposit-balance.png
proofs/screenshots/06-frontend-unlock-success.png
proofs/screenshots/07-final-balance-after-unlock.png
```

Full proof index:

```text
PROOFS.md
```

## Important Transaction Hashes

Lock script deployment:

```text
0x1fc8a8b0104273ff6d79bd27fadaa3540aed2a32284cd29ea37bb2005bbcfa47
```

Deposit:

```text
0x9f7e06e886aafc5232406e4fafdb5f2eca964d549c7fcf72dbd67d377a44285c
```

Frontend unlock:

```text
0xc71f8faaaa54938137d5c5490d90f12f648e18fd8169cf92be3c2ebb1c655ccf
```

## Script Details

```text
Contract file: hash-lock.bc
Code hash: 0xcd262cb39d9e83f63e5415a56a23982fb6ae79b993e3cf371c12fad71dd23519
Hash type: data2
```

Deployment artifact:

```text
proofs/deployment/scripts.json
```

Built bytecode:

```text
proofs/build/hash-lock.bc
```

## Local Environment

```text
OffCKB: 0.4.10
pnpm: 11.18.0
Network: devnet
Frontend: http://localhost:3000
```

## Submission Reminder

Before final submission:

- Upload this repository or the `proofs/` folder to GitHub/file storage.
- Join the Build on CKB Telegram group if you have not already.
- Review `REFLECTION.md` before final submission.
