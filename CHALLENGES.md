# Challenges

Work through these in order. Each one teaches one thing about working with
an agent. Nothing here is assessed, and you cannot break anything that git
cannot bring back.

Before you start, make a first commit:

```
git add -A
git commit -m "Start"
```

## 1 · Look around

Start `claude` in this folder and ask:

> What is in this folder, and what is the data about?

**Notice:** Claude reads files without asking. Reading inside this folder
never needs permission; changing anything does.

## 2 · Plan before doing

Press **Shift+Tab** until the status line says **plan mode**. Ask:

> I want a dose–response plot for both cell lines. How would you do it?

Read the plan. Ask a question about one step you do not understand. Then
press **Shift+Tab** to go back to manual mode and let Claude carry it out.

**Notice:** a plan is cheap to change; code is not.

## 3 · Approve, refuse, steer

As Claude works, it asks before each command and edit. Refuse one with
**No**, and tell it what to do differently.

**Notice:** "No" is not the end of the conversation. Telling Claude *why*
gets you a better second attempt.

## 4 · Check its work

The data file has at least **five problems** a careful scientist would
catch before plotting. Without asking Claude, open
`data/viability_plate.csv` in VS Code and look for them yourself. Write
down what you find.

Then ask Claude:

> Before we trust the plot, what is wrong or unusual in this data file?

Compare its list with yours. What did it find that you missed? What did
you find that it missed? Did its plot from challenge 2 quietly deal with
any of these problems without telling you?

**Notice:** the agent is fast, not careful. Checking is your job.

## 5 · Check one number by hand

Ask Claude for the mean DMSO signal for each cell line. Then calculate one
of them yourself from the file, with a calculator or a spreadsheet.

**Notice:** if you cannot check a number, you cannot use it.

## 6 · Break it and get it back

Commit your work. Then ask Claude to delete the plot script. Get it back
two ways:

- In Claude Code, type `/rewind` and pick a point before the deletion.
- In the terminal, `git restore <file>`.

**Notice:** `/rewind` undoes Claude's own file edits, not every command it
ran. git is the safety net that always works.

## 7 · Teach it a rule

Open `CLAUDE.md` and add a line of your own under **How to work with the
student**, for example:

> Always use a colour-blind-friendly palette in figures.

Type `/clear` to start fresh, ask for the plot again, and see whether it
follows your rule.

**Notice:** `CLAUDE.md` is how you give the agent lasting instructions.
You will write one for your project.

## 8 · Make it explain

Pick five lines of code Claude wrote and ask:

> Explain these lines one at a time, as if I have only done a beginner's
> Python course.

Then ask:

> What could go wrong with this code if the plate layout changed?

**Notice:** you are responsible for code you cannot explain.

## 9 · Notebook

Ask Claude to turn the analysis into a marimo notebook in this folder,
then open it with:

```
uv run marimo edit <notebook>.py
```

Change one concentration value in the data and watch the plot update.

## When you finish

Look at the top of each file Claude wrote. Is the `Agent-written`
declaration there, with the model and date? Fill in the
`Checked by student` line for one of them.
