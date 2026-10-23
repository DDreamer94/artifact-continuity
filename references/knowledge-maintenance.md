# Layered knowledge and reconciliation

Use this for an existing knowledge collection or a requested knowledge-management
change. Reuse the project's sources, maintained pages, indexes and tooling. Scale
the structure to useful reader questions; small collections can keep summaries,
categories and tag navigation in the same pages.

## Give each layer a distinct job

| Layer | Content and purpose |
| --- | --- |
| Sources and details | Original documents, accepted decisions and distinct evidence events, with their authority and provenance. Exact identifiers and exceptions remain searchable here. |
| Topic summaries | What is known about a scoped subject, the decisions, exceptions and open conflicts, with links to supporting sources or sections. A long source can have its own summary when that helps readers. |
| Category overviews | Short descriptions of related topics, their coverage and links. Include representative questions when they help an agent choose where to look. |
| Tags and aliases | Cross-cutting lookup routes. Tags describe shared concerns; aliases name the same subject. Neither creates another copy of a page. |

Prefer summary sections in maintained pages and category sections in existing
indexes before adding files. Do not create one page per extracted noun or one
summary per screenshot. Reuse established category labels and a small tag
vocabulary; introduce a category when several topics need a durable home. Multiple
tags can cross categories. A category is not necessarily a filesystem folder, and
classification alone does not justify moving a canonical file.

The project decides authority. A newer draft or a fluent generated summary does
not supersede an accepted decision. Carry release/environment and authority labels
into summaries and overviews when combining them could change the meaning. Mark
uncertainty and contradictions; resolve them from sources and recorded decisions.

## Keep derivation inspectable

Use existing frontmatter, an index row, manifest or generator state to record:

- The topic's stable identity or canonical path, scope and authority/status.
- Supporting source identities, precise locators where available, and the revisions
  actually used. For mutable inputs without reliable revisions, use content digests.
- Which summary or overview depends on which inputs; distinguish a derivation
  dependency from a merely related-topic link.
- The last reconciled input set and relevant generation/selection rules. Record
  unresolved inputs instead of claiming complete freshness.

Track the source set as well as individual versions: additions, removals, changed
source selection and authority decisions can invalidate a summary even when all
previously recorded files are unchanged. Category membership and tag/alias changes
can invalidate navigation. A timestamp alone does not bind a summary to its inputs.
Keep this receipt in the established metadata owner; do not build a second registry
or require a new sidecar for every artifact.

## Reconcile changes incrementally

1. **Identify the change.** Compare current inputs and the canonical destination
   with the recorded baseline, including human edits. Match candidate duplicates
   by subject, scope, authority and provenance, not similarity alone.
2. **Select affected work.** Follow derivation dependencies. A content change may
   affect a topic summary and its category overview; a path-only rename may need
   only reference repairs. When dependency records are incomplete, inspect the
   relevant source inventory and consumers before asserting that nothing is affected.
3. **Reconcile meaning.** Update the maintained editing source, preserving valid
   facts, reviewer notes and distinctions between accepted, proposed and historical
   material. Use an authoring workflow for substantive synthesis. Preserve source
   evidence even when retiring a superseded claim.
4. **Refresh derived layers.** Update affected summaries, overview entries, tags,
   aliases and generated views. Compare source and destination revisions again
   before promotion; if either changed during generation, reconcile or regenerate
   against the current baseline. Do not overwrite with a result based on stale inputs.
5. **Verify and record.** Check affected coverage, links, meaning and searches;
   update the existing derivation receipt only for inputs actually reconciled.

If the input set, relevant rules, scope and maintained output are unchanged, reuse
the result. A repeat pass should not rewrite files just to refresh a date. Reusing
knowledge or a prior test result is not a new execution or observation. An unresolved
gap remains unresolved on repeated passes.

When a source disappears, investigate relocation or an authorized replacement.
Keep the missing source visible in coverage and label dependent claims as needing
reconciliation. Deleting references, converting broken links to plain text, or
discarding the last-source page does not by itself repair knowledge. Removal still
follows the main skill's authority, preservation and consumer checks.

## Search from an appropriate level

- For a broad question, inspect category overviews and topic summaries, then open
  supporting details before making a precise claim.
- For an exact ID, error code, quoted phrase or source name, search the detailed
  content directly. Preserve source terminology even when summaries paraphrase it.
- Use tags, aliases and related-topic links to expand discovery within the authorized
  project and relevant baseline. If a category or tag search misses, broaden to
  titles, aliases, summaries and source text before concluding absence.
- Treat summaries as navigation and synthesis. Verify disputed or precise claims
  against authoritative sources; a higher search ranking does not grant authority.

Use available project search tools. This workflow can work with Markdown, indexes
and `rg`; it does not require a vector database, graph service or background job.

## Check knowledge health in the affected scope

Check structural properties separately from meaning:

- **Coverage:** every required source in the agreed inventory has a discoverable
  entry, owning topic or explicit unresolved status, including unavailable sources.
- **Navigation:** links and anchors resolve; topics are reachable from the current
  entrypoint. Where graph views are used, verify actual nodes, edges and filters;
  a file URL in prose is not evidence of graph inclusion.
- **Freshness and meaning:** source sets/revisions match, important exceptions and
  conflicting baselines remain visible, and human edits have been reconciled.
- **Identity:** related topics and shared aliases have not been merged incorrectly;
  duplicate candidates have been inspected; separate evidence events retain identity.
- **Retrieval:** try a broad topic question, an exact identifier, and a cross-category
  tag or alias relevant to the change. Inspect whether the result leads to the right
  source and baseline. Add a stale/conflicting-source case when that behavior changed.

Record unresolved issues in the existing task log or issue list with the affected
artifact, source/baseline, impact and next action. Use its existing status convention
and close issues only after checking the affected result. Report what was checked;
link validity or a synthetic health score cannot certify factual correctness.

## Design provenance

Informed by Tencent WeKnora source at
[`8cb53fdbc58e4c15aafdba973d65742551e4c9cd`](https://github.com/Tencent/WeKnora/tree/8cb53fdbc58e4c15aafdba973d65742551e4c9cd):
[wiki generation and identity prompts](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/agent/prompts_wiki.go),
[aggregate profile reuse](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/application/service/knowledgebase_profile.go),
[stale-summary detection](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/application/service/knowledge_summary_refresh.go),
and [wiki quality checks](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/application/service/wiki_lint.go).
These are conceptual adaptations, not imported implementation code. Project authority,
review preservation and evidence-event identity remain governed by this skill.
