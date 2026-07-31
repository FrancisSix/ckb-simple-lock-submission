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
├── dapp/                  # Runnable Simple Lock tutorial project
├── proofs/
│   ├── screenshots/       # Numbered proof screenshots
│   ├── transactions/      # Deposit and frontend unlock tx details
│   ├── deployment/        # Deployment script info artifacts
│   └── build/             # Built hash-lock bytecode and JS bundle
├── PROOFS.md              # Proof index with screenshots and tx hashes
├── SUBMISSION.md          # Submission details and checklist
└── REFLECTION.md          # Reflection template to complete in your own words
```

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

The tutorial app uses the default preimage `Hello World` for the hash-lock example. This is fine for devnet learning, but not safe as a production lock pattern.

Before submitting to the campaign, complete `REFLECTION.md` in your own words. The campaign explicitly asks participants to avoid AI-generated reflections.
