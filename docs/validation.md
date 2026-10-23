# Validation record

Date: 23 October 2026.

This standalone extraction retains the existing skill workflow and two references. Its instruction change generalizes one project-specific authority paragraph. The checks below concern that portable package, not a new retrieval engine or a deployed service.

## Behavioral exercise

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

## Package checks

The skill-creator structural validator passed. The existing personal source package and installed shared entrypoint remained unchanged during extraction. The two references and UI metadata match the starting package byte-for-byte; only the documented authority paragraph differs in `SKILL.md`.

The standalone Git distribution is also checked for local Markdown links, whitespace, and unsafe staged paths/content before publication. The original private repository, local research inputs, runtime configuration and credentials are outside that distribution.

## Limits

This exercise did not test automatic skill discovery, other agent hosts, large-corpus search quality, production use, model speed, a live WeKnora deployment, native WeKnora skill import or any API round trip. The [WeKnora pairing](weknora.md) remains a proposal. Re-run relevant checks when the skill's behavior or integration changes.
