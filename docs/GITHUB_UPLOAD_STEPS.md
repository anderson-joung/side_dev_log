# GitHub Upload Steps

## 1. Create a new repository

Recommended repository name:

```text
sj-applied-tech-tycoon
```

Recommended settings:

- Visibility: Private
- README: do not auto-generate if you are uploading this package
- .gitignore: None
- License: None for now

## 2. Upload files

Unzip the GitHub upload package.

Upload the contents of the folder, not the ZIP itself.

The repository root should contain:

```text
index.html
README.md
AI_HANDOFF.md
.gitignore
assets/
docs/
prompts/
```

## 3. Commit message

Use this commit message:

```text
Initial GitHub upload for SJ Applied Tech Tycoon prototype
```

## 4. Optional GitHub Pages

After upload:

1. Go to Settings
2. Go to Pages
3. Source: Deploy from branch
4. Branch: main
5. Folder: /root
6. Save

Then GitHub will give you a browser-playable link.

## 5. Next ChatGPT handoff

When asking ChatGPT to continue work, upload the latest ZIP or point to the latest repository state and say:

```text
AI_HANDOFF.md 기준으로 v4.4 만들어줘.
```
