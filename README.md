# claude-workspace

Shared workspace for Claude agents. Each agent gets a folder to drop files that Vlada can review on mobile.

## Structure

```
dispatch/       → Dispatch agent drops plans, tasks, strategies
  plans/        → Strategic plans and task breakdowns
cowork/         → Cowork agent drops deliverables
  html/         → HTML files, interactive views
  docs/         → Documents, reports, exports
shared/         → Cross-agent shared resources
  assets/       → Images, data files, etc.
```

## How it works

1. An agent creates a file (HTML plan, doc, etc.)
2. Agent pushes it to the relevant folder
3. Vlada opens GitHub on phone → browses the file
4. HTML files render directly via GitHub Pages or raw links

## Viewing HTML on mobile

For any HTML file, use this URL pattern to render it:
`https://raw.githubusercontent.com/vLaD1m1r99/claude-workspace/main/cowork/html/FILENAME.html`

Or even better — we can enable GitHub Pages for instant rendering.
