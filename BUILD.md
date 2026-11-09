# Build a lab notebook app

Build your own lab notebook and to-do app with Claude: a real program
with buttons and pages that opens in your browser. It takes about two
hours. You decide what it does; Claude writes the code and explains the
Python as it goes.

The app uses **NiceGUI**, which builds browser apps in plain Python.
Notebook entries are saved as markdown files, so you can open them in VS
Code, and git keeps every version.

## How to work

- Do one step at a time. Write the prompt yourself; the suggested prompts
  are starting points, not scripts.
- Read each command before you approve it.
- When Claude explains a new Python concept, read it, and answer the
  question it asks at the end of the step. Your explanations collect in
  `CONCEPTS.md`.
- Commit after every step that works:

  ```
  git add -A
  git commit -m "Step 2: entries"
  ```

- Run the app to check it after every step. Claude will tell you the
  command; it is usually `uv run app.py`. Stop it with **Ctrl+C**.

## Step 1 · Decide what to build (plan mode)

Press **Shift+Tab** until you are in **plan mode**, then describe the app:

> I want a lab notebook app with NiceGUI. I can write dated entries, keep a
> to-do list, and use templates for common experiments. Write a short
> SPEC.md first: the pages, what each one does, and how entries are stored.
> Keep it small. Don't write code yet.

Read `SPEC.md` and change it until it describes what you want. Cut
anything you would not use.

**Watch for:** Claude tends to plan too much. A small app that works beats
a big one that does not.

## Step 2 · Write and read entries

> Build the first part from SPEC.md: a page where I can write an entry with
> a date, a title and text, save it as a markdown file in a notebook/
> folder, and see a list of my entries.

**Watch for:**

- Claude adds NiceGUI with `uv add nicegui`. That is the only way to add
  packages in this folder; `pip` is never used.
- New concepts here: functions, file paths with `pathlib`, f-strings.
- Ask Claude where your entries are saved, then find one and open it in
  VS Code.

## Step 3 · To-do list

> Add a to-do list: items with a due date, a button to mark them done, and
> overdue items shown in red.

**Watch for:**

- New concepts: dictionaries, dates with `datetime`.
- Make a to-do that was due yesterday. Is it red?

## Step 4 · Experiment templates

> Add templates. "New PCR" should open an entry with a table for the
> reaction mix, the cycling conditions, and a space for the gel result. Do
> the same for a western blot and a transfection.

**Watch for:** templates are just text with blanks to fill. Ask Claude how
it fills in the date automatically.

## Step 5 · The biology

Pick at least two.

**Cell culture tracker**

> Add a cell culture page. When I log a split for a cell line, the passage
> number goes up by one and a to-do "Split <cell line>" appears, due in
> three days.

**Incubation timer**

> Add a timer: I type "Transfection, 6 h", it counts down, and a
> notification pops up when it is done.

**Gene lookup**

> Add a box where I type a human gene name like TP53, and the app shows the
> protein name and length from UniProt.

**Watch for:**

- The timer needs the app to do two things at once. New concept:
  `async`/`await`. Ask Claude to explain why the app does not freeze while
  the timer runs.
- The gene lookup calls the internet. Claude asks permission before using
  the network, and explains what an API is and what JSON looks like. Type
  a made-up gene name: what happens?

## Step 6 · Search and tags

> Let me tag entries with #tags like #HeLa or #western, and add a search
> box that finds entries by word or tag.

**Watch for:** new concept: loops that filter a list. Ask Claude to show
you the five lines that do the searching.

## Step 7 · Try to break it

Find out what your app does with bad input, and fix what breaks:

- An entry with no title.
- A cell split logged for a date next year.
- A markdown file in `notebook/` that you edited by hand and broke.

> The app crashed when <what you did>. Explain why, then fix it so it
> shows a sensible message instead.

**Watch for:** new concept: `try`/`except`, Python's way of handling
errors. Did Claude explain the cause before fixing it?

## When you finish

- Read `CONCEPTS.md`. Pick one concept and explain it to the person next
  to you without looking.
- Check that each file Claude wrote has its `Agent-written` declaration,
  and fill in the `Checked by student` line for one of them.
- Add one feature of your own: a freezer box map, a reagent expiry list,
  or anything you would actually use.
