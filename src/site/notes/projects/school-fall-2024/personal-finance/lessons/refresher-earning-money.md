---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/personal-finance/lessons/refresher-earning-money/"}
---


# Earning Money

WOOT! You guys are earning money now! Let's keep track of it.

Remember `hledger`? That's the tool we're going to use. Use `hledger add` to add a new transaction. You should use the following accounts:

- The *amount* will be $50.00
- The account *getting* the money (use a positive number) should be `assets:cash`
- The account *losing* the money should be `revenues:income:mowing`, and it should automatically balance the value you put into cash.

## Spending that sweet cash

You have both spent some money on things recently. Let's record those transactions too:

`hledger add` a transaction that puts a *negative* amount in your `assets:cash` account, and the balancing positive amount in `expenses:spending`. If you want to be more detailed with the spending, you can add another category below that, like `expenses:spending:steam` or `expenses:spending:gifts`

- [ ] #hw Use `hledger` to add transactions for things you've done to earn and spend money over the last few months. [[2025-04-14\|2025-04-14]]
