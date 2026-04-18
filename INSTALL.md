# Skill pdftomd — Guide d'installation

## 1. Installer markitdown

```bash
pip install markitdown[all]
```

## 2. Installer le skill

Copier le dossier `pdftomd/` dans le répertoire des skills Claude Code :

```bash
cp -r pdftomd/ ~/.claude/skills/pdftomd/
```

## 3. Utilisation

Dans Claude Code, lancer la commande :

```
/pdftomd /chemin/vers/dossier
```

Ou sans argument pour utiliser le dossier courant :

```
/pdftomd
```

Les fichiers `.md` sont créés au même endroit que les `.pdf` d'origine.
