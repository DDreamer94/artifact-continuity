# Artifact Continuity

**Pick up the work. Keep its history.**

Your next agent session should be able to find the maintained report, preserve review decisions, and understand which sources a summary actually reflects.

Artifact Continuity is a reusable agent skill for carrying **documents, evidence and knowledge across sessions**. It helps agents locate the existing editing source, reconcile changes in place, and check the outputs that depend on it.

Created and maintained by [DDreamer94](https://github.com/DDreamer94), with AI-assisted development. Its knowledge-maintenance guidance is informed by concepts from [Tencent WeKnora](https://github.com/Tencent/WeKnora). [Credits and provenance →](docs/provenance.md)

## Does this fit your workflow?

Start with these questions:

| Ask yourself | Where the skill helps |
| --- | --- |
| Do I return to the same reports or notes across sessions, models or agents? | Find the maintained home and continue there. |
| Do corrections end up scattered across several copies? | Reconcile the editing source and its exports. |
| Do reviewer comments, stable IDs or earlier decisions need to survive revisions? | Preserve review history and distinguish old approval from changed content. |
| Do I collect screenshots, traces or results from separate runs? | Retain each observation's identity and provenance, including equal-byte captures. |
| Do summaries or indexes become stale when sources change? | Follow dependencies and reconcile the affected knowledge. |

If you recognize one of these patterns, start with **one ongoing artifact and its existing inputs**. A report with reviewer notes, a release handover, or a small knowledge collection is enough.

For a one-off answer with no maintained artifact, there may be little continuity work to do. Scale the process to the task; using this skill does not require a new knowledge system.

### Let your agent help you decide

Paste this into your agent for a short fit assessment:

```text
Help me decide whether artifact-continuity fits my workflow.
Ask one question at a time, up to three, about where my ongoing work lives,
what gets lost between sessions, and who relies on the result.
Then recommend whether to use it, the smallest useful starting scope,
and one concrete success check. Keep this assessment conversational;
leave files unchanged.
```

## What changes in practice?

| Situation | Expected action |
| --- | --- |
| Another session adds findings to the same review | Update its established editing source and existing views. |
| A draft is ready to become maintained work | Compare the baseline, current destination and draft; reconcile human edits. |
| A new evidence capture matches an old file's bytes | Keep both when they represent different observation events. |
| An approved amendment adds a source | Refresh the affected topic and overview, preserving scope and unresolved gaps. |
| The same maintenance request runs again with unchanged inputs | Reuse the result and make no unnecessary writes. |

The skill supplies a decision process to an agent. The agent still needs access to the relevant files and tools, and follows the task's authorization and project rules. This package contains instructions and references; it runs no background service.

## Install and use

Use your agent's documented skill installer with this repository's root directory, which contains [SKILL.md](SKILL.md).

For an agent configured to discover skills in `~/.agents/skills/`, clone it into that directory:

```sh
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/DDreamer94/artifact-continuity.git \
  "$HOME/.agents/skills/artifact-continuity"
```

If that destination already contains a skill, review its editing source and update mechanism first. The clone command will refuse a nonempty destination. For repeatable installations, select a reviewed commit or release.

Invoke the skill explicitly in a supporting agent:

```text
Use $artifact-continuity to update the existing release handover
with this approved amendment. Preserve the review history, add the
new verification observation, and reconcile affected knowledge notes.
Link the maintained entrypoints when done.
```

Installation makes the instructions available. Automatic discovery and tool access depend on the host; check those in your own runtime.

Read the [worked example](examples/review-amendment.md), or try the [contained evaluation fixture](evals/README.md) before applying it to important work.

## How it can pair with WeKnora

Artifact Continuity guides identity, authority and reconciliation decisions. WeKnora can provide a knowledge platform for ingestion, retrieval and Wiki generation.

The [proposed pairing guide](docs/weknora.md) describes keeping project files as the editing source, publishing selected knowledge, tracking source identities and revisions, and reconciling returned edits against the current baseline.

**Status:** architectural proposal. No connector or live integration has been implemented or tested. WeKnora is optional, and this is an independently maintained project.

## What's inside?

```text
SKILL.md                              Agent entrypoint and continuity workflow
references/workspace-layout.md        Naming, ownership and draft promotion
references/knowledge-maintenance.md   Layers, freshness and reconciliation
agents/openai.yaml                    Optional Codex UI metadata
examples/                            Worked scenario
evals/                               Synthetic fixture and inspection criteria
docs/                                Provenance, validation and pairing proposal
```

The initial validation used fresh agent runs on a small filesystem collection. The skill-enabled run preserved review history, distinct evidence events and import provenance, then repeated with no writes. See [validation notes](docs/validation.md) for the control result and limits. This is not a speed or large-corpus retrieval benchmark.

## Maintain and reuse

Keep portable instructions in `SKILL.md`, `references/` and `agents/`. Leave host paths and private project policies in their owning environments. When changing behavior, exercise the [evaluation scenario](evals/README.md) and inspect actual files and meaning; structural validation alone is insufficient.

This repository is the standalone editing source going forward. Downstream bundles should consume pinned revisions. Publishing it does not automatically replace an existing managed installation.

## License and credits

[MIT License](LICENSE), copyright 2026 DDreamer94.

WeKnora is acknowledged for conceptual influence on knowledge organization, identity reuse, freshness and quality checks. Its implementation files are not distributed here. The [provenance record](docs/provenance.md) links the reviewed revision and explains the attribution boundary.
