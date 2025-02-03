---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/personal-finance/lessons/roth-ira/"}
---


# Investing in a Roth IRA 

- Roth IRAs let you invest money that's *already been taxed*
- They're ideal for starting young, because when you *withdraw* the money, its growth is ***not taxed!***
- You can only invest money that you *earned by working* in some way.
- We have to open the account and manage it, but it is in *your name*, under *your social security number*, so you own it and will not have to do anything special to assume control when you're 18.


## Starting your investments

- We're going to open an account and put some money in it, but you'll have to learn how to track income you've earned in order to get the money in.
- The IRS will be aware of what you do, and you may end up paying taxes on it because you're a dependent (sucks, but there's nothing we can do)
- You're limited to $7000 per year of contributions

## How to track your finances

We're going to use a tool called `hledger` to deal with financial stuff. It's a plain-text format that's dead simple and will never become outdated by software upgrades and fancy tools. It's also something that's really easy to import into those fancy tools, so you won't be consigning yourself to a future of crappy software, and you'll also *own your data*, which is pretty rare in tooling these days.

- ***Start simple***: The temptation to go all-in on money tracking when you're full of excitement and ambition is really strong, but you should *not* try to track everything from the start.
- Track ***just your income*** until you've solidly established the habit. This one's easy because you'll usually have pay stubs or other records provided for you, so when you've become lazy and skipped it a few times, you can go back and fix it.
    - After you track your earned income, you can start keeping tabs on your investments as well. This is conveniently done for you by any good investment broker, so all you have to do is log in and copy a number from time to time.
- After you're committed to income tracking, you can start tracking *fixed expenses* - things like rent, insurance, utilities; They're very stable and follow a predictable timing, so it's much easier to keep up with them. You'll generally also be using your computer to *pay* the bills, so you can also use your computer to *record* them at the same time.
- That's probably all you really need, unless you're doing some strict tracking to figure out a solution to a problem of some kind. If you want more detail than that, it's going to take a lot of discipline and scrupulous receipt tracking.

## Using hledger

`hledger` is a plain-text accounting tool that makes it "pretty easy" to keep track of your finances. But, here's the deal: no tool is magical, and the only thing that actually makes this process hard is that it's hard to remember to do this. So, you're going to have to use every trick you know in order to establish the habit of tracking your money. Be prepared for this to be easy to forget.

`hledger` does something called *double-entry accounting*. The whole idea of double-entry accounting is that it keeps track of how money moves rather than just how much there is. That means that every entry you make will have a place where the money came *from*, and a place where it went *to*. Sounds simple, right? It is not. There are a lot of things you'll do with money that don't have an obvious way to work with double-entry systems, but people have figured out how to make it work, and the result is a nice way to know that your "books balance," meaning that you didn't forget anything.

Double entry accounting is very confusing at the start, because of the archaic terminology it uses. It's all based on an equation called the Accounting Equation, which looks like this: $\text{assets} = \text{liabilities}+\text{owner equity}$. The way to think of these terms is that *assets* are things you have that are worth something *to you*. *liabilities* and *owner equity* are things that are worth something to *someone else*. Since we're going to start small, let's talk about income first.

Income is money that you get for some reason. It comes from *outside* of your sphere of control, and it goes into your assets (usually a bank account). When you want to add income, you still have to have something negative to balance the positive to your assets, so we make an account called *income* that represents the money that all of society has. You add income by taking some of that money, so your positive will be to assets, and the negative that balances it will be from income.
