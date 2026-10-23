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
