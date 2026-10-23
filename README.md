# Artifact Continuity

**Keep improving the work. Keep the tree manageable.**

Artifact Continuity gives AI agents reusable instructions for **handling changes without accumulating redundant files**. An artifact can be a report, project brief, review, knowledge page or generated export. The skill helps the agent update the existing work, merge useful revisions, preserve human edits and required history, and remove redundant working copies after checking them.

For people and teams who iterate on AI-assisted work through **retries, regenerations and versions**: researchers and writers, developers and QA practitioners, and builders of agent or knowledge workflows.

Your next attempt should build on the current file and the right input versions. A new session or retry should not automatically produce another `final-v3` document or dated folder. You invoke the skill through an agent with access to your project files; the agent performs the work using its available tools.

[See the example](#what-a-manageable-tree-looks-like) · [Install and use](#install-and-use) · [Validation](docs/validation.md)

Created and maintained by [DDreamer94](https://github.com/DDreamer94), with AI-assisted development. Its knowledge-maintenance guidance is informed by concepts from [Tencent WeKnora](https://github.com/Tencent/WeKnora). [Credits and provenance →](docs/provenance.md)

## What a manageable tree looks like

An ongoing brief has collected two extra drafts:

```text
reports/
  brief.md
  draft-v2.md
  brief-final.md
  release-baseline.md
exports/
  brief.html
```

After an authorized consolidation:

```text
reports/
  brief.md               # Current source, with useful edits reconciled
  release-baseline.md    # Frozen text still needed by a comparison
exports/
  brief.html             # Existing view regenerated from the current source
```

Before removing the two draft copies, the agent merges their useful notes into `brief.md`, resolves conflicting claims and updates links or tools that used the drafts. The HTML is regenerated from that maintained brief. The older baseline stays because a comparison still needs it; original evidence and required source revisions also remain.

Details about which inputs and generator produced the export belong in existing metadata or configuration. Keeping track of revisions should not create another status document or archive folder for every attempt.

This is the [Atlas evaluation fixture](evals/tree-lifecycle.json): its complete project went from 16 files to 14 in both the original and final skill runs, with no writes on repeat. The final run also recorded generation revisions in existing configuration. The point is a clear current home and justified retained history; a lower file count alone does not prove a healthy tree. See the [validation record](docs/validation.md).

## Does this fit your workflow?

Start with these questions:

- **Do I return to the same work across sessions, models or agents?** Find the current source file and continue there.
- **Do retries leave duplicate drafts and make the project tree hard to navigate?** Reconcile useful changes, then retire redundant copies within the authorized scope.
- **Do regenerations leave me unsure which version to use?** Identify the current source and the input versions used to produce its exports.
- **Do reviewer comments, stable IDs or earlier decisions need to survive revisions?** Preserve review history and distinguish old approval from changed content.
- **Do I collect screenshots, traces or results from separate runs?** Keep the runs distinguishable, even when their output files contain identical bytes.
- **Do summaries or indexes become stale when sources change?** Update the affected pages and keep them linked to their sources.

If you recognize one of these patterns, start with **one ongoing artifact and its existing inputs**. A report with reviewer notes, a release handover, or a small knowledge collection is enough.

For a one-off answer with no maintained artifact, there may be little continuity work to do. Scale the process to the task; using this skill does not require a new knowledge system.

### Let your agent help you decide

Paste this into your agent for a short fit assessment:

```text
Help me decide whether artifact-continuity fits my workflow.
Ask one question at a time, up to three, about my current artifact and version,
what gets lost or duplicated during retries, and who relies on the result.
Then recommend whether to use it, the smallest useful starting scope,
and one concrete success check. Keep this assessment conversational;
leave files unchanged.
```

## See it in your own work

These are illustrative situations. The technical handover also has an exercised synthetic fixture; the other examples describe intended use rather than tested customer outcomes.

### Research, writing and recurring reports

An agent regenerates a research brief after a source correction. Continue in `research-brief.md`, retain the review comments, record the corrected source revision, and reconcile the affected overview. Retire a promoted working draft after checking its useful edits reached the maintained brief. Keep any older baseline that a comparison actually requires.

**Useful result:** the next session can find the maintained brief and see which sources it reflects.

### Development, QA and release handovers

An approved amendment changes one rule in a release handover. Revise the existing finding, retain its ID and reviewer comment, mark changed wording for review, and keep two verification runs distinct even when their result files match.

**Try it:** [Lumen's synthetic amendment example](examples/review-amendment.md) and its [validation record](docs/validation.md). The exercise checks document maintenance; it does not verify a real product's behavior.

### Agent and knowledge workflows

An agent regenerates a knowledge export after another source is added. Reconcile the affected topic and overview, record the input set used, and compare any returned edits with the current editing source before promotion.

**Useful result:** a regenerated view has a traceable relationship to its maintained source. The optional [WeKnora pairing](docs/weknora.md) explores this boundary as a proposal.

## What changes in practice?

| Situation | Expected action |
| --- | --- |
| Another session adds findings to the same review | Update its established editing source and existing views. |
| A draft is ready to become maintained work | Compare the baseline, current destination and draft; reconcile human edits. |
| Several drafts represent the same ongoing deliverable | Merge useful changes, repair consumers and retire verified redundant copies within scope. |
| Regeneration fails halfway through | Preserve the last valid output, report it as stale, and clean disposable partial output. |
| A new evidence capture matches an old file's bytes | Keep both when they represent different observation events. |
| An approved amendment adds a source | Refresh the affected topic and overview, preserving scope and unresolved gaps. |
| The same maintenance request runs again with unchanged inputs | Reuse the result and make no unnecessary writes. |

The agent follows your project rules and the scope you authorize. Routine revision does not authorize a project-wide cleanup. This package contains instructions and references; it runs no background service or automatic cleanup job.

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
Use $artifact-continuity to apply these approved changes to the existing
project brief and its exports. Preserve human notes and required history.
Reconcile and retire redundant drafts within this brief after verification.
Report the current entrypoints and any unresolved gaps.
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
references/workspace-layout.md        Ownership, retries, retention and promotion
references/knowledge-maintenance.md   Layers, freshness and reconciliation
agents/openai.yaml                    Optional Codex UI metadata
examples/                            Worked scenario
evals/                               Synthetic fixture and inspection criteria
docs/                                Provenance, validation and pairing proposal
```

The [validation notes](docs/validation.md) distinguish the initial amendment exercise from the tree-management and failed-regeneration review. These are small synthetic filesystem scenarios, with actual artifacts and repeat-write checks. They do not establish performance, automatic discovery or reliability across every agent host.

## Maintain and reuse

Keep portable instructions in `SKILL.md`, `references/` and `agents/`. Leave host paths and private project policies in their owning environments. When changing behavior, exercise the [evaluation scenario](evals/README.md) and inspect actual files and meaning; structural validation alone is insufficient.

This repository is the standalone editing source going forward. Downstream bundles should consume pinned revisions. Publishing it does not automatically replace an existing managed installation.

## License and credits

[MIT License](LICENSE), copyright 2026 DDreamer94.

WeKnora is acknowledged for conceptual influence on knowledge organization, identity reuse, freshness and quality checks. Its implementation files are not distributed here. The [provenance record](docs/provenance.md) links the reviewed revision and explains the attribution boundary.
