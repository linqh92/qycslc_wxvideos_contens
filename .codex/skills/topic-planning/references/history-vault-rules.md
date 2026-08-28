# Historical Content Vault Read Rules

## Location

Repository root: `内容库`

Historical content directory: `01-历史内容/YYYY/YYYY-MM`

## Pre-Topic Read Rules

1. Every time the user requests topic ideas, re-list all Markdown files currently stored under `01-历史内容`.

   - Do not reuse a file list from a previous run.
   - Treat the current repository state as authoritative.

2. Perform a lightweight scan of all historical notes.

   Read and parse these metadata fields first:

   - `title`
   - `publish_date`
   - `business_line`
   - `theme`
   - `content_type`
   - `status`

   Only read the following fields when they are needed for candidate filtering, duplicate checks, or coverage analysis:

   - `audience`
   - `pain_scene`
   - `content_goal`

   Do not read full note bodies during the global scan by default.

3. After the metadata scan is complete, read historical note bodies in the following order.

   ### 3.1 Recent Content

   - Read the full body of the 10 most recent published historical notes.
   - If fewer than 10 published notes exist, read all available recent published notes.

   ### 3.2 Candidate-Relevant Content

   For each preliminary topic candidate, identify historical notes with strong relevance.

   Prioritize notes that match one or more of the following:

   - same or highly similar `theme`
   - same or highly similar `pain_scene`
   - same `business_line`
   - highly similar title or core-question semantics
   - same customer scenario
   - same business action
   - same service opportunity

   Read the highest-relevance matches first.

   By default, read no more than 10 relevant historical note bodies.

   ### 3.3 Total Body Read Limit

   For a normal topic-generation task, keep the total number of historical note bodies read within 10–20 notes.

   Expand beyond this limit only when at least one of the following applies:

   - duplicate risk cannot be judged reliably
   - many historical notes exist under the same topic
   - it is necessary to distinguish between already-covered and genuinely new angles
   - the user explicitly requests a full historical review or deep duplicate analysis

4. Read supporting materials by priority.

   Do not load every supporting file in full by default.

   ### Required

   Always read:

   - 账号基本定位
   - 固定选项库
   - 待发布选题

   ### Read the Latest Version

   Prefer the latest available version of:

   - 内容维护说明
   - 内容缺口分析
   - 重复选题检查

   ### Read On Demand

   Read only when relevant to the current task:

   - 灵感库目录
   - specific notes inside 灵感库
   - related 业务选题池

   For 灵感库:

   - read the directory or index first
   - only read specific note bodies after a relevant lead is identified

   For 业务选题池:

   - only read sections related to the current `business_line` or current topic direction
   - do not scan unrelated business lines by default

5. Use the following read order for topic-generation tasks:

   1. current full historical file list
   2. metadata of all historical notes
   3. 账号基本定位, 固定选项库, 待发布选题
   4. full body of the 10 most recent historical notes
   5. full bodies of high-relevance historical notes
   6. 内容缺口分析, 重复选题检查, and other relevant supporting materials
   7. matched 灵感库 notes or related 业务选题池 content, only when needed

6. If a historical note conflicts with an index, review file, content map, gap-analysis file, or duplicate-check file:

   - treat the current historical note itself as the source of truth
   - use reviews, maps, gap analysis, and duplicate checks only as navigation and decision-support material

7. If the historical vault cannot be read or parsed reliably:

   - explicitly state the blocking issue
   - do not output formal topic recommendations

## Usage Boundaries

- `01-历史内容` is the sole source of truth for published-content history, duplicate checks, and content-coverage judgments.
- A full historical scan does not mean reading every full note body.
- Use metadata for global screening first, then read only high-value note bodies.
- 灵感库 and 业务选题池 may provide candidate leads, but they must never replace a fresh scan of `01-历史内容`.
- Review files, content maps, gap analyses, and duplicate-check files must never override the current historical notes.
- Historical content does not prove that a policy, tax rate, deadline, penalty, platform rule, or operating procedure is still current.
- When a topic depends on current policy, tax rates, deadlines, penalties, platform rules, or procedures, verify the latest official source separately.
- Never store passwords, cookies, verification codes, or other login credentials in the content vault.
