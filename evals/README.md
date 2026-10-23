# Contained continuity scenarios

These exercises cover amendment handling, project-tree consolidation and blocked regeneration. Keep run outputs and evaluator inventories in temporary workspaces, outside this repository and outside the project being evaluated. A new test run does not need another maintained report folder here.

For a first use rather than a comparative evaluation, follow the [runnable Lumen walkthrough](../examples/review-amendment.md#try-it-in-a-temporary-project), which includes sample setup, explicit invocation and a repeat-state check. The neutral tasks below remain suitable for control and skill-enabled conditions.

## Lumen: amendment and knowledge continuity

The `input/` directory is a synthetic project. `inbox/run-b.txt` is a separate supplied input. Neither represents a real product or execution result.

Copy `input/` into a fresh temporary project and `inbox/` beside it. Keep the original fixture unchanged. Give an agent the task below and access only to its temporary project, read-only inbox, and the skill when evaluating the skill-enabled condition. No network or services are required.

### Task

> Update the existing Lumen R1 handover and knowledge notes for approved amendment D-101. Include the new verification observation B: build R1.0, reconnect state, captured 2026-10-22T15:00:00Z; the supplied file is in the sibling inbox/run-b.txt. Make this ready for the next reviewer and report the current entrypoints. Then repeat the same maintenance request and report whether another write was needed. Work only in the assigned project; the sibling inbox is read-only. No network or services are available.

For a control run, provide only the task and raw fixtures. For a skill-enabled run, use a fresh copy and additionally provide `SKILL.md` and its references. Keep the task otherwise the same. Record the model/runtime and conditions; do not infer a general advantage from one sample.

### Inspect the result

- The existing handover is revised in place, with finding `LC-17`, its comment and the original approval's limited scope preserved.
- R1 online behavior remains two retries and `NET-41`; the accepted offline amendment is three retries and `NET-72`. The R2 proposal is not promoted into R1 policy.
- Source bytes and unrelated rendering content are unchanged.
- Run B is preserved inside the project with import provenance and a verified digest. Both A and B remain distinct observations with their capture metadata.
- Networking and its overview reflect the amendment and the source set actually reconciled. The stable topic ID, reviewer note and missing historical-source gap survive.
- Broad topic navigation, exact identifier lookup and alias lookup lead to the right scope and source.
- Hashes and modification times do not change on a repeat pass with the same inputs.

Inspect meaning and actual files, including evidence metadata; matching headings or a validator pass is insufficient. Record partial results and unresolved gaps honestly. If a control already succeeds, report that as preservation evidence rather than inventing a failure or improvement.

The scenario checks document maintenance in a small filesystem collection. It does not test automatic skill discovery, a live WeKnora integration, model speed or large-corpus retrieval quality.

## Atlas: tree lifecycle and blocked regeneration

[tree-lifecycle.json](tree-lifecycle.json) holds two fixtures as relative-path/content mappings, with their user requests in execution order. Expand them into fresh temporary directories; the embedded Python renderers use only the standard library. From the repository root:

```sh
python3 - <<'PY'
import json, tempfile
from pathlib import Path
fixture = json.loads(Path('evals/tree-lifecycle.json').read_text())
root = Path(tempfile.mkdtemp(prefix='continuity-atlas-'))
for name, scenario in fixture['scenarios'].items():
    for relative, content in scenario['files'].items():
        path = root / name / relative
        path.parent.mkdir(parents=True, exist_ok=True)
        path.write_text(content)
print(root)
PY
```

Give each evaluating agent only its assigned project, the task strings and the skill under test. Keep this inspection checklist and other runs' outputs out of its brief. Capture file contents, paths, SHA-256 hashes, sizes, modification times and directory lists before work and after each phase. Store these inventories outside the evaluated project. Compare old and revised instructions in independent fresh contexts when assessing a revision; record a successful baseline honestly.

### Tree scenario

The first phase requests an ordinary amendment; the second authorizes draft consolidation; the third repeats the completed request. Inspect these outcomes:

- The ordinary amendment preserves established source/export paths and does not sweep the old drafts before consolidation is requested.
- Decision A-11 changes the date to 15 December 2026; the accepted USD 1,200 budget survives the stale draft's USD 1,000 value.
- BR-5, Jo's packing note, Al's HTML-only loading-dock note, Lee's eight-unit audit note and Sam's finance note survive in the reconciled source. Kim's old approval does not automatically approve changed wording.
- The renderer consumes the canonical source, its existing HTML agrees with that source, and the generation baseline is identifiable in existing history or metadata. No per-attempt sidecar is needed.
- Consolidation retires exactly the two redundant drafts and fixes their consumers. The frozen comparison baseline, its consumer, accepted sources, two equal-byte observations and separate `Other/` project retain their bytes.
- The complete tree changes from 16 to 14 files with no new maintained paths. The repeat changes neither file content nor modification times. Inspect directories and scratch residue too; file count alone is insufficient.

### Blocked-export scenario

The renderer can truncate its destination before discovering a missing approved logo. Inspect whether the agent stages safely or detects the dependency before calling it, keeps the existing valid HTML intact, reports its stale date accurately and preserves the input brief. No replacement logo or incomplete export should be published. A retry with unchanged inputs should leave no extra attempts in the tree. A concise status in existing metadata or the response is sufficient; new reports are unnecessary.

These fixtures exercise local artifact decisions. They do not simulate concurrent writers, test browser rendering, verify automatic skill selection or cover every retention policy. Human review of preserved meaning remains part of evaluation.
