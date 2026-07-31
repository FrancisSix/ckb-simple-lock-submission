# Reflection

Important: write this section in your own words before submitting. The campaign asks participants to avoid AI-generated reflections, so do not submit this file unchanged.

## My Reflection

Replace this section with your own short reflection.

Suggested structure:

1. What you learned about CKB, cells, lock scripts, or witnesses.
2. One setup/debugging problem you ran into and how you solved it.
3. What surprised you or felt interesting about the transaction flow.
4. Why the `hash_lock` example is weak.
5. How the weakness could be addressed.

## Notes From This Run

Use these only as memory joggers. Rewrite them in your own voice.

- I used OffCKB devnet to run a local CKB chain.
- I built the `hash-lock.bc` contract and deployed it to devnet.
- The dApp generated a hash-lock address from the `Hello World` preimage.
- I deposited CKB into the hash-lock address.
- I unlocked CKB through the frontend transfer flow by providing the matching preimage.
- I had to fix local Windows setup issues around npm global PATH and command execution.
- I had to approve pnpm dependency build scripts before the project would build.

## Weaknesses Of `hash_lock`

Rewrite this in your own words for the final campaign submission:

- The preimage is revealed in the transaction witness when the lock is unlocked.
- Once the preimage is public, anyone can reuse it to unlock other cells that use the same hash.
- Partial withdrawals are risky because remaining funds locked with the same hash can become vulnerable.
- A simple hash lock does not identify the intended owner or require a signature.

## Possible Improvements

Rewrite this in your own words:

- Avoid reusing the same secret/hash for multiple cells.
- Consume all funds protected by a revealed preimage.
- Combine the condition with signature-based authorization.
- Use a production-ready lock such as Omnilock for real assets.
- Implement more robust validation in Rust or another production-focused CKB script stack.
