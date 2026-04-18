---
name: pdftomd
description: Converts all PDF files in a folder to Markdown using markitdown. Use this skill when the user invokes /pdftomd or asks to convert PDFs to markdown, convert a folder of PDFs, or batch-convert documents.
---

# pdftomd — Batch PDF to Markdown converter

## What to do

1. **Get the target folder** — use the path provided as argument. If none was given, ask the user: "Quel dossier voulez-vous convertir ? (laissez vide pour utiliser le dossier courant)"
2. **Find all PDFs** recursively in that folder using `find`.
3. **Convert each PDF** with `markitdown "$f" -o "${f%.pdf}.md"`, printing progress for each file.
4. **Report a summary**: total found, converted successfully, failed (with filenames).

## Bash script to run

```bash
FOLDER="${1:-.}"
echo "Recherche des PDFs dans : $FOLDER"
FILES=$(find "$FOLDER" -type f -name "*.pdf")
TOTAL=$(echo "$FILES" | grep -c '.pdf' 2>/dev/null || echo 0)
echo "→ $TOTAL PDF(s) trouvé(s)"
SUCCESS=0; FAIL=0; FAILED_LIST=""
while IFS= read -r f; do
  [ -z "$f" ] && continue
  OUT="${f%.pdf}.md"
  echo -n "  Conversion : $f ... "
  if markitdown "$f" -o "$OUT" 2>/dev/null; then
    echo "✓"
    SUCCESS=$((SUCCESS + 1))
  else
    echo "✗"
    FAIL=$((FAIL + 1))
    FAILED_LIST="$FAILED_LIST\n  - $f"
  fi
done <<< "$FILES"
echo ""
echo "Terminé : $SUCCESS converti(s), $FAIL échec(s)."
[ -n "$FAILED_LIST" ] && printf "Fichiers en échec :%b\n" "$FAILED_LIST"
```

Run this script via Bash, substituting the user's folder for `$FOLDER`.

## Notes
- Output `.md` files are created alongside each `.pdf` (même dossier).
- If `markitdown` is not found, tell the user to run: `pip3 install markitdown[all]`
- Warn if no PDFs were found.
