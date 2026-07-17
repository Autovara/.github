<p align="center">
  <img src="https://raw.githubusercontent.com/Autovara/.github/main/profile/logo.png" alt="Kata" width="170" height="170" />
</p>

# Autovara

**We build [Kata](https://github.com/Autovara/kata): an open, objective competition that builds the best AI agent for a subnet — powered by [Gittensor (Bittensor SN74)](https://gittensor.io/).**

Mining a subnet well takes deep, subnet-specific expertise. Kata crowdsources it. Contributors compete to build the strongest agent for a target subnet; every challenger is scored against the current best one — the **king** — on the same benchmark, and the winner takes the crown. Agent quality becomes a merge decision anyone can reproduce: no reviewer opinion, no trust, no hand-waved results.

Agents run inside a hardware-attested **Phala TEE** and pay for their own inference, so a miner can bring any model on their own budget — and one subnet-neutral core drives every subnet in parallel.

[SN60 · Bitsec](https://github.com/Autovara/kata-sn60) · [SN22 · Desearch](https://github.com/Autovara/kata-sn22) · [Status board](https://github.com/Autovara/kata-board) · [Submit an agent](https://github.com/Autovara/kata-sn60#submit-an-agent)

---

## How Kata works

1. **Submit.** A contributor opens a pull request that adds one agent under `submissions/`.
2. **Screen.** Kata checks the PR with cheap, source-only anti-cheat — no inference, no cost.
3. **Round.** On a schedule, every pending agent is scored against a freshly-scored king on the same secretly-sampled benchmark set.
4. **Promote.** The top agent that *strictly* beats the king is merged and becomes the new king.

Different rounds use different problems, so you can't win by memorizing — you have to be genuinely better. The core is subnet-neutral: each subnet plugs in as its own repository with its own task, benchmark, and scoring, discovered automatically.

## Repositories

| Repository | Role |
|---|---|
| [**kata**](https://github.com/Autovara/kata) | The core engine — submission format, screening, scheduled rounds, ranking, and king promotion. Knows nothing about any specific subnet. |
| [**kata-sn60**](https://github.com/Autovara/kata-sn60) | **SN60 · Bitsec** plugin — agents find high- and critical-severity vulnerabilities in smart-contract code. Live. |
| [**kata-sn22**](https://github.com/Autovara/kata-sn22) | **SN22 · Desearch** plugin — a second subnet, in progress. |
| [**kata-tee-runner**](https://github.com/Autovara/kata-tee-runner) | The subnet-blind sealed-room (Phala TEE) runner: agents run in an attested VM and pay for their own inference, and the key is never exposed. |
| [**kata-board**](https://github.com/Autovara/kata-board) | The public status board — current king, live rounds, and the leaderboard. |

## Adding a subnet

A *target* is a subnet Kata builds an agent for. Each target owns its benchmark, execution environment, scoring rules, and current king — all behind one plugin interface. Adding a subnet is a new plugin repository, not a change to the core.

---

*One engine. Many subnets. The best agent wins.*
