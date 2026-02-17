# Antigravity Skill Hunter Implementation Playbook

This document explains how to install skills from the 'antigravity-awesome-skills' repository.

## Installation Methods

### Method 1: GitHub CLI (`gh`) - Recommended

Using `gh` is the most reliable way to list and fetch files.

**List Skills:**
```bash
gh api repos/sickn33/antigravity-awesome-skills/contents/skills --template '{{range .}}{{.name}}{{"\n"}}{{end}}'
```

**Install a Skill:**
1.  Check content: `gh api repos/sickn33/antigravity-awesome-skills/contents/skills/<skill_name>`
2.  Download `SKILL.md`: `gh api repos/sickn33/antigravity-awesome-skills/contents/skills/<skill_name>/SKILL.md --header 'Accept: application/vnd.github.v3.raw' > .agent/skills/<skill_name>/SKILL.md`
3.  Resources: Use `svn export` or recursive download if possible, or just fetch `resources/implementation-playbook.md` if known.

### Method 2: Curl / Raw Download

If `gh` is not available, use `curl` to fetch raw files.

**Base URL:**
`https://raw.githubusercontent.com/sickn33/antigravity-awesome-skills/main/skills/`

**Install:**
```bash
mkdir -p .agent/skills/<skill_name>
curl -o .agent/skills/<skill_name>/SKILL.md https://raw.githubusercontent.com/sickn33/antigravity-awesome-skills/main/skills/<skill_name>/SKILL.md
```

## Troubleshooting

- **404 Not Found**: The skill might not exist or the name is typoed. Check the list first.
- **Empty File**: `curl` might have failed silenty or returned an error page. Check file size.
- **Missing Resources**: Some skills have resources. Check the repo manually if the skill references missing files.
