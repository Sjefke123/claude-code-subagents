## Subagent routing (low credit use, same quality)

Applies to whichever model is selected (Fable, Opus, Sonnet or Haiku).
The selected model is the lead: plan, assign work and accept the result.

Use Explore for local file discovery.
Use research for outside docs and facts.
Use builder once the files, approach and done criteria are clear.
Use reviewer to check the finished change against the original brief.

Give each worker the goal, relevant paths, allowed changes,
acceptance checks and the output you need back.
Send concrete review findings back to builder, then recheck.

## Save credits

- Handle tiny changes and quick questions directly. Do not spawn agents for them.
- Do not spawn every role for every task. Skip reviewer for small, low-risk changes.
- Start with the cheapest agent that can do the job. Escalate only when it fails twice, or the task is clearly reasoning-heavy.
- Escalate builder to Opus by passing model opus for that one call. Never use Fable for workers.
- Give agents exact paths and the exact check command so they do not search or re-read.
- Never re-run an agent for something it already reported.
- Keep briefs short: goal, paths, check command. Do not paste whole files into a brief.
- Ask agents for short reports. Findings and file lists only, no long explanations.
- Run independent agents in one go instead of one by one.

## The team

| Agent | Model | Effort |
|---|---|---|
| Explore | haiku | low |
| research | sonnet | medium |
| builder | sonnet | medium |
| reviewer | sonnet | high |

## Per lead model (same team, different delegation)

| Selected lead | Team | Delegation |
|---|---|---|
| Fable | Explore haiku, research sonnet, builder sonnet, reviewer sonnet | Do small and medium changes directly. Delegate only large or parallel work. |
| Opus | same | Do small changes directly. Delegate medium and large changes. |
| Sonnet | same | Do tiny changes directly. Delegate builder work for anything bigger. |
| Haiku | same | Delegate coding to builder (Sonnet) and always use reviewer. Keep only simple edits. |

The agents run on the same models for every lead, so quality of the work is the same. Only how much the lead does itself changes.

## Extra workers

worker-haiku (low) for mechanical tasks, worker-sonnet (medium) for routine tasks, worker-opus (medium) for hard tasks only after Sonnet failed.
All subagents may edit files.
