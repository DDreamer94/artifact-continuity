---
name: artifact-continuity
description: "Use when revising or regenerating documents, reports, reviews, evidence, knowledge or exports across retries and sessions; when importing references or promoting drafts; or when duplicate revisions, stale outputs and scattered folders make the project tree hard to manage."
---

# Artifact Continuity

Keep changes correct and the project tree manageable: one maintained home per artifact, reconciled outputs, and history retained for a defined purpose. A new day, session, model, worker, correction, or retry does not create a new document identity. Apply this check before the first artifact write for a task, when scope changes, and before handing over its result. Once an evidence batch has an established owner and naming rule, do not repeat discovery for every capture.

This skill governs artifact identity, placement, history and the continuity of derived knowledge. The task's authoring or testing workflow still governs content, evidence quality, and execution. The user's explicit request for a separate deliverable takes precedence.

For project-tree organization, revision retention, draft promotion, or regeneration that could overwrite an existing output, read [Workspace lifecycle and draft promotion](references/workspace-layout.md). Follow the project's adopted layout; do not migrate another project merely because the reference offers a scheme. Resolve the project root before placement—an active conversation's working directory may be a child workspace. Follow the project's applicable instructions and accepted documentation-authority decisions when distinguishing sources, maintained knowledge, guides and historical records. This skill supplies a placement workflow, not approval to promote a draft into accepted policy.

For knowledge maintenance, summaries, category indexes, tags, Wiki/graph coverage or search improvement, also read [Layered knowledge and reconciliation](references/knowledge-maintenance.md). Use the layers the collection needs within its existing owners; a routine artifact edit does not require building a knowledge system.

## 1. Find the existing home before deciding to create

Identify the work by purpose, audience, subject/release, review round or execution event, and source baseline. Match these facts to existing artifacts; filenames and timestamps alone do not establish identity.

Search aliases and summaries to find candidates, then compare their actual scope and sources. Related subjects, a shared acronym, similar wording or equal file bytes do not establish the same artifact identity. Keep different releases and observations distinguishable.

- Read applicable project instructions, recorded user decisions, and the relevant existing README/index/manifest. Use `rg --files` and focused content searches to find plausible homes. Inspect the likely artifacts and their generators, rather than dumping the whole corpus.
- For a requested tree-wide rebase or naming cleanup, inventory all descendants of the authorized tree, including requirement/source folders and their consumers. Identify selected baselines, amendments and superseded revisions before changing names or removing duplicates; checking only generated outputs or top-level indexes is insufficient.
- Search relevant sibling roots when necessary, including singular/plural alternatives such as `output/` and `outputs/`. A miss in one folder does not establish that the document is absent.
- Follow the user's established canonical path. Otherwise use the documented owner and lineage. Neither the newest folder nor the oldest filename automatically wins. A temporary generated copy must not displace the established document.
- If a named path is absent, check the current workspace root, nearby names, existing links, and available history. State the mismatch; do not create that path merely to claim the original was restored. If the intended home remains materially ambiguous, ask one focused question and continue independent inspection.
- Find the actual editing source as well as the reader's entry point. A maintained script or data file may generate HTML, Markdown, and exports. Inspect manual changes before regeneration so they are not lost.

### Bring external reference files into the project

When adopting a file from outside the resolved project root as a project source, input or evidence, bring a copy into the project tree before citing it in maintained work. This includes Downloads, temporary folders, another workspace/worktree and downloaded or exported remote files. A link or symlink to the external location does not satisfy this action.

- Find the existing source/evidence owner and compare any local counterpart first. Reuse an identical local revision; preserve a distinct required revision with its own provenance instead of overwriting it or importing a whole external tree.
- Copy the required file and its required companion assets, preserving the original bytes. Verify the copy against the source by digest. Leave the external original in place unless moving it was expressly requested.
- Name the local file and containing folder according to the project's adopted convention, including release, scope and source revision where needed. Record the original filename even when the local name changes; retain the original name when an explicit project rule or native file dependency requires it. See the naming reference for placement.
- Record the original path or URL, original filename, source version/date when known, import date, local path and digest in the existing source index or manifest. Repoint consuming links, generators and citations to the local copy; keep the external location as provenance.

If the source cannot be copied or exported with available access, state that limitation and keep the dependency unresolved; do not claim it is preserved. Installed skills, plugins and tools remain at their maintained capability locations; this import rule governs project reference artifacts.

For an ongoing artifact, preserve its path even if it contains an old date. Put revision dates in its existing metadata or work log. Renaming it to today's date, `latest`, `final`, or `groomed` requires a real relocation need or an explicit user request.

## 2. Choose the smallest sufficient change

Discussion and exploratory work may remain drafts. A draft does not become canonical because it is newer or more complete. Before promotion, inspect the corresponding destination and classify the change as **addition, modification, replacement, or discard**. Merge into the established editing source where the identity is unchanged, preserve human comments and required history, and remove the redundant working copy after verified promotion. A request for a draft alone does not authorize replacing the maintained document; an existing instruction to apply or finish the revision does. Read the reference for the practical staging and comparison rules.

| Intended work | Default action | When a new file is justified |
|---|---|---|
| More findings, corrections, or proposals for the same review/report | Update its editing source and regenerate its existing views | A distinct supporting asset or required export belongs in the same pack |
| A retry or regeneration of the same deliverable | Reuse its destination; stage intermediate work temporarily when needed | A requested alternative or independently meaningful observation needs its own identity; an attempt number alone does not |
| Additional context for the same knowledge topic and baseline | Update the canonical page; retain sources and decision history | A separate topic or materially different baseline needs its own scoped page |
| A screenshot, trace, payload, or result from a new observation | Add an event record under the established evidence owner; update its manifest | The capture represents a different time, state, environment, build, or execution |
| Reuse of an existing observation | Reference the existing evidence if it supports the claim | A derived annotation/redaction may need a separate labelled file |
| A reader-friendly format or machine export | Regenerate the existing view from the designated source | A requested format has no existing view; record its source relationship |
| A historical baseline required by a comparison or audit | Keep only the required frozen inputs with the consuming comparison/archive | The snapshot must remain reproducible while the current source continues changing |
| A separate product/release, accepted review round, or independent test run | Establish its relationship to the existing work and follow project conventions | Its content or lifecycle must remain independently identifiable |
| Scratch calculations, intermediate downloads, or verification fixtures | Use the existing ignored scratch area or system temporary directory | It becomes a maintained artifact only when the task actually needs it |

Prefer reuse, an in-place update, or a section in the existing document before adding a supporting file. Prefer the owning pack before creating a sibling folder. A new folder needs an independently justified scope or a structural need within the established pack, not just several new files.

For every proposed new maintained path, be able to state: **owner, distinct purpose, why the existing file/section cannot serve it, and whether it is a source, derived view, event record, or snapshot.** Record this briefly in the existing task log or working update when useful; do not create another preflight report to justify a routine file.

Continuity bookkeeping belongs in existing metadata, version history or the task response. It does not require a new status document, sidecar, registry or archive folder for each revision.

Do not introduce a second root spelling, mirror a pack into knowledge/evidence, or copy an entire document tree to hold one new result. Distinct approved baselines or executions must also not be merged merely to reduce file count.

## 3. Preserve the right kind of history

**Maintained documents and knowledge.** Keep one active home per scoped subject. Incorporate corrections and explicitly retire superseded claims while retaining their sources and decision dates. Do not silently rewrite raw source documents or apply one release's rule to another. Update an existing index when the canonical relationship changes; create no parallel registry if that index already serves the purpose.

**Generated views.** Multiple formats can belong to one source of truth. Keep their edit/generate relationship and last reconciled input revisions and generation rules identifiable through existing version history, generator state or metadata. This applies to ordinary exports as well as knowledge summaries. If a reviewer edited a generated view directly, reconcile that work before overwriting it; matching case counts or titles does not prove all edits were carried forward. A missing generation baseline is a reconciliation gap, not permission to overwrite. See the workspace reference for safe regeneration and retries.

**Evidence.** A new capture legitimately creates a new file, often with a timestamp or run ID. Use the existing capture directory and manifest for its owning task. Retain case/claim ID, source or case revision, environment/build, relevant state, and capture time. Preserve originals and link derived images to them. Never overwrite distinct observations, flatten different runs, or deduplicate evidence by filename resemblance. Reusing evidence does not turn it into a new execution result.

**Review progress.** Preserve stable IDs, comments, reviewer decisions, and browser-backed progress where applicable. A path, origin, or storage-key change can strand notes. Avoid changing these during routine revision; if a move is needed, reconcile/export progress and verify the migration before retiring the old location. Import-format compatibility alone is not proof that all notes were recovered. A materially revised case retains its comments but must not silently inherit approval of different content.

**Snapshots.** Keep a frozen baseline only when a consumer needs it. Pin that consumer to the snapshot, with a revision or digest where appropriate, before updating the live artifact. Mark snapshots as historical and keep them out of the current review entry point. Do not snapshot the entire pack for every small edit.

**Ordinary revisions.** Use existing version history when it actually contains the required prior content; do not assume a file is committed or recoverable. Working revisions and failed generation attempts do not all need permanent copies. Raw sources and evidence retain their applicable provenance and retention requirements. During authorized cleanup, distinguish those requirements from redundant working history; unresolved retention needs remain explicit rather than being guessed away.

## 4. Maintain discovery alongside the owning artifact

When knowledge is affected, follow its recorded dependencies from changed sources to topic summaries and category overviews. Tags and aliases provide additional search routes to the same maintained content. Keep source authority, release/environment scope and unresolved conflicts visible at every layer that could otherwise mislead a reader.

Record enough source revision and coverage information in existing metadata or indexes to recognize a stale summary. A valid link is not proof of current content. Reuse a derived result only while its inputs, scope and generation rules still match; a new session alone is not a reason to regenerate it. Recheck the inputs and destination before replacing a generated result so concurrent edits are reconciled.

Verify both navigation and retrieval: required sources are discoverable, affected summaries agree with their sources, and exact identifiers can still be found in detailed content. The knowledge reference defines the bounded reconciliation and search checks. Unavailable sources remain explicit gaps rather than disappearing from coverage.

## 5. Consolidate only within the task's authority

When the user requests consolidation, or correcting duplicate artifacts created during the current task:

1. Inspect both versions, including unique content, human edits, images, notes, scripts, and consumers. Resolve the canonical destination from the user's decision or established project record.
2. Incorporate required changes into that destination and preserve any genuinely required historical inputs with their consumers. Repoint generators, imports, links, and manifests.
3. Verify the destination and preserved content before removing duplicates. Use a temporary recovery copy only as needed during the operation, then clean it after verification.
4. Remove redundant active copies within the authorized scope. Keep a redirect/alias only for a known consumer that cannot be updated; record that it contains no independent content.

Do not conduct project-wide deletion, create a new date-based archive tree, or move unrelated evidence merely because this skill was invoked. Unknown unique content remains unresolved until inspected; age is not grounds for removal.

## 6. Check continuity before delivery

- The result lives at the established path; the final answer links that current entry point.
- Compare the affected tree before and after: justify added files and folders, check retired paths for remaining consumers, and remove task-created redundant staging after validation. No accidental parallel review, knowledge page, root spelling, or date-based copy remains. File count alone does not establish manageability.
- The project root, naming convention, case target version and actual environment version are explicit where relevant. Drafts are labelled and have not silently displaced reviewed material. Promoted drafts were compared with their destination and reconciled there.
- Sources, generated views, indexes, image links, and required snapshot consumers agree. Check only the affected scope.
- When knowledge is affected, check source coverage, summary freshness, authority, graph reachability where applicable, and representative searches using the knowledge reference. Report unresolved gaps; successful link checks alone do not establish these properties.
- Every adopted external reference file has a verified local copy or an existing equivalent in the project tree, with the project naming convention, provenance and consumer links updated. Any unavailable copy is explicitly unresolved.
- Human edits and review progress are accounted for; unresolved migration limits are stated accurately. Do not claim preservation solely from structural validation.
- Any authorized consolidation is complete, including removing temporary duplicates after validation.

Report the canonical path and material additions/removals briefly. This is a decision check, not an automatic filesystem write interceptor; project instructions can make applying it mandatory for artifact work.
