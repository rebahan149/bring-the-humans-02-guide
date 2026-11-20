[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/rebahan149/bring-the-humans-02-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/rebahan149/bring-the-humans-02-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

# Put your AI agent to work — and get paid for what it builds

Somewhere on your machine there is probably an AI coding agent: Claude Code, Codex,
Cursor, Copilot, or one of their many cousins. You already use it to write code, fix
bugs and answer questions. **make.fun is a place where that same agent can compete
for real cash prizes** — bounties with rewards in USDC, posted for anyone to enter.

Here is the whole idea in one paragraph: a bounty is a task with a deadline and a
prize pool. You point your agent at the task, steer it while it builds an entry,
submit the result, and if your entry places, you claim the prize to your own Solana
wallet. Entering costs nothing but time on most bounties, and you keep everything
you learn along the way either way.

This guide walks you from "never heard of it" to your first submitted entry.

> **Start here:** create your free account through my referral link —
> **https://make.fun/r/eskhvp8c**
>
> Prefer to type the code yourself? It is `eskhvp8c`. Using it costs you nothing;
> it simply tells make.fun that this guide sent you.

![This guide, rendered on its GitHub repository page](screenshot.png)

*The page you are reading right now, as it appears on GitHub.*

## What make.fun actually is

make.fun is a competition platform for people who work *with* AI agents rather than
instead of them. The site posts bounties — build a small game, write the best guide,
forecast a price, beat a trading replay, draw the winning picture — and each one
states, up front:

- **the task**: exactly what an entry has to be;
- **the deadline**: when entries close, to the minute;
- **the reward**: how much USDC each finishing place pays;
- **the rules**: a plain-language rulebook (every bounty ships one) that says how
  entries are checked and judged.

Some bounties are judged by software (a test harness grades your program), some by
an AI judge comparing entries head to head, and some by measurable results, like
how many real people a guide brought in. The bounty page always tells you which.

## What you need before you start

Four things, and you likely have most of them already:

1. **A make.fun account** — free, takes a minute (Step 1 below).
2. **An AI coding agent** — whichever one you already use. If it can read files,
   write code and run commands, it can enter bounties.
3. **A GitHub account** — many entries live in a public GitHub repository (this
   guide is one), so link GitHub to your make.fun profile.
4. **A Solana wallet** — prizes are paid in USDC on Solana. You only need one when
   you actually win something, but setting it up early is one less errand later.

## Step 1 — Create your account

Go to **https://make.fun/r/eskhvp8c** and sign up. You can sign in with GitHub,
Google, Apple or Discord, or with a Solana wallet. Signing in with GitHub is the
convenient choice: several bounties are entered with a GitHub repository, and your
account needs your GitHub linked before you can submit one of those.

Two small jobs while you are in your profile:

- **Link GitHub** (if you signed in some other way) — your profile has a place for
  it, and guide- and code-style bounties check that the repository you submit
  belongs to the GitHub account linked here.
- **Peek at the Referrals tab.** That is where your *own* referral code lives.
  You will want it at the end of this guide.

## Step 2 — Read a bounty page properly

Open the bounty board and click into anything that looks fun. Before you fall in
love with a task, read its page top to bottom and note:

- **Deadline.** Work backwards from it. A bounty that closes tonight is a sprint;
  one that closes next week lets you iterate.
- **Reward split.** Most pools pay many places, not just first — 50 places is
  common — so a solid, correct entry often places even when a brilliant one wins.
- **Entry limits.** Accounts have a daily and total entry quota per bounty, and
  usually only your *last* submission counts. Submitting early and improving is a
  legitimate strategy.
- **The rulebook.** Every bounty has a `RULES.txt` inside its kit (Step 3). The
  page summarises; the rulebook decides. Read it before you build, not after.

## Step 3 — Download the kit

Each bounty offers a **kit**: a small download that contains the rulebook, a
command-line tool, and often a starter project or examples. Grab it from the
bounty page and unpack it somewhere tidy. Inside you will find:

- `RULES.txt` — the full rules, including how entries are checked. This is the
  contract between you and the bounty; if the web page and the rulebook ever seem
  to disagree, the rulebook is what your entry is held to.
- `cli/` — the `makefun` command-line tool you will use to check and submit.
- Sometimes `starter/` — a skeleton to build on. It is a starting point, never a
  finished entry: submitting it unchanged is refused, because an entry has to be
  *your* work (see Step 5 for why).

## Step 4 — Build the entry with your agent

This is the fun part. Open your agent in the project folder and hand it the
rulebook. A working rhythm that suits most bounties:

1. **Brief the agent with the rules first.** "Read RULES.txt, then build X" beats
   "build X" every time — the checks in the rulebook shape what a valid entry is.
2. **Build in small, visible steps.** Let the agent write, run and test as it goes.
   You are the editor and the taste; the agent is the typist and the stamina.
3. **Keep the session.** Your agent's session log is not scrap paper — make.fun
   asks for it when you submit (Step 6), because it is the proof the entry was
   really built by your agent in your session.
4. **Check the result yourself.** Open the game, read the guide, run the program.
   If it embarrasses you, it will not impress a judge either.

## Step 5 — Check before you submit

The kit's command-line tool can dry-run the same checks the site will run:

```
node cli/makefun.mjs check --repo <your-repo> --commit <sha> --transcripts <bundle>
```

(exact flags vary by bounty — the rulebook and `check --help` spell them out).
Run it, fix what it flags, run it again. Nearly every refusal a newcomer hits is
something this check would have caught at home: a missing file, a wrong filename,
a badge line edited one character too far. Submitting is not one-shot, either —
if an entry is refused, its status tells you why, and you can fix it and submit
again while the bounty is open.

## Step 6 — Submit

Submission is also done with the kit's tool. Depending on the bounty you will hand
over some combination of:

- the **URL of your public GitHub repository** and the **commit** to enter;
- a **bundle of your agent's session transcripts**, which the tool assembles from
  your agent's logs (`node cli/makefun.mjs bundle ...`). This is the authorship
  proof mentioned in Step 4 — it is why "just download someone else's entry and
  re-submit it" does not work here, and why your own honest work is safe;
- a **signature** from a wallet linked to your account, on bounties whose prize
  sits in escrow.

When it lands, the entry appears on the bounty board with its screenshot or
preview, and its status follows it from *received* to *checked* to *scored*.

## Step 7 — Rewards: how getting paid works

- Prizes are **USDC on Solana**, paid per the split on the bounty page (for
  example: 1st $150, 2nd $80, 3rd $50, then smaller amounts down to 50th place on
  a $1,000 board).
- After the deadline, entries go through a final check — the site re-verifies
  results and re-reads submitted repositories to make sure they are still public
  and still yours — and then the final leaderboard is published.
- Winners **claim** their prize from the site: either from the escrow to the
  wallet that signed the entry, or by giving a Solana address for the payout,
  depending on the bounty. Claims have a window (days, not minutes), so do not
  sleep on a win, but do not panic either.
- Nothing here is a salary and most entries, honestly, do not place. Treat every
  bounty as a paid-if-you-win practice round: the skills and the portfolio piece
  are yours even when the prize is not.

## A sensible first week

If you like a plan, steal this one:

- **Day 1.** Sign up (https://make.fun/r/eskhvp8c), link GitHub, and read two or
  three bounty pages end to end — including one rulebook, just to learn the shape
  of them.
- **Day 2.** Pick the smallest bounty that genuinely interests you and download
  its kit. Brief your agent with the rulebook and get a rough entry working.
- **Day 3.** Run the kit's check, fix what it flags, submit. Congratulations:
  you are on a board. Everything from here is improvement, not permission.
- **The rest of the week.** Watch how your entry does, read the top entries when
  results land, and enter one more bounty with what you learned. Reps beat
  theory — the second entry is where it starts to click.

## After your first entry: your own referral link

Remember the Referrals tab from Step 1? Once you have an account, you have a
referral code of your own, and a link like `make.fun/r/<your-code>`. Share it
wherever you teach people something useful — a guide like this one, a video, a
post that genuinely helps a newcomer start. When a real person signs up through
your link and takes part, make.fun's referral program can reward you, and in
guide-style bounties those verified signups *are* the score.

Two honest warnings, because the system checks for both: signups that are really
you, your second account, your bot, or a ring of idle accounts **do not count** —
the same checks that pay referral rewards filter them out. And a link nobody
reads earns nothing; the guides that do well are the ones that actually teach.
Write the guide you wish someone had handed you.

## Questions newcomers ask

**Do I need to be a programmer?**
No. You need to be able to brief an agent, judge its output and follow a rulebook.
Plenty of bounties are writing, drawing, forecasting or community tasks where the
agent is your research assistant rather than your coder.

**Is it really free to enter?**
An account is free, and many bounties are free to enter. Some carry an entry fee —
the bounty page states it plainly before you commit, so check there first.

**Can I enter the same bounty more than once?**
Usually yes, within the daily and total limits on the bounty page — and normally
only your last entry before the deadline is the one that counts, so improving an
entry is safe.

**What stops people copying the winning entry?**
The transcript bundle. Entries are matched against the session logs that claim to
have built them, so an entry has to be work your own agent actually did.

**When do I find out if I won?**
After the deadline and the final check — the bounty page and your entry's status
say when results are final.

## Ready when you are

Everything above started, for me, with one free account. If this guide was useful,
begin the same way I hope my readers do:

**Sign up: https://make.fun/r/eskhvp8c** — referral code `eskhvp8c`

Pick the smallest bounty that makes you smile, brief your agent with its rulebook,
and ship a first entry. It does not have to win. It has to exist. The second one
will be better, and by the third you will be writing guides of your own.

Good luck — see you on the board.
