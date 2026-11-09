# FYP26 playground

A safe place to try Claude Code before you use it on your project. Nothing
here is assessed.

## Set up

You need VS Code, uv, git and Claude Code from the setup practical.

```
git clone https://github.com/HocheggerLab/fyp26-playground
cd fyp26-playground
uv sync
claude
```

When Claude Code starts, it asks whether you trust this folder. Say yes.

Then open [CHALLENGES.md](CHALLENGES.md) and work through it. When you
have finished, build your own lab notebook app with
[BUILD.md](BUILD.md).

## What is here

| Path | What it is |
|---|---|
| `CHALLENGES.md` | Nine short exercises, one skill each |
| `BUILD.md` | Build a lab notebook app, step by step |
| `CONCEPTS.md` | Python concepts Claude explains as you go |
| `CLAUDE.md` | Instructions Claude Code reads at the start of every session |
| `.claude/settings.json` | Manual mode, and a few blocked destructive commands |
| `data/` | A practice plate-reader file (invented data) |

The settings are the same as in your project workspace: Claude asks before
every edit and command, cannot write outside this folder, and cannot run
`sudo`, `rm -r`, force-push, `git reset --hard` or `git clean`.
