# Lost in the Heap

Disclaimer: half forgot about this chall, so I only write what I remember when upsolving this chall and based on my convo with the problem setter at the competition time.

Given a memory dump. I analyzed it using volatility2. Using `mftparser` plugin, I got an encrypted file named `flag.enc`. If I ran strings to the dump, it shows some pastebin links about RSA private key and a passphrase `S3C12ETP45SPHRA5E`.

The next step is just decrypt the `flag.enc` using `openssl`.

```
Hology6{Th4Nk5_G0d_w3_DoN't_N3Ed_tO_R3T4ke_tH1s_C0uR5e_4Ga1n}
```

I kinda hate this chall because it was really guessy haha