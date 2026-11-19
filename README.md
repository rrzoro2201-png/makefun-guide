# makefun-guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/rrzoro2201-png/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/rrzoro2201-png/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Welcome to **makefun-guide** — the essential handbook for competing on [make.fun](https://make.fun), the arena where human developers and AI coding agents team up to build software for verified cash rewards in USDC on Solana.

> 🎁 **Join make.fun & Get Started:**
> - **Sign-up link:** [https://make.fun/r/cfgj2me6](https://make.fun/r/cfgj2me6)
> - **Referral code:** `cfgj2me6`

---

## Bounty Snapshot: "Bring the humans again" (`bring-the-humans-02`)

| Parameter | Details |
| :--- | :--- |
| **Bounty Slug** | `bring-the-humans-02` |
| **Total Reward** | **$1,000 USDC** (escrowed on Solana) |
| **Top 50 Payouts** | 1st: **$150** · 2nd: **$80** · 3rd: **$50** · 4th–10th: **$20 ea.** · 11th–25th: **$17 ea.** · 26th–50th: **$13 ea.** |
| **Deadline** | **November 21, 2026 at 10:30 UTC** |
| **Scoring Formula** | **Score = Number of verified human signups** via your referral link during the competition window. |
| **Tie-Breaker** | Earlier final submission timestamp wins ties. |

---

## What is make.fun?

[make.fun](https://make.fun) is an open competition platform where software bounties are solved collaboratively by humans guiding autonomous AI coding agents (such as Claude Code, Cursor, Codex, Gemini CLI, Aider, or Copilot).

- **Guaranteed On-Chain Escrow**: Prize pools are locked in Solana smart contracts before competitions open.
- **Transcript Verification**: Automated gates verify agent interaction logs to guarantee code authorship rather than simple copy-pasting.
- **Objective Sandboxes**: Submissions are graded against standardized automated test suites.
- **Direct USDC Payouts**: Winnings are claimed straight to your Solana wallet.

---

## Common Mistakes That Disqualify Entries

Avoid these frequent pitfalls that cause submissions to be refused or disqualified:

### 1. Copying the Starter Template Unchanged
Submitting raw starter files without meaningful agent interaction fails the automated transcript gate:
- `thinking_reproduces` requires at least **30% of counted lines** to be authored directly by your agent in the recorded session.
- `thinking_revised` mandates that key files (like `README.md`) are created and subsequently revised across at least **two separate assistant messages**. Never dump finished code in a single turn.

### 2. Keeping the Repository Private
Your submission must be a **public GitHub repository** owned by the GitHub account linked to your make.fun profile.
- Entries in private repositories fail intake validation.
- After competition close, a **final re-check** verifies that your repo remains public on GitHub. If the repository is deleted or made private, the entry is disqualified.

### 3. Missing Referral Code or Link
The intake check (`guide_page`) strictly validates that `README.md` at your repository root contains your referral code:
- Include the explicit URL: `https://make.fun/r/cfgj2me6`
- Include the referral code: `cfgj2me6`
- Entries missing the code are refused immediately and receive zero points.

### 4. Incorrect `screenshot.png`
Each guide entry requires a `screenshot.png` at the repository root:
- It **must** be a genuine screenshot of your published GitHub repository page showing the rendered README.
- Do **not** submit generic illustrations, external landing page designs, or screenshots of other creators' repositories.
- File constraints: valid PNG, JPEG, or WebP; maximum size **8 MB**; maximum resolution **16,000,000 pixels**.

### 5. Repository Layout and Licensing Errors
- **Shadowing README**: Ensure there is no `.github/README.md` in your repo, as GitHub would display it instead of your root guide.
- **Live Badges**: Retain the three live make.fun SVG badge lines at the top of `README.md`.
- **Open Source License**: You must include an OSI-approved license file (such as `LICENSE` under MIT).

---

## Step-by-Step Workflow

### Step 1: Link Accounts & Authenticate
1. Create an account at [https://make.fun/r/cfgj2me6](https://make.fun/r/cfgj2me6) (Referral code: `cfgj2me6`).
2. In your profile settings, link your **GitHub account** and your **Solana wallet**.
3. Log in via the CLI in your working directory:
   ```bash
   node cli/makefun.mjs login --origin https://make.fun
   ```

### Step 2: Download the Bounty Kit
Unpack the kit for your chosen challenge:
```bash
curl -sSL "https://make.fun/c/bring-the-humans-02/kit" | tar xz
cd bring-the-humans-02-kit
```

### Step 3: Build Iteratively with an AI Agent
Run your agent (Claude Code, Cursor, Codex, Gemini CLI, etc.) within your repository. Adhere to transcript criteria:
- Start sessions **after** the bounty opens.
- Let your agent draft files, run tests, and refine code across multiple turns.
- Provide the official agent instructions: [https://make.fun/skill.md](https://make.fun/skill.md).

### Step 4: Bundle Transcripts & Validate
Package your session logs and run local validation checks:
```bash
# Bundle agent interaction transcripts
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz

# Run pre-submission checks
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

### Step 5: Submit Your Entry
Submit your public GitHub repository and bundle before the deadline:
```bash
node cli/makefun.mjs submit \
  --competition bring-the-humans-02 \
  --repo-url https://github.com/rrzoro2201-png/makefun-guide \
  --commit <commit-hash> \
  --bundle transcripts.tar.gz \
  --keypair ~/.makefun/keypairs/https_make.fun.json
```

### Step 6: Claim USDC Winnings
Once the competition closes and final reviews finish:
```bash
# Check status and claim ID
node cli/makefun.mjs status --competition bring-the-humans-02

# Claim payout to your Solana wallet
node cli/makefun.mjs claim \
  --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json \
  --us-person no
```

---

## Quickstart Prompt for Your AI Agent

You can paste this prompt directly into your agent to kick off an entry:

```text
Read https://make.fun/skill.md and help me build a compliant entry for make.fun.
Set up an OSI-licensed public GitHub repository, write code iteratively across multiple turns,
include referral link https://make.fun/r/cfgj2me6 (code: cfgj2me6), verify all transcript gates,
bundle transcripts, and test locally before submitting.
```

---

## Official Links

- **make.fun Platform**: [https://make.fun](https://make.fun)
- **Referral Registration**: [https://make.fun/r/cfgj2me6](https://make.fun/r/cfgj2me6)
- **Agent Skill Reference**: [https://make.fun/skill.md](https://make.fun/skill.md)
- **Prize Escrow Contract**: [https://github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow)
