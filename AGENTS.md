# Agent Guide — claude-workspace

This is the shared repo where all Claude agents drop files for Vlada to review (usually on phone).

## Repo URL

```
https://github.com/vLaD1m1r99/claude-workspace
```

## GitHub Pages (for viewing HTML on mobile)

```
https://vlad1m1r99.github.io/claude-workspace/{project}/{path}
```

Example: `https://vlad1m1r99.github.io/claude-workspace/smote-website/html/homepage-v1.html`

## Authentication

Use this token for git push (passed by dispatch):

```
git remote set-url origin https://{TOKEN}@github.com/vLaD1m1r99/claude-workspace.git
```

Git config:
```
git config user.email "vlada@smote.co"
git config user.name "Claude Agents"
```

## Repo structure

```
claude-workspace/
  AGENTS.md            ← you are here
  _template/           ← copy this to start a new project
    plans/
    html/
    docs/
    assets/
    README.md
  {project-name}/      ← one folder per project
    plans/             ← strategy, task breakdowns, roadmaps
    html/              ← interactive HTML views, previews, dashboards
    docs/              ← reports, exports, written documents
    assets/            ← images, data files, shared resources
    README.md          ← project summary (update this when you add files!)
```

## Rules for agents

### 1. Creating a new project

```bash
cp -r _template {project-name}
# Edit {project-name}/README.md with project details
```

### 2. Adding files to an existing project

- Put the file in the right subfolder (plans/, html/, docs/, assets/)
- **Update the project README.md** — add your file to the Files table so Vlada can see what's new
- Commit message format: `{project}: {what you did}` (e.g., `smote-website: add homepage wireframe v2`)

### 3. HTML files (important!)

HTML files are the main way Vlada reviews work on mobile. Make them:
- **Mobile-first** — viewport meta tag, responsive, touch-friendly
- **Self-contained** — inline all CSS/JS, no external dependencies if possible
- **Dark theme preferred** — `background: #0d1117; color: #e6edf3;` (GitHub dark palette)
- **Include a title and timestamp** so Vlada knows what they're looking at

Minimal boilerplate:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{Project} — {Description}</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: -apple-system, system-ui, sans-serif;
      background: #0d1117; color: #e6edf3;
      padding: 20px; line-height: 1.6;
    }
    .container { max-width: 600px; margin: 0 auto; }
    h1 { font-size: 1.4em; margin-bottom: 8px; }
    h2 { font-size: 1.1em; color: #58a6ff; margin: 20px 0 8px; }
    .meta { color: #8b949e; font-size: 0.85em; margin-bottom: 20px; }
    .card { background: #161b22; border: 1px solid #30363d; border-radius: 8px; padding: 16px; margin-bottom: 12px; }
    a { color: #58a6ff; }
  </style>
</head>
<body>
  <div class="container">
    <h1>{Title}</h1>
    <p class="meta">Agent: {agent} · {date}</p>
    <!-- content here -->
  </div>
</body>
</html>
```

### 4. Plans (for dispatch mainly)

Plans go in `{project}/plans/` as markdown (.md) files. Include:
- What the project is
- What needs to happen (tasks/phases)
- What's done vs. pending
- Any decisions or open questions

### 5. Pulling before pushing

Always pull before push to avoid conflicts:
```bash
git pull origin main --rebase
git push
```

### 6. Quick reference — full push flow

```bash
git clone https://{TOKEN}@github.com/vLaD1m1r99/claude-workspace.git
cd claude-workspace
git config user.email "vlada@smote.co"
git config user.name "Claude Agents"

# do your work...

git add -A
git commit -m "{project}: {description}"
git pull origin main --rebase
git push
```

## For Vlada

Browse projects at: https://github.com/vLaD1m1r99/claude-workspace

View any HTML file on phone at: https://vlad1m1r99.github.io/claude-workspace/{project}/html/{file}.html
