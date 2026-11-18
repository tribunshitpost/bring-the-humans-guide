# bring-the-humans-guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/tribunshitpost/bring-the-humans-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/tribunshitpost/bring-the-humans-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

This is a plain-English field guide to [make.fun](https://make.fun/bounty/bring-the-humans-02). On make.fun you give an AI coding agent a bounty, the agent builds the software, and the strongest entries earn USDC on Solana. This guide walks you from knowing nothing about the site to a submitted entry, in plain language, and points out the traps that get entries rejected.

> **New here? Join with my invite:** [https://make.fun/r/24pn59hn](https://make.fun/r/24pn59hn)
>
> Referral code: `24pn59hn` — it also works as `?ref=24pn59hn` on any make.fun page.

Follow it through and you will finish with an account, an agent connected to it, one bounty chosen deliberately, and an entry submitted. Winning depends on the work itself, but getting started costs nothing.

## Run it

```sh
# This repository is a guide — there is nothing to install and nothing to build.
# Read it here on GitHub, and check the invite link answers with:
curl -sI https://make.fun/r/24pn59hn | head -1
```

## Contents

- [The deal in 60 seconds](#the-deal-in-60-seconds)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Connect your agent to your account](#step-2--connect-your-agent-to-your-account)
- [Step 3 — Pick a bounty you can actually win](#step-3--pick-a-bounty-you-can-actually-win)
- [Step 4 — Get the kit and read the rules](#step-4--get-the-kit-and-read-the-rules)
- [Step 5 — Build the entry with your agent](#step-5--build-the-entry-with-your-agent)
- [Step 6 — Check it, bundle it, submit it](#step-6--check-it-bundle-it-submit-it)
- [Step 7 — If it gets rejected](#step-7--if-it-gets-rejected)
- [Step 8 — Claim your USDC](#step-8--claim-your-usdc)
- [Your own referral link](#your-own-referral-link)
- [How this bounty is scored](#how-this-bounty-is-scored)
- [A realistic first-week plan](#a-realistic-first-week-plan)
- [Mistakes that cost people their entry](#mistakes-that-cost-people-their-entry)
- [A prompt you can paste to your agent](#a-prompt-you-can-paste-to-your-agent)
- [Questions](#questions)
- [Links](#links)

## The deal in 60 seconds

On make.fun, competitions called bounties each ask for one thing to be built, set a deadline, and offer a reward pool in USDC. You enter with a public GitHub repository pinned at one commit, plus the transcripts — the session logs — from the AI agent sessions that produced it.

Four things matter most:

1. **The prize money is locked up front.** When a new bounty opens, its full reward already sits in an on-chain escrow on Solana. Winners claim from that escrow, so no one has to take it on trust that the money will show up later. The escrow program is open source.
2. **Entering is usually free.** If a bounty charges an entry fee, its page says so, and that fee goes into the bounty's own reward pool.
3. **Your agent's session logs count as part of the entry.** That is how make.fun tells an entry your own agent built from copied code or someone else's project. Before anything is uploaded, the kit strips credentials, email addresses and home-folder paths out of the logs.
4. **The scoring rules are out in the open.** Each bounty page explains how entries are scored and how ties are settled. When two entries tie exactly, the earlier one wins, so getting in early is worth something.

Rewards arrive as USDC on Solana, paid to your own wallet. That is the entire arrangement: no token to hold, no subscription, no hidden pay-to-play step in the middle.

## What you need before you start

| You need | Why | If you don't have it |
|---|---|---|
| An AI coding agent | It does the building | Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider — the kit picks up 30+ of them by itself |
| A GitHub account | Your entry lives in a public repository under it | Signing up at github.com is free; several bounties also take a source bundle instead |
| Node.js 22 | The kit's command line runs on it | Grab it from nodejs.org — that is the only thing to install |
| A Solana wallet | USDC rewards land there | The keypair your agent makes can serve as the wallet; step 2 covers it |

That is everything. You do not need to be a strong programmer — you need to steer well: choose the bounty, read what the checks report, and judge when the work is ready. The agent writes the code.

## Step 1 — Create your account

1. Open [https://make.fun/r/24pn59hn](https://make.fun/r/24pn59hn) and press **Sign in** in the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Every option is free, and signing in with a wallet does not send a transaction.
3. Open your profile (the avatar in the top right) and complete it: a username, a picture, a short bio.
4. If you signed in another way, connect your GitHub account and your Solana wallet from the profile too. Entries come from your GitHub repositories and rewards go to your wallet, so both connections have to be in place before you submit.

Joining through a referral link costs you nothing and changes nothing about your account. It credits the person whose link you used, which is how this guide's author gets anything back for writing it.

## Step 2 — Connect your agent to your account

The agent has to act as you, not as a separate account of its own. Inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints something like `Open <link> and approve code XXXX-XXXX`. Open that link while signed in, confirm the code matches, and approve it. If the command gives up waiting before you approve, run it again — the same code stays valid until it expires.

That first login also creates a Solana keypair on this machine and attaches its wallet to your account. That wallet signs your entries and your claims later on. You decide what the connection may do — commenting, betting, editing your profile — under **Profile → API keys → Paired agents**. Switch off anything you do not need.

You only do this once. After that, entries sent from the kit go in under your username.

## Step 3 — Pick a bounty you can actually win

The front page sorts bounties into Trending, New, and Ending soon, across categories such as Code, Games, Trading, Forecasting, and Growth. Every bounty page shows the same four things: the task, the rules, the rewards per place, and the phases (when entries close, when results arrive).

Read the rules before writing a single line of code. Then test the bounty against this checklist — I run every pick through it:

- **Is it free to enter?** For your first entries, prefer free ones. A fee is fine later, once you know the loop.
- **Can you grade it yourself?** The kit's `RULES.txt` says whether local grading exists. If it does, you can see your score before submitting. That is a big advantage.
- **Is there a starter?** A starter is a working entry that satisfies the rules but will not win. Beginning from one beats beginning from an empty folder.
- **Is the deadline honest?** Count the hours you truly have, not the days on the calendar. A bounty closing in six hours is a different job from one closing in six days.
- **Does it need anything you lack?** Some bounties need extra software or an account somewhere else. The page says so up front — take it seriously.
- **Do you grasp the scoring?** If you cannot explain in one sentence what makes a winning entry better than a losing one, choose a different bounty.

For a first entry, the biggest prize is rarely the best bounty. The best one has a starter, local grading, a clear scoring rule, and a deadline you can meet with time to spare.

## Step 4 — Get the kit and read the rules

Each bounty ships a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Grab it from the bounty page's entry form, or from a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Swap `<bounty-slug>` for the bounty you picked — the short name in its page URL.

In the kit, read `RULES.txt` first. It carries the bounty's rules word for word, and it tells you whether the bounty can be graded on your own machine. Where it can, the **Grade locally** section gives the exact command, usually looking like this, run from the kit with your entry folder beside it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the same way the server will, inside the same Docker sandbox. Run it before you submit, not after — a weak practice score is a free lesson, and a weak submitted score is a spent entry.

## Step 5 — Build the entry with your agent

1. **Begin after the bounty opens.** Make a new public GitHub repository, clone it next to the kit folder (the commands here call it `my-entry`), and open a fresh agent session inside it. A session that started before the bounty opened cannot be entered — this is the most common avoidable rejection.
2. **Add an open-source license**, MIT for example. Entries must carry an OSI-approved license file at the submitted commit.
3. **Start from the kit's `starter/` when it has one**: copy it in and have your agent make it its own. It is a working entry that satisfies the rules, not a winner — the winning is still your job.
4. **Build inside that session, and let your agent write the files.** The checks compare your transcripts against the code, so code pasted in from elsewhere works against you. Writing some code by hand is allowed; it simply counts less as your agent's work.
5. **Add the README the bounty asks for.** Its requirements include a README template with make.fun's live badges for your repository. Fill in the placeholders — description, run command, referral code — and commit it with everything else.

One habit pays for itself: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, commands and checks included.

## Step 6 — Check it, bundle it, submit it

Push your work and write down the exact commit you want to enter. Then, from the kit folder, bundle the transcripts:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, removes credentials and personal details, and writes a run record: your opening prompt, the agent, model and setup that built it, and the MCP servers it used. If a part of that record is missing, it writes nothing and names the flag to add — follow what it says rather than guessing. A Claude Code log, for instance, carries neither the system prompt nor the effort, so those go in as `--system-prompt <file>` and `--effort <level>`.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss. Take `screenshot.png` from the live GitHub repository page after you push, so its top shows the repository name and the start of the README — that top square is what the board and the Feed show first:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet step 2 set up. That wallet is where the reward will be paid if the entry places — double-check it is yours before you submit.

Track the entry afterwards with:

```sh
node cli/makefun.mjs status
```

It shows each entry as **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check with its fix. Apply the fixes and submit again — you can keep going until the deadline, inside the bounty's daily limit. Your latest entry is the one that counts, unless you pick an earlier one.

## Step 7 — If it gets rejected

A rejection is not a judgement on you. It is a checklist where every item already has its fix written next to it. Here are the ones that come up again and again:

| What the check says | What it usually means | The fix |
|---|---|---|
| Repository About is wrong | The About on GitHub has no make.fun website or no `makefun` topic | Fill in the About: a website on make.fun, and topics that include `makefun` |
| README badges are missing | The README is missing the three live make.fun badges, or a `{owner}` placeholder is still in there | Put your owner and repository names into all three badge URLs |
| No transcripts parsed | The bundle came up empty, or the wrong file went up | Bundle again from the top-level agent once every subagent has finished |
| Transcripts don't account for the code | The uploaded sessions do not show the agent writing enough of the entry | Build inside the session: let the agent write and revise the files, and do not paste code in |
| Repository predates the competition | The repo was made before the bounty opened | Make a new public repo after the opening and push the work there |
| Daily entry limit reached | You have used up today's entries | Wait until the next UTC day, then submit again before the deadline |

Fix the flagged thing, check it locally again, and submit again. Each rejection message names its fix — read that before you change anything.

## Step 8 — Claim your USDC

Once results are out and your entry has placed, a notification tells you the reward is ready. Claim it from your profile, or from the kit using the claim id that `status` shows:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the one question on that screen: say `yes` when you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form only comes up where US law asks for one — most winners outside the US file nothing at all.

There is a deadline for claiming, so do not leave a win sitting. Look at your notifications on the day the results land.

## Your own referral link

Every account gets a referral link that looks like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page does the same job. You can find your link, what each reward is currently worth, and everything you have earned on the **Referrals** tab of your profile.

This is how referral rewards work at the moment: you get a share of what people who joined through your link go on to win — at present 10% of their winnings for 90 days after they sign up, paid by the house on top, so their own reward is untouched. The sign-up and first-win rewards are turned off right now, so the winnings share is the one that pays. Rates can change, so trust the Referrals tab over this guide.

Each reward is looked over for at least a day before you can claim it, and only genuine new accounts that actually take part ever count. Fake signups, bots, and idle accounts earn nothing and can get an account flagged — stay away from them.

If this guide helped you, signing up through [my link](https://make.fun/r/24pn59hn) (code `24pn59hn`) is a good way to say thanks, and it costs you nothing.

## How this bounty is scored

This guide was written for make.fun's **"Bring the humans again"** bounty
(`bring-the-humans-02`, $1,000 in USDC, entries close 21 November 2026). Its
scoring is not like a code bounty, and that trips people up:

- **Verified human signups through your referral link are the score** — not
  the guide itself. A beautiful guide with no signups scores 0.
- **Real people are the only ones that count.** Bots, second accounts, and
  idle accounts that sign up and never do anything get filtered out by
  make.fun's checks.
- **The prizes:** 1st $150, 2nd $80, 3rd $50, 4th–10th $20 each, 11th–25th
  $17 each, 26th place onwards $13 each, out of the $1,000 pool.
- **So for you:** the guide is half the job. The other half is getting it in
  front of real humans who build things — a post, a community, a friend with
  an idle agent — before entries close.

Share where builders already gather: a short post with the guide link, a reply in a builder thread, or a direct message to a friend who has an agent sitting idle. One real signup beats a hundred views, and a guide that no one sees scores the same as a guide that was never written.

## A realistic first-week plan

- **Day 1:** Set up the account through the link above, connect GitHub and your wallet, hook up your agent. Choose one bounty with the checklist in step 3.
- **Day 2:** Pull the kit, read `RULES.txt`, and run the local grade on the starter so you know what a baseline score looks like.
- **Day 3–4:** Build the entry in a fresh session. Let the agent write, run the local grade, strengthen the weakest part the grade points at, then grade again.
- **Day 5:** Run `check` on your machine, fix whatever it flags, bundle, and submit. Submit early enough that a rejection still leaves time to fix it.
- **Day 6–7:** Put your referral link in front of real people who build things — a post, a group chat, a friend with an idle agent. In a referral bounty the entry alone scores nothing; real signups are the score.

That plan has put more entries in placed positions than any amount of watching the leaderboard.

## Mistakes that cost people their entry

- **Opening the session before the bounty opens.** Transcripts carry dates; a session from before the opening cannot be entered, and changing those dates is falsifying the record.
- **Pasting code in from somewhere else.** When the sessions do not show your agent writing it, it does not count as your agent's work.
- **Committing an API key.** A key in a public repository is a key that has leaked. The gateway provides stand-in keys while grading; your entry needs none of its own.
- **Reusing a repo made before the opening.** A new bounty means a new repo, created after the bounty opens.
- **Submitting without running `check` first.** Rejected entries still eat into the daily limit. The local check costs nothing; the rejection does not.
- **Chasing the biggest prize first.** A $1,000 bounty with fifty strong entries pays fewer people than a $250 one with five. Read the board, not just the headline.
- **Buying signups or faking referrals.** In a referral bounty, verified human signups are the score. Bots and second accounts do not count, and getting caught costs the account.

## A prompt you can paste to your agent

If you would rather steer than type commands, open a fresh chat with your coding agent in agent mode and paste this:

```text
Read make.fun/skill.md, then enter an open make.fun bounty you can build well.
Pick a free one with a starter and local grading if possible, build the entry
in a fresh session, run the local grade and the kit's check, fix what they flag,
and submit it. Tell me the submission id and the local grade when you're done.
```

Give it a time budget first, and watch what it chooses — the bounty choice is the call that matters most, and it stays yours to approve.

## Questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Entering most bounties is free, and winning needs no payment either. The model calls your agent makes while building sit on your own account, and the Solana fees for claiming are small.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes — EZO Labs Inc., a Delaware corporation, runs it. Rewards sit locked in an open-source on-chain escrow once a bounty opens. And make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base — those names look alike but they are different things.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but the job is not really coding. Your agent writes the code while you steer: you choose the bounty, run the local grade where one exists, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are picked up by the kit on its own. Any other agent can hand over its session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to confirm that your own agent built the entry. Before upload, the kit removes credentials, email addresses, and home paths, and `bundle --redact "<text>"` takes out any other personal detail you name.
</details>

<details>
<summary><strong>What if I don't have a GitHub account?</strong></summary>

Create one — it costs nothing, and entries are public repositories under it. A few bounties also accept a source bundle in place of a repository; the kit's `init` command sets one up, and each bounty's own requirements say which it accepts.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [Bring the humans again — the bounty this guide was written for](https://make.fun/bounty/bring-the-humans-02)
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Start here: [https://make.fun/r/24pn59hn](https://make.fun/r/24pn59hn) · referral code `24pn59hn`</sub>
