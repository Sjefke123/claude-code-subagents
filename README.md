# Claude Code Subagents

> **Beta.** This setup is in beta. Settings, model choices and routing rules may change, and the quality and credit savings are estimates that have not been measured.

A ready-to-use subagent setup for [Claude Code](https://code.claude.com). The lead model plans and accepts the work. Specialised agents do the research, building and review. It works with any lead model (Fable, Opus, Sonnet or Haiku) and is tuned to use less of your usage limit.

## What is included

| File | Purpose |
|---|---|
| `CLAUDE.md` | Routing rules: when the lead uses which agent |
| `.claude/agents/builder.md` | Implements a planned change and runs the checks |
| `.claude/agents/reviewer.md` | Checks the finished change against the original brief |
| `.claude/agents/research.md` | Looks up outside docs and facts |
| `.claude/agents/Explore.md` | Fast local file discovery |
| `.claude/agents/worker-*.md` | General workers on Haiku, Sonnet, Opus and Fable |

## Models and effort

| Agent | Model | Effort |
|---|---|---|
| Explore | Haiku 5.5 | low |
| research | Sonnet 5.5 | low |
| builder | Sonnet 5.5 | medium |
| reviewer | Sonnet 5.5 | high |
| worker-haiku | Haiku 5.5 | low |
| worker-sonnet | Sonnet 5.5 | low |
| worker-opus | Opus 5.5 | medium |
| worker-fable | Fable 5.2 | high |

All agents may edit files. Builder escalates to Opus only after two failed attempts on Sonnet.

## Install

Per project: copy `CLAUDE.md` and `.claude/agents/` into your project root.

For all projects: copy the files into `~/.claude/` (put the agents in `~/.claude/agents/`).

Then start a new Claude Code session so the agents are detected.

## How it works

1. You pick a lead model.
2. The lead handles tiny changes itself and delegates larger work.
3. Builder implements, reviewer checks, and findings go back to builder.
4. The same team runs for every lead model, so the quality of the work stays consistent.

## Credits

Based on the setup from Brad Bonanno's "Give Fable a team" field guide, adapted for lower usage.

## Notes

Routing rules in `CLAUDE.md` are instructions the model follows. Claude Code does not enforce them.
