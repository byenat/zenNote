# ZenNote - Daily Note Standalone App PRD

## Positioning
- ZenNote is a dedicated daily journaling/note-taking app focused on efficient capture and structured organization.
- Managed in parallel with `yourPXO`. While `yourPXO` already embeds ZenNote capabilities, ZenNote serves users who prefer a dedicated writing/logging workflow.
- Integrates `byenatOS` to map notes into HiNATA and drive continuous PSP personalization.
- With the same account across `yourPXO`, `ZenRead`, and `ZenNote`, a single HiNATA and PSP is shared by default (account-level). App-level Overlay is optional.

## Target Users
- Daily writers, reviewers, planners
- Users needing Markdown, STT, and templates

## Core Capabilities
1) Fast Capture
- Rich text/Markdown, speech-to-text, images/files
- Templates, snippets, backlinks, Today/Week views

2) Intelligent Organization
- Topic extraction, sentiment analysis, keywords & tag suggestion
- Timeline, project/area views, review & retrospective

3) HiNATA Mapping (byenatOS)
- Rule: NoteTitle/KeySentence → `Highlight`; FullNote/Details → `Note`
- Metadata: `Source=zennote`, `Tag=[journal, source]`, `Access=Private` (default)
- Local operators: summarization, highlight suggestion, entity extraction, embeddings, validation

4) Retrieval & Review
- Full-text search, filter by tag/sentiment/topic, periodic review

## Integration & Sharing Policy
- Account-level Sharing (default): Multiple Apps share one HiNATA and PSP under the same account.
- App-level Overlay (optional): ZenNote-specific style/voice, summary length, structural formatting.
- PSP Scope: `Scope=account` (default) or `Scope=app` (Account PSP + ZenNote Overlay).

## Key Flows (Overview)
1) Create/edit journal → generate/update HiNATA → local enhancement → validation → persist (account-level)
2) Weekly/monthly review → derive summaries → QnA → archive as HiNATA (Q→Highlight, A→Note) → PSP iteration

## Non-functional
- Privacy: local-first; stateless calls to `byenatOS` (no user identifier)
- Performance: create < 200ms; search < 300ms; offline-capable

## Relation to yourPXO
- `yourPXO` embeds ZenNote (Daily Note). ZenNote is a professional writing app parallel to `yourPXO`, sharing the same HiNATA/PSP under the same account for a multi-input workspace.

## Parallel Positioning & Choice Guide
- **All-In-One workflow**: Choose `yourPXO` to get unified capture, reading, and writing in one app.
- **Focused Daily Note**: Choose `ZenNote` to keep journaling/review workflows minimal and distraction-free.
- **Seamless switching**: With the same account, `yourPXO`, `ZenNote`, and `ZenRead` share a single HiNATA and PSP (account-level) by default; switch anytime without import/export.
- **App-level Overlay**: Optionally enable `ZenNote` writing-style Overlay without breaking account-level PSP continuity.

## Cross-App Seamlessness (Shared HiNATA/PSP)
- **Login & sharing**: When logging into both `ZenNote` and `yourPXO` with the same account, all HiNATA and PSP accumulated in `ZenNote` automatically become available in `yourPXO`.
- **Scope policy**: Default `Scope=Account`. With `Scope=App`, compose ZenNote Overlay on top of the account PSP.
- **Consistency**: Highlights and notes created across apps follow the mapping rules so retrieval, review, and AI context stay consistent.

## AI Chatbot Personalization (via PSP)
- `ZenNote` writing preferences, templates, and structure feed into the shared PSP; AI chats in `yourPXO` or other `byenatOS` apps inherit these preferences by default.
- When App-level Overlay is enabled, AI uses "Account PSP + ZenNote Overlay" for reasoning and responses.
