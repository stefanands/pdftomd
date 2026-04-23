# pdftomd — Claude Code Skill

Converts all PDF files in a folder to Markdown, using Microsoft's [markitdown](https://github.com/microsoft/markitdown).

Created by [Stefan Anderson](https://github.com/stefanands) with [Claude Code](https://claude.ai/code) (Anthropic).

---

## Installation

### 1. Install markitdown

```bash
pip3 install --upgrade markitdown
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

---

---

# pdftomd — Skill Claude Code

Convertit tous les fichiers PDF d'un dossier en Markdown, en utilisant [markitdown](https://github.com/microsoft/markitdown) de Microsoft.

Créé par [Stefana Andriason](https://github.com/stefanands) avec [Claude Code](https://claude.ai/code) (Anthropic).

---

## Installation

### 1. Installer markitdown

```bash
pip install markitdown[all]
```

### 2. Installer le skill Claude Code

Copiez `SKILL.md` dans votre répertoire de skills Claude Code :

```bash
mkdir -p ~/.claude/skills/pdftomd
cp SKILL.md ~/.claude/skills/pdftomd/SKILL.md
```

C'est tout. La commande `/pdftomd` est immédiatement disponible dans Claude Code.

---

## Utilisation

Dans Claude Code, tapez :

```
/pdftomd /chemin/vers/dossier
```

Ou sans argument pour convertir le dossier courant :

```
/pdftomd
```

Les fichiers `.md` sont créés au même endroit que les `.pdf` d'origine.

---

## Formats supportés

markitdown supporte aussi DOCX, PPTX, XLSX, HTML, images, audio, et plus encore.
