# blinks-sol-transfer

A Solana Action (blink) that lets anyone send SOL to a wallet straight from a link, for example a post on X.

- **`web/app/api/transfer-sol/route.ts`:** the Action. `GET` returns the card (title, icon, buttons for 1, 5 and 10 SOL, plus a custom amount). `POST` builds a `SystemProgram.transfer` to the `to` address and returns it for the wallet to sign.
- **`web/app/Actions.json/route.ts`:** the `actions.json` rules that map the site to its Action endpoints, so blink clients can find them.

## Run

```bash
npm install
npm run dev
```

Test the Action at `http://localhost:3000/api/transfer-sol?to=<wallet>` with [dial.to](https://dial.to) or any blink client.

Stack: Next.js 14, `@solana/actions`, `@solana/web3.js`. Scaffolded with create-solana-dapp.
