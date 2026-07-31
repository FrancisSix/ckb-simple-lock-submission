# CKB Simple Lock Campaign Submission

This repository contains my OffCKB **Build a Simple Lock** campaign submission.

The work completed:

- Ran a local CKB devnet with OffCKB.
- Built the tutorial `hash-lock` custom lock script.
- Deployed the custom lock script to devnet.
- Ran the dApp frontend locally.
- Deposited devnet CKB into the hash-lock address.
- Used the frontend dApp to unlock and transfer CKB out of the hash-lock script.

## Repository Structure

```text
.
|-- dapp/                  # Runnable Simple Lock tutorial project
|-- proofs/
|   |-- screenshots/       # Numbered proof screenshots
|   |-- transactions/      # Deposit and frontend unlock tx details
|   |-- deployment/        # Deployment script info artifacts
|   `-- build/             # Built hash-lock bytecode and JS bundle
|-- PROOFS.md              # Proof index with screenshots and tx hashes
|-- SUBMISSION.md          # Submission details and checklist
`-- REFLECTION.md          # Reflection
```

## Direct Links

Main pages:

- [Proofs](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/PROOFS.md)
- [Submission details](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/SUBMISSION.md)
- [Reflection](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/REFLECTION.md)

Proof screenshots:

- [01 - OffCKB devnet running](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/01-offckb-devnet-running.png)
- [02 - Contract build success](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/02-contract-build-success.png)
- [03 - Lock script deployed](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/03-lock-script-deployed.png)
- [04 - Frontend running](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/04-frontend-running.png)
- [05 - Deposit balance](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/05-deposit-balance.png)
- [06 - Frontend unlock success](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/06-frontend-unlock-success.png)
- [07 - Final balance after unlock](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/screenshots/07-final-balance-after-unlock.png)

Transaction proofs and artifacts:

- [Deposit proof](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/transactions/deposit-proof.txt)
- [Frontend unlock proof](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/transactions/frontend-unlock-proof.txt)
- [Deployment scripts.json](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/deployment/scripts.json)
- [System scripts.json](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/deployment/system-scripts.json)
- [Built hash-lock bytecode](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/build/hash-lock.bc)
- [Built hash-lock JS bundle](https://github.com/FrancisSix/ckb-simple-lock-submission/blob/main/proofs/build/hash-lock.js)

## Key Results

Custom lock script deployment:

```text
0x1fc8a8b0104273ff6d79bd27fadaa3540aed2a32284cd29ea37bb2005bbcfa47
```

Hash-lock address:

```text
ckt1qzkymvxscq5t5rtnmmy7uhn28sxf3lxle2y4gq4r9pwksr5kfh95vqgqqrxjvt9nnk0g8a372s26263rnqhmdtnehxf78nehrsf044ca6g63jpqsdyg7f7p70y8pavhnn00ly0qaksldttujr8mk8et38zd0yyjeegwmczc8
```

Deposit transaction:

```text
0x9f7e06e886aafc5232406e4fafdb5f2eca964d549c7fcf72dbd67d377a44285c
```

Frontend unlock transaction:

```text
0xc71f8faaaa54938137d5c5490d90f12f648e18fd8169cf92be3c2ebb1c655ccf
```

## Reproduce Locally

Install prerequisites:

```powershell
npm install -g @offckb/cli pnpm
```

Start OffCKB devnet in one terminal:

```powershell
offckb node
```

Build and deploy the lock script in another terminal:

```powershell
cd dapp
pnpm install
pnpm build
offckb deploy --network devnet --target dist --output deployment -y
```

Run the frontend:

```powershell
Copy-Item .\deployment\scripts.json .\frontend\deployment\scripts.json -Force
Copy-Item .\deployment\system-scripts.json .\frontend\deployment\system-scripts.json -Force
cd .\frontend
Copy-Item .\.env.example .\.env -Force
pnpm install
pnpm run dev
```

Open:

```text
http://localhost:3000
```

## Notes

The tutorial app uses the default preimage `Hello World` for the hash-lock example.
