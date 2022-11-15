# Hard Auditability

## Privacy Pools

### Description

1) Deposit: Generate secret sk. Computer leaf node l=H1(s) and nullifier n=H2(s). Submit 1 dollar and l to the privacy pool (as Merkle tree)
2) Spend: To send 1 dollar to Bob (at leaf l'): submit n; submit l'; prove knowledge (zk-SNARK) of s such that n=H1(s) and that l=H2(s) where l is in the Merkle tree.
3) Update State: If proofs validate and n is unseen, add n to the spent list and l' to the Merkle tree
4) Denylist: consists of sanctioned l values. Prove non-membership in denylist when spending.

### Challenges

1. Maintaining Denylist Post-Hoc: How do you add to the denylist once the system is in place? Find evidence of a leaf node attached to a sanctioned organization, you can block the leaf from being spent. However you would probably relate the node to the organization by knowledge of s, in which case you could just quarentine the money instead
2. You cannot stop transactions *to* a sanction organization as the design forces them to use an ephemeral secret for every receipt.

## One Hop Anonymity

### Description

1) Enrolment: establish a list of known participants; establish a list of authorized distributors for anonymous cash; establish a list of authorized recipients of anonymous cash (simplest: same as known participants)

2) Black coins: free sent amongst known participants

3) Red coins: can be received by anyone (including unknown participants) but only from authorized distributors (who convert black coins into red coins). Red coins can only be sent to authorized recipients.

   
