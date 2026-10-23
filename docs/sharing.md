# Share Artifact Continuity

**Does every AI retry leave you with another `final-v3.md`?**

Artifact Continuity gives file-capable AI agents instructions to revise existing work, preserve human edits and required history, and reconcile redundant drafts within the scope you authorize.

Start with people who already use agents for recurring reports, project briefs, QA handovers or knowledge pages. Invite them to try one ongoing document and report what was preserved, lost or duplicated. Five useful trial reports are a sensible first target; no adoption or growth results are claimed here.

## Ready-to-share media

- [GitHub social preview PNG](../assets/sharing/preview.png): 1280 × 640, solid background. [Editable SVG source](../assets/sharing/preview.svg).
- [40-second demonstration MP4](../assets/sharing/demo.mp4): 1280 × 720, captioned, no audio. Suitable for uploading with a launch post.
- [Animated demonstration GIF](../assets/sharing/demo.gif): the same five scenes for GitHub and other image embeds.

The diagram uses an original, restrained document motif, large type and a readable before/after file tree. No third-party logos or customer endorsements appear. The media are covered by this repository's MIT license. Alt text: “Atlas draft copies are reconciled into brief.md; useful human notes and the required release baseline survive.”

Upload the PNG through the repository's **Settings → Social preview → Edit → Upload an image**. GitHub recommends 1280 × 640 and an image below 1 MB. Committing an image alone does not set this repository setting. [GitHub's instructions](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview)

## English launch post

Does every AI retry leave you with another `final-v3.md`?

I've open-sourced **Artifact Continuity**, an agent skill developed with AI assistance for people who repeatedly revise reports, project briefs, QA handovers and knowledge pages.

It guides your agent to continue from the current file, preserve human edits, reconcile useful changes and retire checked redundant drafts. Required history stays.

The repository includes Codex setup, a runnable example and documented synthetic checks. The attached 40-second walkthrough presents recorded results from a synthetic run.

Try it on one ongoing document: **did your edits survive, and is the current version easier to find?**

https://github.com/DDreamer94/artifact-continuity

Feedback and small, sanitized examples are welcome.

## Short post for X

Does every AI retry leave another final-v3.md?

I built Artifact Continuity: an agent skill for preserving human edits and reconciling redundant drafts. Codex setup + runnable example included.

Try one ongoing document:
https://github.com/DDreamer94/artifact-continuity

## 中文发布文案

**AI 每改一次，项目里就多一个「最终版」？**

报告改了几轮，文件夹里留下 `final.md`、`final-v2.md`、`final-final.md`。下次继续时，哪个才是当前版本？你手动补充的意见还在吗？

我把自己在 AI 协作中整理的方法做成了开源技能 **Artifact Continuity**，开发过程有 AI 协助。

它为能读写项目文件的 AI agent 提供工作指引：沿用当前文档、合并有用的修改、保留人工批注和必要历史，并在核对后清理授权范围内的冗余草稿。不同次执行的证据，仍然分别保留。

适合经常用 AI 迭代研究报告、项目说明、测试交接和知识文档的人。仓库提供 Codex 安装说明、可动手操作的示例，以及测试记录。视频是一次合成示例实际运行结果的 40 秒浓缩展示。

先拿一份持续修改的文档试试：**你的修改保住了吗？当前版本更容易找到了吗？**

GitHub：https://github.com/DDreamer94/artifact-continuity

欢迎反馈，也欢迎提供已去除敏感信息的小例子。

#AI工具 #开源项目 #Codex #工作流 #知识管理

## Demonstration and evidence

This is a **condensed presentation of recorded results**, not a real-time screen recording, simulated terminal session or customer case study. Scene durations are editorial choices, not execution timings. Instructions and fixture: [`cbc67ed`](https://github.com/DDreamer94/artifact-continuity/tree/cbc67ed78552609c1b912aaafd3fb4024017ef56), [Atlas tree scenario](../evals/tree-lifecycle.json), fresh run on 23 October 2026.

| Time | What is shown | What the recorded run established |
| --- | --- | --- |
| 0–7 s | Four brief files and scattered edits | The maintained source, two redundant drafts and a required comparison baseline all existed. |
| 7–14 s | The consolidation request and its scope | Accepted sources controlled the date and budget; the separate project remained outside scope. |
| 14–24 s | Preserved notes and review boundary | Jo, Al, Lee and Sam's notes survived in the current brief and HTML. Kim's original approval did not silently cover the amended date. |
| 24–32 s | Before/after tree | The complete fixture changed from 16 files to 14. Only two verified redundant drafts were retired; their consumers were repaired. |
| 32–40 s | Unchanged repeat and invitation | File paths, contents and nanosecond modification times were identical on repeat; no generator rerun occurred. |

The retained budget was USD 1,200; the accepted date became 15 December 2026. The baseline, comparison, original sources, renderer, two separate equal-byte evidence observations and `Other/` remained unchanged. These observed results are limited to this synthetic run. A smaller file count alone is not success, and no general time, token or performance savings are claimed. The [validation guide](validation.md) explains the wider checks and limitations.

The media intentionally show selected brief files rather than every file in the fixture. The editable social SVG is the maintained source for its PNG. The MP4 and GIF share the same five captioned scenes. Revise these existing assets when the example changes; do not add a new media set for each retry.

## Distribution and follow-up

1. Use the [GitHub repository](https://github.com/DDreamer94/artifact-continuity) as the main entry point. Its README features the share graphic, expandable demonstration, installation instructions and runnable example.
2. Invite reports through [GitHub issues](https://github.com/DDreamer94/artifact-continuity/issues). Ask for the host and revision, a sanitized before/after example, what needed to survive and what actually happened. Follow up with one concrete improvement or useful case rather than repeatedly reposting the same announcement.
3. For skill discovery, the [skills CLI installation route](../README.md#install-and-use) was exercised with version 1.7.4 in a disposable Codex project. According to [skills.sh's FAQ](https://www.skills.sh/docs/faq), its leaderboard surfaces skills through genuine CLI installations and aggregate installation telemetry. This repository does not claim a verified listing, ranking or cross-host compatibility.
4. The English, short and Chinese posts above are reusable drafts for any future expansion to LinkedIn, X, 小红书 or appropriate community showcase areas. Choose one relevant example and check that community's current posting rules before publishing.

The current launch scope is **GitHub only**. External posts and community submissions are not part of this launch. The custom social preview must be configured separately from committing the PNG, using the instructions above. Keep any future publication links in this section rather than opening a separate campaign-status document.

## Attribution

Created and maintained by DDreamer94, with AI-assisted development. Knowledge-maintenance concepts were informed by [Tencent WeKnora](https://github.com/Tencent/WeKnora); see [credits and provenance](provenance.md). This is an independent project. The suggested WeKnora pairing remains a proposal, and no endorsement or implemented integration is claimed.
