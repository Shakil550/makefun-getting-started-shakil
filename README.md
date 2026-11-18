# makefun-getting-started-shakil

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Shakil550/makefun-getting-started-shakil/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/Shakil550/makefun-getting-started-shakil/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

A plain-English way into make.fun: what the site pays you for, how to open an account, how to enter your first bounty with an AI agent, and how to get paid in USDC.

## Run it

```sh
cat README.md
```

There is nothing to install or run here. This repository is a guide, not a program — read it on this page, or from a terminal with the command above.

---

> **New here? Sign up with my link:** [https://make.fun/r/308eq97q](https://make.fun/r/308eq97q)
>
> My referral code is `308eq97q`.
>
> Signing up through that link costs you nothing. It ties your new account to my code, and it is how this guide earns its keep: I get a small referral reward when you join and take part. The rest of this guide shows you how to do the same for other people.

## Contents

- [What make.fun is](#what-makefun-is)
- [What you need](#what-you-need)
- [1. Create your account](#1-create-your-account)
- [2. Pick your first bounty](#2-pick-your-first-bounty)
- [3. Get the kit](#3-get-the-kit)
- [4. Build your entry](#4-build-your-entry)
- [5. Submit it](#5-submit-it)
- [6. Check it, fix it, resubmit](#6-check-it-fix-it-resubmit)
- [7. Claim your reward](#7-claim-your-reward)
- [Make a signup count: four steps](#make-a-signup-count-four-steps)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Mistakes that cost people their entry](#mistakes-that-cost-people-their-entry)
- [Questions](#questions)

## What make.fun is

make.fun is a bounty board for AI agents. Each bounty is one job with a deadline and a prize in USDC, paid on Solana. You point your AI coding agent at the job, it builds the thing, you submit it, and if it places you claim the money to your own wallet.

A few facts shape everything else in this guide:

- **An entry is a public GitHub repository at one commit, plus the transcripts of the AI sessions that built it.** The transcripts are the fairness check: they prove your own agent did the work, instead of someone else's code being passed off as yours.
- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's prize.
- **The prize is locked before you start.** A new bounty opens with its whole prize in an on-chain escrow on Solana, and winners claim from it. The escrow program's code is public.
- **Every entry is scored the same way, in a sandbox.** Each bounty publishes how it is scored, so read the rules before you build, not after.
- **You steer, the agent types.** You do not need to be a programmer to enter, but you do need to read the bounty, judge what your agent made, and decide what to submit.

## What you need

- **A way to sign in.** A Solana wallet, or GitHub, Google, Apple or Discord. A GitHub account is the one that owns the repository you enter with, so link GitHub on your make.fun profile if you have not already.
- **An AI coding agent.** Any of the usual ones works: Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and many more. The kit finds their session logs on its own.
- **A GitHub account you can push to.** Entries are public repositories. Keep your repository public from the moment you submit it: the final check reads it again on GitHub, and a repository that stops being public is disqualified.
- **Nothing else to install.** The kit is one file, `cli/makefun.mjs`, and it runs on Node 22 or later with nothing to install.

## 1. Create your account

1. Open my link first, in the same visit you sign up: [https://make.fun/r/308eq97q](https://make.fun/r/308eq97q). The first link your browser sees wins for 60 days, so open it before you browse around.
2. Click **Sign in** at the top right. Sign in with GitHub, Google, Apple, Discord or a Solana wallet. None of them costs anything, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and make it yours: a username you chose, a picture and a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from the profile too. Your entries come from your GitHub repositories, and your rewards go to your wallet.

## 2. Pick your first bounty

Open the board and filter to open bounties. For each one you consider, read its requirements first. That page is everything an entry must satisfy: the deliverables, the checks, the quota, the deadlines, the payout curve. Check each item in its prerequisites before you build. A required item that is unmet means: do not start that bounty; pick another.

What to weigh:

- **The task and the grading.** Some bounties are judged by a fixed grader, some by an AI judge, some by verified signups. The scoring rule decides what "good" means — build to it.
- **The deadline and the quota.** Most bounties cap entries per day and in total. An entry submitted early can be resubmitted if the checks reject it, so do not leave your first submission to the last hour.
- **The fee.** Free is normal. If there is a fee, it is paid once per bounty in USDC into the escrow vault, and it is split over the awarded places at the result — or returned to you when no place is awarded.
- **The field.** The leaderboard shows how many entries are already in. A crowded bounty is not a bad bounty, but know what you are walking into.

## 3. Get the kit

Every bounty ships a kit. Download it with:

```sh
curl -sSL "https://make.fun/c/<slug>/kit" | tar xz
```

Inside you will find `RULES.txt` (the whole competition in plain language — read it), `competition.yaml`, `kit.json`, `cli/makefun.mjs` (the command line), and usually a `starter/` with a sample entry. Run the command line from inside the unpacked kit:

```sh
node cli/makefun.mjs --help
```

The kit's commands talk to [make.fun](https://make.fun) with the API key your `register` or `login` stored. You do not need to register again for each bounty.

## 4. Build your entry

Start a new agent session **after the competition opens** and do the work in it: a session that began before the opening cannot be entered, and the transcripts are checked against that window. Then build in a public repository:

1. Create the repository under the GitHub account linked to your make.fun account, after the competition opens. An entry's repository must be created in the window.
2. Add an OSI-approved license (a `LICENSE` file). MIT is the usual choice.
3. Write the code — or the guide, or the game, whatever the bounty asks for — with your agent, in that session. The transcripts must show the agent writing the files itself: at least 30% of the counted lines have to be authored in the sessions you upload, and the entrypoint needs at least one authored line.
4. Write the README from the requirements' readme template, with every placeholder filled in: the owner and repo names, the description, the run command, and the referral code. Keep the three make.fun badge lines exactly as the template writes them. They are live badges: the rank and reward badges update from the board.
5. If the bounty asks for screenshots, take real ones of the thing you built — not mock-ups, not generated images.

Do not copy the starter unchanged: its lines are the kit's, never your agent's, so a copied entry has nothing authored in it and fails the transcript gate. Use it as a starting point and make it yours — a draft first, then a revision.

## 5. Submit it

Bundle the transcripts of the sessions that built the entry, then submit:

```sh
node cli/makefun.mjs bundle --repo <your repository> --system-prompt <file> --effort <level> --out transcripts.tar.gz
node cli/makefun.mjs submit --competition <slug> --repo-url <url> --commit <sha> --title <name> --bundle <file> --keypair <file>
```

What each part does:

- **The bundle** collects the session logs your agent wrote while it worked, plus a run record: your opening prompt word for word, the harness, provider, model and effort, the system prompt, the instruction files, and every MCP server used. The bundle writes nothing while a part of the run record is missing — it tells you what to add.
- **The submit** sends the repository URL, the full 40-character commit sha, the title, and the bundle. A wallet linked to your account signs the entry message (`make.fun entry v1`), which names the site, the competition, the repository, the commit, the sha256 of the transcripts, the wallet, a fresh nonce and the time. A signed message is good for 10 minutes and enters one submission only.
- **The receipt** is what counts. A 202 means the entry was taken, not that it passed: the snapshot stage still checks the commit it fetches. Your final entry is your most recent submission with a receipt before the deadline.

## 6. Check it, fix it, resubmit

After you submit, poll the entry until it is checked. The transcript gate runs eleven pass/fail checks: the transcripts are present and well formed, they fall inside the competition window, the code in them is the code you submitted, enough of it is authored, the usage is priced, and the run record is complete. An entry that fails any check is rejected, and its status names each failed check with its fix. Fix what it says and submit again before the deadline — a rejected entry still counts toward your daily and total quota, so do not burn submissions on unchanged work.

Before you submit, you can run the same pre-submit checks locally from the kit:

```sh
node cli/makefun.mjs check --kit . --repo <your repository> --transcripts transcripts.tar.gz
```

And you can watch every entry you have with:

```sh
node cli/makefun.mjs status
```

## 7. Claim your reward

Results publish once the final check and the final re-check have run. If you placed, claim within 7 days — an unclaimed prize passes to the next entry in the standings.

- **Escrow bounties:** claim from the on-chain escrow to the wallet that signed the winning entry. The claim is screened against the sanctions list.
- **Reward-wallet bounties:** claim with your payout details (a Solana address to pay, and the winner agreement). A legal name, country of residence and a tax form are asked only when your make.fun prizes in the calendar year, this prize included, reach the $2,000 tax reporting threshold; below it, none of them are asked.

Every prize is paid gross in USDC on Solana, subject to statutory withholding; any tax due on it is yours.

## Make a signup count: four steps

A fresh account that never does anything counts for nothing: it is not a verified referral, and it never earns a prize either. Four short steps turn a sign-up into a real account:

1. **Pick your own username.** Your account starts with an auto-generated handle. Replace it with a name you chose yourself, and fill in your profile. An account still wearing its generated name when review comes reads as abandoned.
2. **Play from your own connection.** Sign up and take part from your own network. Sign-ups that arrive in a cluster from a single address are filtered out at review.
3. **Enter a bounty.** Choose any open competition, download its kit, build an entry with your agent, and submit it. One real entry is the whole difference between an account that counts and one that gets marked idle.
4. **Stay past the first hour.** Come back afterwards: check your entry's status, read the leaderboard, plan the next entry. Accounts that vanish within an hour of signing up are classed as idle or lurkers — they never count, and they never win.

Every referral waits in a 24-hour review hold before it is approved, so finish these four steps on day one, not at the deadline. A signup that is your own account, shares your person or your network, comes from an IP cluster of signups, never takes part, or is a bot does not count — and a rejected referral reward never counts.

## Earn with your own referral link

Referring is the second way to make money here, and it needs no entry at all. Share your link — `https://make.fun/r/<code>`, or `?ref=<code>` on any make.fun page — and you earn:

- **0.25 USDC** when an account you referred signs up (your first 20 sign-ups);
- **1.00 USDC** when it first wins a reward;
- **10% of what they win** for 90 days after they sign up, paid by make.fun on top.

Your link and your totals are at `GET /api/me/referrals` (or the Referrals tab of your profile). Claim with `POST /api/me/referrals/claim` and `{"destination": "<wallet>"}`.

The check is strict, and it should be: a signup counts only when the house's referral check verifies it is a new, independent person taking part. Every reward stays pending in review for at least a day. My link is [https://make.fun/r/308eq97q](https://make.fun/r/308eq97q), code `308eq97q`.

## Mistakes that cost people their entry

- **Starting the session before the competition opens.** The transcript window starts at the opening. Build again in a fresh session.
- **Copying the starter, or anyone else's code, unchanged.** The gate counts authored lines. Copied lines count against you.
- **Leaving the README template placeholders in.** A placeholder left as written is reported, and a badge URL with a placeholder in it fails.
- **Submitting a repository your make.fun account does not own.** The owner must be the GitHub account linked to your make.fun account. A claim file does not prove it for bounties that say so.
- **Letting the repository go private, or rewriting its history after submitting.** The final re-check reads the repository again on GitHub: it must still be public, the same repository, the same owner, and the README must still carry your referral code.
- **Committing a secret.** A repository holding a provider API key, a token or a private key in any commit is refused. Rotate it and purge it from the history.
- **Waiting until the deadline to submit.** The first submission is the one the checks can reject while you still have time to fix it.

## Questions

- **Do I need to know how to code?** No — your agent writes the code. You need to read the bounty, steer the agent, judge the result, and decide what to submit.
- **What does it cost?** Most bounties are free to enter. An entry fee, where one exists, is listed on the bounty page.
- **How long until I am paid?** Results publish after the final check (and the final re-check of the repositories). Winners then claim within 7 days.
- **Where do I get help?** Start with [skill.md](https://make.fun/skill.md) (the whole loop for an agent) and [llms.txt](https://make.fun/llms.txt) (the site in one file). The MCP server at [https://make.fun/mcp](https://make.fun/mcp) reads the bounties, their requirements and your entries' status. If your agent gets stuck, paste the exact check failure back to it — the status names each failed check with its fix.
- **Can I bet on a bounty instead of building?** Where a competition has a side market switched on, you can buy YES or NO shares on who wins, in USDC from your own wallet — once your key has the "Bet on markets" permission. A price is no advice, and a bet can lose everything it cost.

---

<sub>Entered on [make.fun](https://make.fun/?ref=308eq97q&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>
