# Proposed WeKnora pairing

Status: design proposal; no connector or live integration has been built or tested.

This guide is based on the [pinned source review](provenance.md). At that revision, WeKnora describes document ingestion, retrieval, agent tools and generated Wiki pages. Those capabilities suggest a place to publish searchable project knowledge; they do not establish that this skill is compatible with a particular deployed version.

## Keep ownership explicit

| Concern | Proposed owner |
| --- | --- |
| Original project files, accepted decisions and review comments | Existing project repository or document owner |
| Artifact identity, source authority and reconciliation decisions | Agent applying Artifact Continuity and project instructions |
| Search index and optional generated Wiki | Selected WeKnora knowledge base |
| Project-to-knowledge-base identity mapping and sync state | One receipt in the project's existing metadata owner |

For a first pairing, keep the project files as the editing source. Publish selected knowledge to WeKnora as a derived view. This keeps generated Wiki edits from silently replacing accepted project policy. If a project later chooses WeKnora as an editing source, define that authority and the return path explicitly before enabling writes in both directions.

## Suggested handoff

1. Select the intended WeKnora deployment, workspace and knowledge base using a bounded read-only check. Verify the installed version, access and supported interface before relying on its import or update behavior.
2. Reconcile the project artifact first. Preserve source documents, review comments and separate evidence observations. Choose the smallest useful source set for retrieval; do not upload an entire workspace by default.
3. Record a stable project identity and canonical path for each selected source, its revision or digest, scope, authority, and any unresolved dependency. After publishing through a supported interface, record the returned remote document identity and the exact revision published.
4. On the next change, use that mapping to find the corresponding remote item. Reconcile source-set additions and removals as well as changed bytes. A path rename alone should not accidentally create a second independent document.
5. Let the selected platform perform its supported indexing and Wiki work. Check the actual indexed revision, source citations and relevant output; a successful upload does not establish retrieval freshness.
6. Treat returned summaries and Wiki edits as candidate input when updating project files. Compare the recorded baseline, current project source and returned text. Preserve human edits and resolve conflicts through the project's authority rules.

These are workflow requirements, not verified WeKnora API fields or endpoint names. Before implementing a connector, map them to the deployed version's documented interfaces. Some metadata may need to stay in the project receipt if the remote interface cannot represent it.

## Example mapping

The following is illustrative project metadata, not a WeKnora request body:

```yaml
artifact_id: lumen-networking-r1
canonical_path: knowledge/networking.md
scope: Lumen R1
authority: accepted decisions D-100 and D-101
source_revisions:
  sources/r1-policy.md: D-100
  sources/r1-amendment.md: D-101
remote_identity: record the identity returned by the selected deployment
published_revision: record the exact project revision or content digest sent
coverage_gaps:
  - sources/legacy-r0.md is unavailable
```

Reuse an existing project index or manifest for this information. The example is not a requirement to create a new sidecar file for every artifact.

## Verify a first integration

Use a disposable knowledge base and a small non-sensitive fixture. Check a broad topic question, the exact identifier `NET-72`, and the alias `reconnect`. Inspect the sources and release scope returned, not merely whether a plausible answer appears.

Then add an accepted amendment without modifying the old source. Verify that the affected summary and index reconcile it, an unaccepted R2 proposal does not become R1 authority, and an unavailable historical source remains an explicit gap. A repeat sync should not create another remote item for the same identity. Two separate verification observations with identical bytes must remain distinguishable if they are in the selected source set.

Also check a remote edit made after export, source relocation or removal, and an interrupted publish. A retry must compare the current local and remote state before writing. Do not enable deletion or automatic return writes until their version-specific behavior and recovery path have been verified.

This checklist defines what a future connector needs to demonstrate. None of these live checks has been performed for this package.
