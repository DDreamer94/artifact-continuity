# Workspace lifecycle and draft promotion

Read this when organizing a document-heavy workspace, retaining revisions, promoting a draft or regenerating an existing output. First use the named project root, its instructions, indexes and recorded decisions. This reference offers decision criteria; it does not prescribe another project's folders or authorize a migration.

## Locate the boundary and owner

Confirm the physical project root, independent repositories, source records, editing sources, generated views and known consumers. An active shell directory or compatibility alias need not be the owner. Follow applicable `AGENTS.md` and project decisions. If the project has an accepted document-authority policy, use that policy to distinguish original evidence, accepted knowledge, current implementation, operational guides and historical work. Do not promote a later draft or projection into accepted authority by moving or renaming it.

For each maintained artifact, identify its purpose, lifecycle, source baseline, editing source and reader entrypoint in the existing index or pack metadata. Keep one maintained home for the same identity. Match by subject and scope, not by the newest timestamp or filename. A new release, observed environment, capture or independent execution can have its own record when its provenance differs. Preserve IDs, reviewer comments, source hashes and browser progress keys where relevant.

Use descriptive maintained names that explain content and scope. A date belongs in the name when it distinguishes a source revision, observation or run; another workday alone does not justify a duplicate pack. Name newly imported reference files according to the project's adopted convention and keep their original filenames in provenance. Preserve a raw source filename when an explicit project rule or native file dependency requires it; preserve capture identifiers and intentional historical names when renaming would damage provenance. A naming change alone does not justify a second content copy. Do not apply a case-release or environment scheme outside projects that have adopted one.

## Compare and promote drafts

1. Stage a persistent draft under the existing draft owner when a file is useful. Record its intended destination, starting baseline and unresolved questions in the draft or existing task log. Scratch calculations can stay in a temporary area.
2. Compare the starting baseline, current canonical destination and draft. Inspect unique additions, overlaps, contradictions, reviewer edits, evidence and dependent links.
3. Choose addition, modification, replacement or discard. Apply changes to the established editing source, regenerate its views, and keep only justified historical inputs. A draft for review is not an approved case, execution result or accepted policy.
4. Verify the destination, identifiers, evidence links and consumers. Retire only the redundant draft after required unique content has been reconciled. The user's authorization for the task controls whether to apply the change; this workflow does not add a routine approval gate.

## Regenerate without accumulating attempts

Identify the source, generation rules and last generated output using existing history or generator metadata. Compare that baseline with the current source and current output so manual edits can be reconciled into the editing source. If the baseline is unavailable, inspect the differences and preserve unresolved edits; do not treat the output as disposable merely because it is generated.

After successful regeneration, make that baseline available to the next session. If existing version history does not already identify it, update the existing generator configuration, artifact metadata or owning index with the source revision/digest, relevant generator/rules revision or digest, and resulting output digest. Record only inputs actually used. Source and output paths alone do not identify their revisions. A check recorded only in the current conversation does not give future sessions a project baseline; do not create a separate sidecar when an existing owner can hold it.

When a generator can truncate a good output before failing, generate into the existing ignored scratch area or use its safe replacement mechanism. Validate the candidate, recheck source and destination changes, then replace the established output. Keep the last valid output until a replacement passes. If generation is blocked, report that the retained output is stale and name the dependency; do not label it current.

A retry uses the same maintained destination. Retire known disposable partial outputs after inspection; keep unfinished work only when it contains unique work needed for resumption, with its destination and blocker recorded in the existing owner. An ignored folder can also accumulate junk. Check task-created staging before delivery without sweeping unrelated scratch files. An actual test execution still has its own observation identity, even if it was triggered by a retry.

## Retain useful history

Separate the current editing source, drafts still awaiting review, regenerable views, distinct observations and consumer-required snapshots. Ordinary revisions can remain in the project's existing version history; verify the required content is recorded there before relying on it. This does not require creating a Git commit for every edit or setting up a new archive system.

During authorized consolidation, assess each proposed retirement against current consumers, unique edits and the project's provenance or retention requirements. A superseded working source copy is not automatically a permanent raw-source archive. Equally, a raw imported source or independent evidence event is not disposable merely because no current page links to it. Preserve unresolved cases and report the reason in the existing task record.

## Shared resources and compatibility

The same ownership test applies to templates, scripts, schemas, skills, plugins, MCP configuration and indexes. Distinguish an installed capability from a delivery copy or upstream snapshot; update the maintained owner through its own workflow. A matching digest proves byte equality, but separate observation events or pinned comparison baselines can still have distinct provenance.

Keep compatibility aliases only for named consumers that cannot yet be retargeted, and document their owner. Do not silently rewrite imported repositories or their local instructions. Verify current entrypoints and relevant links after a move. Leave unrelated paths, product results and external systems outside the authorized cleanup.
