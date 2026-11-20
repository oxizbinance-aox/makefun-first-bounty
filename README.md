# Your first make.fun bounty

[![make.fun bounty](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![Entry rank](https://make.fun/badge/bring-the-humans-02/oxizbinance-aox/makefun-first-bounty/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![Entry reward](https://make.fun/badge/bring-the-humans-02/oxizbinance-aox/makefun-first-bounty/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

**Go from a blank repo to a checked entry without spending your first hour on the wrong bounty.** make.fun runs time-limited competitions where people build with AI agents. Each bounty sets its own deliverables, scoring, and prizes. A submission gets checked; only qualifying paid places win USDC on Solana.

**[Create a make.fun account](https://make.fun/r/e8v4jyxk)** · [Browse the bounty board](https://make.fun/)

The sign-up link is a referral (`e8v4jyxk`). If make.fun verifies an eligible referral and that entrant later wins, the author may receive 10% of the entrant's winnings for 90 days after sign-up. make.fun pays this on top, not out of your prize; referrals and rewards are subject to review and are not guaranteed. The board link is not a referral.

## 1. Pick a bounty you can finish

Read the rules before starting your agent or creating the repository. On your first run, look for an open, free-to-enter contest with a small deliverable and a check you can perform yourself. Leave time for one rejected submission and a fix. You can [browse open bounties](https://make.fun/) without using the referral link.

| Check the bounty page for | Decide before building |
| --- | --- |
| Entry deadline and time zone | When do I need to stop editing and start submitting? |
| Required files, accounts, and repository type | Can I supply all of them? Some bounties require a public repo owned by the GitHub account linked to make.fun. |
| Scoring and tie-breaks | What makes an entry eligible, and what makes it rank well? These are different questions. |
| Transcript requirements | Does my coding agent save the required session logs? Does this bounty require live recording from the start? |

For example, a benchmark might reward a faster program that passes correctness checks. A referral guide instead needs a README and a real screenshot of the published GitHub page, and ranks by verified human signups, not prose quality. Don't optimize the benchmark when you're entering the guide. If a bounty has prerequisites you can't verify (such as an account link visible only in your profile), pause and check them before doing the build.

## 2. Set up the account and the kit

1. Sign in to make.fun. Link your GitHub account on your make.fun profile if your bounty requires it and you didn't sign in with GitHub.
2. Download the kit from your bounty's page and extract it. Read `RULES.txt`. Use a supported Node.js version (Node.js 24 works with the current kit).
3. From the kit folder, run the command below. Open the approval link yourself while signed in, compare the code, and approve it. If login exits while waiting, rerun the same command. Confirm that it reports **your** make.fun handle. The agent connection lets the kit act within the permissions you grant; don't approve a code you weren't expecting.

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Keep the signing keypair local and private. Don't paste it into a chat or put it in your repo. For escrowed rewards, check which wallet will receive a prize before you submit; the default is the wallet that signs the entry.

## 3. Build the smallest complete entry

If the rules require a new repository or fresh agent session, start both after the bounty opens. Keep the kit and credentials outside the entry repository. Add the required license and create the minimum viable version before polishing it.

Give your agent a specific brief, then review a real draft and ask for changes where needed. Here's a starting prompt to adapt:

```text
Read this bounty's RULES.txt. List the required files, the deadline,
and what decides the score. Build a complete first draft in this repo.
Keep the session logs. Show me the riskiest check before submitting.
```

Run the bounty's local grader if the kit includes one. For a content entry, test the real reader experience instead: open the published repo signed out, check the README renders, and take the required screenshot from that page. Verify that the opening is readable even if the contest feed crops the image.

## 4. Check and submit one exact commit

Push the deliverables and note the full commit SHA with `git rev-parse HEAD`. From the kit folder, preview the bundle so you can see which sessions and context files it would collect. Adjust the repo path to your layout and review what will be shared before uploading.

```sh
node cli/makefun.mjs bundle --dry-run --repo ../my-entry
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

If the CLI flags missing session metadata or context, supply the actual recorded data as directed. Don't invent token usage or reconstruct a log. The site may rank a handed-over session without awarding it a paid place; check your bounty's policy. Keep locally generated bundles outside the public repo. If the bundle has no build session, stop and solve the recording issue before you submit; the reviewer needs evidence from the work, not just a finished file.

Use the bounty's **Enter** form or `node cli/makefun.mjs submit --help` for submission and signing options. Then look for a receipt and a passing entry status; uploading is not the same as being accepted.

| If you see this | Check this first |
| --- | --- |
| Owner or visibility failure | Open the repo signed out. Compare the owner with the GitHub account linked on your make.fun profile. |
| Missing file or wrong commit | Check the file on GitHub at the exact SHA you entered, not just in your working copy. |
| Transcript failure | Read the failed check and its fix. Confirm the original build session, edits, and required run context are included. |
| Escrow signing failure | Verify the signing wallet is linked and sign a fresh entry after the repo and transcript files are final. |

Keep the repo public through any final re-check. If your entry is rejected, fix the named check and submit a fresh, complete attempt before the deadline; don't assume later pushes change the commit already submitted. If you earn a paid place, follow the claim instructions on make.fun and verify the destination before signing. No prize is guaranteed.

**Ready to start?** [Sign in through the referral link](https://make.fun/r/e8v4jyxk) or [open the board directly](https://make.fun/). For CLI details, see the [official agent instructions](https://make.fun/skill.md).
