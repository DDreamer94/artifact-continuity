# Worked example: an amended handover

This is a synthetic example. It illustrates the evaluation fixture rather than reporting a real product test.

An agent resumes Lumen R1 work. The project already has `reviews/handover.md`, a networking topic, a knowledge index and evidence run A. An approved amendment adds an offline exception. An R2 proposal also exists, and a new verification file B has the same bytes as A.

## Before

- Accepted R1 decision D-100: retry twice, then `NET-41`.
- Approved amendment D-101: in offline mode, retry three times, then `NET-72`. Online behavior stays the same.
- Unaccepted R2 proposal: five retries in all modes.
- Reviewer comment on stable finding `LC-17`: approval covered the original wording.
- Run A and run B: equal file bytes, different capture events.
- The networking summary used only D-100. The rendering topic is unrelated.

## Apply the skill

Keep `reviews/handover.md` as the editing source. Revise `LC-17` to distinguish online and offline behavior, retaining the comment and making clear that changed wording needs review. The original approval is history; it does not approve the amendment automatically.

Bring the supplied run B file into the existing evidence owner, verify its digest and record its source and capture metadata. Retain both A and B because they document different observations. Equal hashes establish matching bytes, not matching event identity.

Reconcile `knowledge/networking.md` and its entry in `knowledge/index.md`. Include D-101 in the derivation record, preserve the missing historical source gap and keep the R2 proposal's status explicit wherever it is discussed. Leave the unrelated rendering topic and raw sources unchanged.

## After

The maintained entrypoints are still the handover and existing knowledge index. The agent can answer a broad networking question from the topic and find `NET-72` in the detailed source. Both answers retain R1 scope and the accepted-decision baseline.

A second pass with the same inputs should make no file changes. There is no need for a new dated report, duplicate knowledge tree or whole-project snapshot.

Try the [evaluation scenario](../evals/README.md) to inspect these decisions on actual files. See the [validation record](../docs/validation.md) for what was observed in this package's check.

## Try it in a temporary project

### Copy the sample

Install and [confirm activation](../README.md#2-confirm-activation) first. From a full checkout of this repository, run the following in a terminal with Python 3. A managed skill installation may omit the examples and fixtures; use a separate reference checkout in that case.

```sh
python3 - <<'PY'
import shutil
import tempfile
from pathlib import Path

checkout = Path.cwd()
assert (checkout / 'evals/input/README.md').is_file(), 'Run from the repository checkout.'
demo = Path(tempfile.mkdtemp(prefix='artifact-continuity-demo-'))
shutil.copytree(checkout / 'evals/input', demo / 'project')
shutil.copytree(checkout / 'evals/inbox', demo / 'inbox')
print('Open this project in your agent:', demo / 'project')
print('Allow read access to this supplied inbox:', demo / 'inbox')
PY
```

Open the printed `project` directory as the agent's workspace. Give it write access there and read access to the sibling `inbox` and installed skill. Keep the original repository fixture unchanged.

### Apply the amendment

Send this prompt in that workspace. It uses Codex's explicit skill syntax; use your host's equivalent if applicable.

```text
Use $artifact-continuity to update the existing Lumen R1 handover and knowledge
notes for approved amendment D-101. Include the new verification observation B:
build R1.0, reconnect state, captured 2026-10-22T15:00:00Z; its supplied file is
in the sibling inbox/run-b.txt. Make this ready for the next reviewer and
report the current entrypoints. Work only in this project; the inbox is
read-only. No external services are needed.
```

Inspect the files against [Before](#before) and [After](#after) above:

- `reviews/handover.md` keeps `LC-17` and the reviewer comment, with the changed wording awaiting review.
- `knowledge/networking.md` and `knowledge/index.md` distinguish accepted R1 online/offline rules from the R2 proposal; the missing R0 source stays visible.
- The evidence manifest identifies both A and B, with B's import provenance and digest. Equal bytes remain two observation events.
- Raw sources, the rendering topic and observation A retain their bytes. The existing project has 11 files; one new observation normally makes 12. That is justified evidence growth, without another handover or knowledge-tree copy.

The supplied result text is synthetic and does not prove the amended product behavior passed a real test. Inspect its stated limitations as well as its file placement.

### Check the repeat

After inspecting the first result, open a terminal in the printed **project** directory and run this block. It records a baseline beside the project. Git internals are excluded if your host created a repository.

```sh
python3 - <<'PY'
import hashlib
import json
from pathlib import Path

project = Path.cwd()
assert (project / 'reviews/handover.md').is_file(), 'Run from the temporary project.'
paths = [p for p in project.rglob('*') if '.git' not in p.relative_to(project).parts]
state = {
    'files': {str(p.relative_to(project)): {
        'sha256': hashlib.sha256(p.read_bytes()).hexdigest(),
        'mtime_ns': p.stat().st_mtime_ns,
    } for p in sorted(paths) if p.is_file()},
    'directories': sorted(str(p.relative_to(project)) for p in paths if p.is_dir()),
}
baseline = project.parent / 'repeat-baseline.json'
if not baseline.exists():
    baseline.write_text(json.dumps(state, indent=2) + '\n')
    print('Baseline saved. Ask the agent to repeat, then run this block again.')
else:
    assert json.loads(baseline.read_text()) == state, 'Changes detected; inspect the repeat before accepting it.'
    print('No file-content, path, modification-time or directory changes detected.')
PY
```

Now send:

```text
Use $artifact-continuity to repeat the completed Lumen maintenance request
with the same inputs. Report whether any further write is needed and keep
unresolved gaps explicit.
```

Run the same terminal block again. A passing comparison verifies the observable repeat state, while the earlier content review checks preservation and meaning. If it fails, inspect what changed; keep the original baseline for that comparison. A changed input or newly supplied source calls for reconciliation rather than an automatic no-change result.

When finished, remove this disposable demo directory through your normal file workflow. It contains the copied project, inbox and one comparison baseline; no generated demo files belong in the skill repository. For the separate draft-consolidation and interrupted-export scenarios, use the existing [Atlas fixtures](../evals/README.md#atlas-tree-lifecycle-and-blocked-regeneration).
