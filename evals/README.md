# Contained continuity scenario

The `input/` directory is a synthetic project. `inbox/run-b.txt` is a separate supplied input. Neither represents a real product or execution result.

Copy `input/` into a fresh temporary project and `inbox/` beside it. Keep the original fixture unchanged. Give an agent the task below and access only to its temporary project, read-only inbox, and the skill when evaluating the skill-enabled condition. No network or services are required.

## Task

> Update the existing Lumen R1 handover and knowledge notes for approved amendment D-101. Include the new verification observation B: build R1.0, reconnect state, captured 2026-10-22T15:00:00Z; the supplied file is in the sibling inbox/run-b.txt. Make this ready for the next reviewer and report the current entrypoints. Then repeat the same maintenance request and report whether another write was needed. Work only in the assigned project; the sibling inbox is read-only. No network or services are available.

For a control run, provide only the task and raw fixtures. For a skill-enabled run, use a fresh copy and additionally provide `SKILL.md` and its references. Keep the task otherwise the same. Record the model/runtime and conditions; do not infer a general advantage from one sample.

## Inspect the result

- The existing handover is revised in place, with finding `LC-17`, its comment and the original approval's limited scope preserved.
- R1 online behavior remains two retries and `NET-41`; the accepted offline amendment is three retries and `NET-72`. The R2 proposal is not promoted into R1 policy.
- Source bytes and unrelated rendering content are unchanged.
- Run B is preserved inside the project with import provenance and a verified digest. Both A and B remain distinct observations with their capture metadata.
- Networking and its overview reflect the amendment and the source set actually reconciled. The stable topic ID, reviewer note and missing historical-source gap survive.
- Broad topic navigation, exact identifier lookup and alias lookup lead to the right scope and source.
- Hashes and modification times do not change on a repeat pass with the same inputs.

Inspect meaning and actual files, including evidence metadata; matching headings or a validator pass is insufficient. Record partial results and unresolved gaps honestly. If a control already succeeds, report that as preservation evidence rather than inventing a failure or improvement.

The scenario checks document maintenance in a small filesystem collection. It does not test automatic skill discovery, a live WeKnora integration, model speed or large-corpus retrieval quality.
