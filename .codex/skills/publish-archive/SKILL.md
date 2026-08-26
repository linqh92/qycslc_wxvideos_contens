---
name: publish-archive
description: Archive actually published WeChat Video Account content into the historical knowledge base only after the user explicitly requests archiving. Use only when both publication and an archive/write instruction are explicit.
---

# WeChat Video Account Publish Archive

Only archive content that has actually been published and has an explicit archive instruction. Write it into the formal historical knowledge base and complete the required content-asset feedback flow.

## Trigger Conditions

Both conditions are required:

1. The user explicitly confirms that the content has been published or the update is complete.
2. The user explicitly requests archiving, writing to the knowledge base, or saving to historical content.

Both are mandatory. If the user only says “已发布”, prepare only a uniquely identifiable archive preview and do not write any file. If the actual published information cannot uniquely determine the title, body, or publication date, ask for clarification first. Never guess or overwrite existing records.

## Archive Execution

Before archiving, fully read and strictly follow `内容库/00-首页与维护规则/历史内容归档规范.md`. This file is the single source of truth for path, filename, Frontmatter, body structure, and completion checks. This Skill does not redefine the archive schema.

When archiving:

1. Check the target directory for same-name or likely duplicate notes. If a conflict exists, stop and report it.
2. Write only the actually used title, body, and actual publication date. Do not save alternative titles, drafting process, or unpublished information.
3. Update the corresponding topic-pool entry to `已发布`, while preserving its source and linked historical content, to prevent duplicate recommendations.
4. Update indexes, content map, duplicate checks, and content-gap analysis. Do not force statistical rewrites when no new facts are available.

## Feedback to Idea Library

After archiving, extract 1–2 non-duplicate follow-up questions from the published content. Create one new `历史延展` idea note for each question. If real comments, consultations, or service-delivery feedback exist, create separate idea notes for each and link them to this historical content.

Mark all feedback entries as `待分析` first. They must not directly become the next formal topic. End the workflow here; do not automatically generate the next batch of topics or copy.
