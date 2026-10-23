# Authorship and design provenance

Artifact Continuity is created and maintained by [DDreamer94](https://github.com/DDreamer94), with AI-assisted development. It packages the owner's existing artifact-management workflow as a portable agent skill.

Suggested description when sharing it:

> I developed Artifact Continuity, an agent skill for maintaining reports, evidence and knowledge across sessions. Its knowledge-maintenance guidance is informed by Tencent WeKnora's work on Wiki organization, identity reuse and freshness checks.

This describes ownership of the tool while making the conceptual influence visible. It does not claim that all underlying ideas are novel or that the tool was developed by Tencent.

## WeKnora acknowledgment

The existing skill already recorded conceptual influence from [Tencent WeKnora at commit `8cb53fdbc58e4c15aafdba973d65742551e4c9cd`](https://github.com/Tencent/WeKnora/tree/8cb53fdbc58e4c15aafdba973d65742551e4c9cd). This extraction preserves that acknowledgment in the [knowledge-maintenance reference](../references/knowledge-maintenance.md#design-provenance) and makes it visible in the README.

| Reviewed source | Relevant idea |
| --- | --- |
| [Wiki prompts](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/agent/prompts_wiki.go) | Reuse established identities; aliases and resemblance alone do not prove identity. |
| [Knowledge-base profiles](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/application/service/knowledgebase_profile.go) | Use aggregate descriptions and topics to support collection discovery. |
| [Summary refresh](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/application/service/knowledge_summary_refresh.go) | Detect source changes before accepting a generated summary. |
| [Wiki lint](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/internal/application/service/wiki_lint.go) | Check structural quality separately from whether claims are correct. |

These are conceptual adaptations. No WeKnora implementation files or runtime are distributed here. Project authority, reviewer preservation and distinct evidence-event identity are the skill's own operating requirements. This package is independently maintained and is not an official WeKnora product or endorsed integration.

The pinned WeKnora [LICENSE](https://github.com/Tencent/WeKnora/blob/8cb53fdbc58e4c15aafdba973d65742551e4c9cd/LICENSE) identifies MIT terms for the project and separate terms for third-party components. Its license should not be flattened into a claim that every dependency has the same terms. If implementation code, prompts or substantial documentation are incorporated in a future change, review and retain the applicable copyright, license and notices for the material actually included.

## Extraction record

The starting personal package was version `2026-10-10.1`. The standalone package preserves its workflow and two references, generalizes one project-specific authority paragraph, and adds repository documentation, examples and evaluation materials. It does not import the previous private repository's history or unrelated packages.

[Origin hashes](../provenance/origin.json) record the four starting package files. [Upstream receipts](../provenance/weknora.json) record the reviewed public sources, retrieval date and byte digests. Exact research copies are retained locally under the ignored `.local/evidence/weknora/` directory; they are not part of the Git distribution. Public links and digests identify those inputs for later review without bundling the upstream implementation.

The pairing guide is an architectural proposal based on that pinned source review. No WeKnora deployment, API session, native skill import or end-to-end round trip was tested.
