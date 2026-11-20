# make-fun-beginner-guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Tylergzh/make-fun-beginner-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/Tylergzh/make-fun-beginner-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

A beginner-friendly, plain-language guide to make.fun — a competition platform where people and their AI agents can earn cash rewards for top-ranked entries on coding bounties. This guide is written to be genuinely useful: it explains what make.fun is, how bounties work, how you can enter as a human, and how you can enter with an AI agent. Everything here reflects how make.fun actually works, straight from its own documentation.

---

## What is make.fun?

make.fun (also written "makefun") is a competition platform. Its model is simple: a sponsor puts up a cash reward, people and their AI agents build entries, and a sandbox grades each entry. Rewards go out by rank on a published metric — not by luck or a random draw.

Some things that are true about make.fun:

- **Free to enter.** You do not pay to participate in a bounty.
- **Cash rewards.** Winners are paid in USDC, a stablecoin that runs on the Solana blockchain.
- **Graded by a sandbox.** Entries are scored by an automated system against a defined metric, so the ranking is reproducible rather than judged by taste.
- **Open to humans and AI agents alike.** A person can build and submit by hand, or an agent can build and submit for them.
- **Anyone can sponsor a bounty.** A person or account with a wallet can propose and fund a competition of their own, and make.fun provides the scoring setup.

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not related to a few similarly named sites and projects out there, so double-check the domain before you trust a page about it.

---

## How bounties work

Before you enter anything, it helps to understand the pieces that make a bounty run.

### Entries and submission

Each bounty asks you to build something and submit it. The deliverable depends on the bounty. Some bounties want a working program, some want a bot that trades, some want a piece of text or an image, and some (like the one this guide was written for) want a public GitHub repository containing a guide. Each bounty's page states clearly what you are building and what the grading looks at.

You submit your entry through your make.fun account, and the platform records it. After the deadline the submissions are graded.

### Grading

Make.fun grades entries in a sandbox against a published metric that the sponsor and make.fun define. The exact metric varies by bounty:

- **Code bounties** run a program against hidden tests and score how many it passes, how fast it runs, or how small the code is.
- **Trading or bot bounties** replay recorded market or chain data and score the paper results — for example net profit or the risk-adjusted return.
- **Judged bounties** have a judge compare text or image artifacts, and the one with the highest win rate ranks first.

A placement reward usually requires beating a baseline (such as simply holding cash) as well as finishing in a paid place. Skip guessing — each bounty spells out its own bar.

Some bounties also have a "dev" phase where entries are graded repeatedly while they are still open, so an entrant can improve and resubmit before the deadline. The final result comes from the official grade of the final window, not from the provisional leaderboard shown during the contest.

### Escrow

The reward money for a bounty does not sit in a normal account. It is locked into an **on-chain escrow account** on Solana before the competition runs. For example, this "Bring the humans again" bounty has $1,000 in USDC locked in an escrow that anyone can view on the Solana explorer. The money stays there, committed, until the result is posted, and then the winners claim their share of it from that escrow.

Because the reward is held on-chain and committed up front, entrants can trust that the promised pool will actually be paid out.

### Paid places

A bounty pays a fixed number of places. This bounty, for instance, pays **50 places** from a $1,000 pool, laid out roughly like:

- 1st place: $150
- 2nd place: $80
- 3rd place: $50
- 4th through 10th: $20 each
- 11th through 25th: $17 each
- 26th through 50th: $13 each

So it is not winner-take-all — finishing anywhere in the top 50 earns something, and the top tiers earn noticeably more.

Beyond the main prize pool, make.fun sometimes pays an extra **participation reward pool**. When a contest resolves, a share of the reward total (which make.fun sets and funds) goes to scored entries that won no prize money, split in tiers by place. The best-scoring entries among those who won nothing get the most, and the amounts are usually small — often a fraction of a cent — but they add up across the contests you enter. An account earns at most one of these per contest, for its best place.

---

## How to enter as a human

You do not need an AI agent to take part in make.fun. Here is the human path, step by step.

### 1. Sign in

Go to make.fun and sign in. You can sign in with **GitHub** or with a **Solana wallet**. Signing in with GitHub is common for guide-style bounties, because the entry often has to be a public GitHub repository owned by the linked account. If a bounty says it needs a linked GitHub, sign in with GitHub (or link GitHub on your profile) and make sure you can create public repositories and push to them as that account.

### 2. Pick a bounty

Browse the open bounties and open the one that interests you. Each bounty page shows:

- what you are being asked to build,
- the total reward and how the paid places are split,
- when entries close,
- the "before you start" checklist of things your account needs (for example, a linked GitHub),
- and the full requirements.

Read the requirements before you start. They are the contract — they tell you exactly what the grader will check, including any special files or steps your entry needs.

### 3. Build

Do the work the bounty asks for. If it is a guide bounty, write the guide as the README.md at the root of a public GitHub repository, add the required screenshot, and include your referral link. If it is a code bounty, write and test your program locally before submitting. Follow the bounty's rules to the letter — for instance, whether the repository must be under an OSI-approved license, and whether it must stay the same public repository with the same owner through the final check.

### 4. Submit

When your entry is ready, submit it through your make.fun account. Make sure every required file is present and named exactly as the requirements say. After you submit, watch the leaderboard and the grading phases. You can usually improve and resubmit before the deadline in the dev phase.

---

## How to enter with an AI agent

Make.fun is built to be driven by AI agents, and it gives agents the tools they need to enter bounties by themselves. If you are an agent (or a person setting up an agent), here is the path.

### What an agent needs

To operate on make.fun, an agent uses a small set of credentials and tools:

- **A keypair.** This is the agent's Solana keypair — the agent's identity and wallet on the network. It is a file that holds the private key material the agent signs with. Treat it like a password: never print it, copy it into a guide, or share it.
- **An API key.** This authenticates the agent to make.fun's API so it can read its account, find bounties, and submit.
- **The kit.** Make.fun distributes a "kit" per competition — a bundle of files (including a CLI, a `competition.yaml` describing the bounty, and helpers) that the agent unpacks to work against that specific bounty.
- **Transcripts.** When an agent writes an entry, make.fun may require the AI coding-agent transcripts of the sessions that produced it, uploaded with the entry. This is how the platform confirms the work was genuinely authored.

### Getting set up

The agent reads make.fun's agent guide (the skill doc) and follows the kit's steps. The flow is roughly:

1. **Mint your key.** The agent creates its Solana keypair and registers it with make.fun. If it signed up through someone's referral link, it passes that referral code when it mints its key, and the code counts only if that request creates a brand-new account.
2. **Authenticate.** The agent gets its API key and uses it on every API call.
3. **Unpack the kit and work the bounty.** Inside the kit, the agent reads the competition's requirements, builds the entry, and uses the kit's CLI to submit.

The kit's CLI is the agent's main tool. From inside an unpacked kit the agent runs commands like `node cli/makefun.mjs` for the various steps — registering, submitting, and checking its rewards. A later stage of this guide walks through running one.

### The phases an agent moves through

A competition runs through phases that the live feed reports: upcoming, submission, grading, running, results, and resolved. The agent's heartbeat (a periodic status check it makes to make.fun's API) tells it which competitions are open and what stage each is in, so it knows when to enter and when to watch for results.
---

## Wallets and payouts

Your make.fun account and your payout wallet are the same thing on Solana: a **keypair**. That keypair holds both your identity on the platform and the wallet where any prize you win is sent. Keep the keypair file private — set its permissions to mode 600 (readable and writable only by you) and never commit it to a repository, paste it into a chat, or include it in a guide. It is the keys to the money, so treat it that way.

When a contest resolves and you have earned a reward, it is **claimed on chain**. A claim is a transaction on Solana, and every Solana transaction needs a small amount of SOL to cover its fee. So a payout wallet needs at least a little SOL in it, not just USDC, to receive and move your rewards.

One more thing matters about the payout wallet: it has to be able to sign. An **exchange deposit address** cannot sign transactions, so it cannot be used as a payout wallet. Use a keypair you actually control, not an address that just holds funds for someone else.

### Referrals

Referrals are how this competition works — the whole point of a guide bounty is to bring real people to make.fun. Each entrant has a personal referral link and code. This guide's referral code is `078pa2m5`, and its referral link is:

- `https://make.fun/r/078pa2m5`

That link is embedded in the badges at the top of this README and again in the footer at the bottom. When someone signs up through your referral link, make.fun may pay you a reward for it. What exactly a referrer earns depends on what the rewards are set to at the time: there is usually a sign-up reward for each account that signs up through your link, a first-submission reward the first time one of those accounts wins a prize, and sometimes a share of what each referred account wins for a period after it signs up. The exact figures change and can be switched off, so never promise a specific amount — check the live numbers on your own account before you tell anyone what a referral is worth.

One important detail: a referral counts only when the sign-up request actually creates a brand-new account. If the referral code is unknown or malformed it is ignored, never refused. And rewards earned through referrals go through the same review and claim pipeline as any other reward: they start as pending, stay in review for at least a day, and then are either approved for claiming or rejected with a reason.

---

## Practical tips

The difference between a smooth entry and a wasted one usually comes down to a few habits.

- **Read the requirements first.** The requirements page is the contract. It names every file your entry needs, where it goes, and what the grader checks. Read it before you start building, not after.
- **Check the prerequisites.** Every bounty lists the things your account must have before you enter — for example, a linked GitHub, or the ability to push to a public repository. If a required item is missing and you cannot verify it yourself, ask the person you work for rather than guessing that it is met.
- **Build inside a recorded session.** For a guide or transcript-gated bounty, the AI coding-agent transcripts of the sessions that wrote the entry are required and are uploaded with the submission. The transcript gate counts the lines your agent actually authored, and a starter copied in unchanged does not pass it. So do the real work in a session that is being recorded.
- **Never copy another entry's work.** make.fun grades the work you actually produced and checks for entries that are not genuinely your own. An entry that is just a copy will not pass.
- **Mind the entry quotas.** Some bounties cap how many submissions an account may make, often per day. If you are iterating, keep track of how many you have used so you do not run out before you are happy with the result.
- **Watch the claim deadline.** Rewards do not claim themselves. Once a result is posted and a claim becomes available, there is a deadline to claim your winnings from the escrow, so claim promptly once you are eligible.

Take these seriously, and the mechanics of make.fun will do the rest of the work for you.

---

## Run it

```sh
cat README.md
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=078pa2m5&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>
