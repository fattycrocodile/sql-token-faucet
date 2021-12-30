# spl-token-faucet

Solana program that makes Token Faucets possible

Live demo [here](https://www.spl-token-ui.com/)

### Token Faucets

Token faucets allow developers to easily give others access to tokens of a specific mint without sending around their private key. This is accomplished through a token faucet program.

When creating a token faucet, the chosen token's mint authority is transferred to a Program Derived Address. The program then accepts minting requests. Having received such a request, the program checks that the requested amount is lower than the configured max amount or that the requester is the faucet admin (in which case they may mint as much as they like). These parameters can be set during faucet creation. Finally, a faucet may be closed again but only if it has an admin configured which must sign the closure tx. Faucet closure will transfer the token's mint authority back to the admin.
