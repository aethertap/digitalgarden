---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/personal-finance/lessons/hledger-intro/"}
---


# Introduction to hledger

`hledger` is a tool that handles the math of accounting. We're going to use it in a very basic form for a while, to keep track of your income so that we can get money into a Roth IRA.

## Getting it set up

1. Create a folder at the path `Documents/records/finance`
2. Create a file in that folder called `2025.journal`: `cd ~/Documents/records/finance; touch 2025.journal`
3. Create a *symlink* to that file in your home directory, with the name `.hledger.journal`: `cd; ln -s ~/Documents/records/finance/2025.journal .hledger.journal`
4. Now, set up your initial accounts. Put this into your journal file:

```ledger
account assets:bank:savings        ; type:A,
account assets:investment:roth        ; type:A,
account assets:cash        ; type:A,
account equity                   ; type:E,
account equity:openingbalances   ; type:E,
account revenues:income       ; type:R,
account expenses:purchases       ; type:X,
```

### Opening balances

Next, we'll set up your initial balances. Look up your bank account balance, and use the following command to get it set up:

`hledger add`

`hledger add` will open up an interactive prompt that will ask you a few questions and then generate the entries you describe. The first transaction we're going to enter is going to hold our *opening balances*, which just means we're saying "here's how much money we're starting with." When `hledger` asks for the first account, use `assets:bank:savings`. The amount should be whatever you have in the account right now.

The next account can be your *cash* if you have any. Use `assets:cash`, and enter the amount of money you have floating around. If you don't have any, skip this part.

After you have all of your assets recorded, the last account is going to be `equity:openingbalances`. This is a placeholder to let you know that all of this money came from somewhere, but you didn't track it. Just accept the default for the amount (it will automatically be the negative of whatever you entered up to now), and tell it to save the transaction. You can press `ctrl-d` to exit the prompt when you're done adding transactions.

### Recording income

When you make some money, record it in `hledger` using the `hledger add` command. In this case, the *positive* money amount will go to wherever you put the money after you got it (either `assets:cash` or `assets:bank:savings` usually). The *balancing* (negative) amount is recorded under `revenues:income`. You can think of income as being the account for *the rest of the world* - after you get some income, the rest of the world has that much less and you have that much more. This way it all balances out, and money isn't created from nothing.

### Recording spending

When you buy something, record it using `hledger add` by *adding an amount to expenses*. That means that the positive amount will go under `expenses:spending`, and the negative amount will be on whatever acount you spent money from (either `assets:cash` or `assets:bank:savings` for now).

### Recording investments

Investing in stocks or other things that aren't money is a bit more complicated. Here, you need to tell `hledger` that the thing you're getting is its own store of value, called a *commodity*. To declare a commodity, you can give it a pattern to look for:

```ledger
commodity $1,000.00
commodity VTI
```

The first one says to format dollar amounts with two decimal places and commas. The second one says that there's something called "VTI" that you might own (that's the stock ticker for the Vanguard Total Market Index, by the way).

Now you can record buying your commodities with `hledger add`. The positive account will be `assets:investments:roth`, and the negative will be `assets:bank:savings` (or cash, if you can buy with cash somehow). To record that you bought 3 shares of VTI for $249.99 each, you'd enter the amount for the `assets:investments:roth` account like this:

`3 VTI @ $244.99`

When the other account value is asked, you can't let it be empty so you have to accept the commodity line. You'll have to go into the journal file and delete the balancing amount so that it infers the cost for you, otherwise you get weird issues with stock shares coming directly from your bank account.

When it's done, the stock buy transation should look like this:

```ledger
2025-02-05 buy 3 VTI
    assets:investments:roth     3 VTI @ $244.88
    assets:bank:savings
```

### Paying Employees

You have somebody doing work for you, and you want to keep track of how much they should be paid at the next pay period. Their work creates a debt that you owe, which you periodically pay off from an asset account.

```hledger
P mow_field $50

2025-04-11 gr10 mowed west field
    expenses:labor:gr10  1 mow_field
    liabilities:owed:gr10  

2025-04-11 Paid gr10
    liabilities:owed:gr10     $50
    assets:cash
```

### Paying by forgiving debt

Scenario:
1. gr10 mows the pasture, earning $50.00, which goes in as a liability that I owe to her
2. She asks me to buy a month of crunchyroll for her for $8.00, by canceling some of her owed wages

Mental model:
She works to mow the grass, and I owe her $50.00. I am buying crunchyroll with my own credit card for $8.00. She offers to pay me back, which means she incurs a debt to me that balances the crunchyroll expense. I then forgive her debt by having her forgive *my* debt.
```hledger
P mowing $50

2025-04-11 gr10 mowed west field
    expenses:labor:gr10  1 mowing
    liabilities:owed:gr10  

2025-04-11 buy crunchyroll month for gr10
    expenses:fun       $8.00
    liabilities:amazonchase

2025-04-11 gr10 reimburses by owing me
    assets:debts:gr10       $8.00
    expenses:fun

2025-04-11 I credit gr10's debt by canceling some of my debt to her
    assets:debts:gr10        -$8.00
    liabilities:owed:gr10
```

The net result of all of that would be equivalent to me just using my credit card to pay part of her wages, which would look like this:

```hledger
2025-04-11 I pay for crunchyroll for gr10
    liabilities:amazonchase        -$8.00
    liabilities:owed:gr10        $8.00
```

By adding a *positive* value to the `liabilties:owed:gr10` account, I'm *reducing* the amount I owe to her.