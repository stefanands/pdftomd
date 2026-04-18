# pdftomd — Claude Code Skill

Converts all PDF files in a folder to Markdown, using Microsoft's [markitdown](https://github.com/microsoft/markitdown).

Created by [Stefana Andriason](https://github.com/stefanands) with [Claude Code](https://claude.ai/code) (Anthropic).

---

## Installation

### 1. Install markitdown

```bash
pip install markitdown[all]
```

### 2. Install the Claude Code skill

Copy `SKILL.md` into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/pdftomd
cp SKILL.md ~/.claude/skills/pdftomd/SKILL.md
```

That's it. The `/pdftomd` command is immediately available in Claude Code.

---

## Usage

In Claude Code, type:

```
/pdftomd /path/to/folder
```

Or without argument to convert the current directory:

```
/pdftomd
```

Output `.md` files are created alongside the original `.pdf` files.

---

## Supported formats

markitdown also supports DOCX, PPTX, XLSX, HTML, images, audio, and more.
