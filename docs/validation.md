# Validation record

Date: 23 October 2026.

This record separates the initial standalone extraction from the subsequent review of change handling and project-tree manageability. Results apply to the instruction hashes recorded for each exercise, not automatically to later revisions.

## Initial extraction: amendment exercise

Two fresh-context agent runs used the same synthetic Lumen project and maintenance task: one control without the skill and one with the standalone skill and its relevant references. Each condition ran once in a separate temporary directory. These are samples from the current Codex runtime; exact provider build and sampling parameters were not recorded. They do not establish comparative model quality.

| Property | Control | Skill enabled |
| --- | --- | --- |
| Existing handover and knowledge entrypoints retained | Observed | Observed |
| Accepted R1 online/offline rules kept distinct from R2 draft | Observed | Observed |
| Stable finding ID, reviewer comment and limited prior approval preserved | Observed | Observed |
| Source bytes, rendering topic and original observation A unchanged | Observed | Observed |
| Equal-byte observation B retained as a distinct event | Observed | Observed |
| Imported B has source path, original filename, import date and digest recorded in the manifest | Incomplete: copied bytes were checked, but this provenance receipt was absent | Observed |
| Affected topic and overview include approved amendment D-101 | Observed | Observed |
| Missing R0 source remains explicit | Observed | Observed |
| Repeat request produces no writes | Reported by control agent | Verified against retained before/after hash and mtime inventories |

The skill-enabled run modified the handover, networking topic, existing index and evidence manifest, and added only the new observation file. All twelve resulting project files retained identical SHA-256 hashes and nanosecond modification times during the repeat pass. The controller inspected the actual outputs, verified immutable inputs and evidence metadata, and compared the saved repeat inventories with the resulting files.

Broad topic navigation, exact identifiers and alias/tag retrieval were checked in this small filesystem collection. Generic PASS evidence did not prove the amended behavior passed a real execution: it omitted mode, retry count and error code. The revised finding still required reviewer approval, and the historical R0 source remained unavailable.

[Evaluation instructions and raw fixture](../evals/README.md) are included for independent exercise. [Observed-result hashes](../evals/observed-results.json) bind the record to the tested instructions and resulting files. Exact local reports and inventories are retained under ignored `.local/evals/`; they are not distributed as a public benchmark dataset.

## Initial extraction: package checks

The skill-creator structural validator passed. The existing personal source package and installed shared entrypoint remained unchanged during extraction. The two references and UI metadata match the starting package byte-for-byte; only the documented authority paragraph differs in `SKILL.md`.

The standalone Git distribution is also checked for local Markdown links, whitespace, and unsafe staged paths/content before publication. The original private repository, local research inputs, runtime configuration and credentials are outside that distribution.

## Purpose review: changes and tree manageability

The owner identified preventing redundant revision documents as a core purpose alongside preserving changes. A read-only instruction review found that the existing skill already covers stable ownership, three-way draft comparison, human notes, distinct evidence and authorized duplicate retirement. Two ambiguities warranted clarification: ordinary exports needed the same identifiable generation baseline as knowledge summaries, and ordinary working revisions needed a clearer distinction from required permanent snapshots and raw-source retention.

The revised entrypoint and workspace reference now foreground tree manageability, reuse destinations across retries, keep continuity bookkeeping in existing owners, describe safe staged regeneration and check task-created scratch residue. They distinguish working revisions from source/evidence retention requirements without authorizing broad deletion. No runtime, automatic file watcher or new registry was added.

Before editing instructions, two independent fresh-context agents exercised the old skill on the [Atlas fixtures](../evals/tree-lifecycle.json). The controller inspected actual content, protected-file hashes, tree changes and repeat modification times:

- Routine amendment: established source and HTML retained, HTML-only reviewer note reconciled, stale generator target corrected, no draft cleanup before authorization.
- Authorized consolidation: all unique reviewer notes retained; exactly two redundant drafts removed; the complete project changed from 16 files to 14. Accepted sources, comparison baseline and consumer, distinct equal-byte observations and unrelated project stayed byte-for-byte unchanged.
- Repeat: all 14 files retained hashes, sizes and nanosecond modification times; no new paths.
- Blocked generation: both attempts failed in scratch space because the approved logo was unavailable. All five original files and their modification times survived; partial output and temporary directories were retired; the retained export was accurately reported as stale.

These successful baseline results are preservation evidence, not a demonstrated cleanup failure fixed by the revision.

Three fresh-context runs then exercised the first revised candidate on Atlas consolidation, blocked export and the original Lumen amendment. All preserved the required content and passed repeat hash/mtime checks. Lumen again changed four existing files and added only observation B, with import provenance and the unresolved coverage/source gaps preserved.

Controller inspection found a remaining failure in the first candidate: Atlas's generation was verified, but its source, renderer and output revisions were not recorded in the project. The workspace reference was tightened to require a durable receipt in an existing owner when version history does not already identify the baseline. This is a demonstrated instruction gap; it does not mean the earlier content or cleanup checks failed. Exact instruction/output digests and partial results are recorded with the existing [observations](../evals/observed-results.json).

A final independent Atlas run passed all three phases with that clarification. The existing generator configuration now holds verified source, renderer and output SHA-256 values; they match the final files after consolidation. The run still retired exactly two drafts, added no maintained files or directories, preserved the protected content and performed no writes on repeat. The controller compared the retained inventories against the actual final files, rather than accepting the agent's completion report alone.

The final clarification changed only the workspace reference's successful-generation receipt guidance. Atlas was rerun against that exact final snapshot. Blocked-export and Lumen results remain bound to the first revised snapshot; their relevant preservation rules and the knowledge reference were unchanged. All scenarios are single samples in the current Codex runtime, with exact provider build and sampling parameters unrecorded. No concurrent-writer or automatic-discovery test was performed.

## Limits

This exercise did not test automatic skill discovery, other agent hosts, large-corpus search quality, production use, model speed, a live WeKnora deployment, native WeKnora skill import or any API round trip. The [WeKnora pairing](weknora.md) remains a proposal. Re-run relevant checks when the skill's behavior or integration changes.
