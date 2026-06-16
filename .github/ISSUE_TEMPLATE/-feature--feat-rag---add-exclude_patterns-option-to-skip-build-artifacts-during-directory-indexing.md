---
name: "[FEATURE] feat(rag): Add exclude_patterns option to skip build artifacts during
  directory indexing"
about: Suggest an idea for this project
title: ''
labels: enhancement, good first issue
assignees: ''

---

```markdown
## Problem
When you add a folder to the RAG server to search through your code, it indexes EVERYTHING - including junk files like `node_modules` (thousands of JavaScript packages), `.git` folders, Python cache files, and log files. This makes searches slow and gives you irrelevant results.

## What I want
A simple way to tell the RAG server to skip certain files/folders when indexing. Like a "skip list" where you can say:
- Skip `*.log` files
- Skip folders named `node_modules` 
- Skip `.git` folders
- Skip `__pycache__` folders

## How it would work
When you run `manage_rag` with `add_directory`, you could add:
```
exclude_patterns: ["*.log", "node_modules", ".git", "__pycache__"]
```

The RAG server would skip those files and tell you how many were skipped.

## Why this helps
- Faster indexing (skips thousands of unnecessary files)
- Better search results (no junk in the mix)
- No need to manually clean folders before adding them
```
