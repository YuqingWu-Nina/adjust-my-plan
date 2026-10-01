# Learning Notes: Adjust My Plan

This note explains the project with simple computational language. Think of the browser page as a small helper that follows a list of instructions.

## 1. What each file does

- `index.html` is the whole website. It contains the words you see, the CSS that makes it look calm, and the JavaScript that makes the button work.
- `README.md` explains the project to someone who sees the folder on GitHub.
- `Learning_note.md` is my beginner-friendly explanation of the code.

## 2. Input → process → output

| Part | What happens in this project |
| --- | --- |
| **Input** | The student types a task name and chooses its minimum time, ideal time, and importance. |
| **Process** | JavaScript keeps every task in today, puts important tasks first, and squeezes flexible task lengths only as far as their protected minimum time. |
| **Output** | The page shows an adjusted schedule, or it shows a conflict message if the tasks cannot fit. |

## 3. Important code ideas

### A task is a small group of information

```js
{ name: "Finish reading assignment", duration: 60, minDuration: 45, importance: "medium" }
```

This is called an **object**. It keeps related information together. The output is a schedule line like: `3:00–4:00 Finish reading assignment`.

### An array is a list

```js
const originalTasks = [task1, task2, task3];
```

The square brackets mean “this is a list.” The page reads this list to draw the original plan.

### The button listens for a click

```js
form.addEventListener("submit", (event) => { ... });
```

This means: when the student clicks **Adjust My Plan**, run the instructions inside the braces. The visible output changes without opening a new page.

### Sorting means putting a list in an order

The `sortByImportance` function compares two tasks at a time.

1. All tasks are already for today, so it checks importance only.
2. It puts High before Medium before Low.

For example, a **High** task is placed before a **Medium** task. The output is that the high-priority task appears earlier in the adjusted plan.

### An `if` statement makes a choice

```js
if (planLength() > availableMinutes) { ... }
```

This asks one yes-or-no question: “Do all the work minutes plus the break go past 6:00 PM?”

- If the answer is **yes**, the output is a red conflict message.
- If the answer is **no**, the output is a new schedule and a supportive green message.

### The daily auto-squeeze plan makes small changes in an order

The `makeDailyPlan` function does not immediately say “conflict.” It tries these choices one at a time:

1. Keep every assignment in today’s calendar.
2. Shorten lower-priority flexible study time, but never below that task’s minimum time.
3. Shorten the break from 30 minutes to no less than 15 minutes.
4. If the plan still cannot fit, show the conflict message.

The output includes a “What changed?” list, so the student can see why their plan looks different without manually dragging anything.

### Minimum and ideal time are a range

```js
{ minDuration: 30, duration: 60 }
```

Here, `duration` starts as the ideal time (60 minutes). `minDuration` is the smallest useful amount of time (30 minutes). When new work arrives, the program can change 60 to 30, but it cannot make the task shorter than 30. The output stays in the Today calendar; it does not move to another day.

## 4. Easy test cases

| Try this input | Expected output |
| --- | --- |
| `Email teacher`, minimum 30, ideal 30, High | It fits. The new High task appears first, and the break stays. |
| `Prepare for quiz`, minimum 30, ideal 60, High | The presentation shrinks first because it has lower importance, but it keeps its 30-minute minimum. |
| Add a second task | The program adds it to the same day and recalculates every flexible block automatically. |

## 5. A small next step for me

I could let the student choose a new ending time, add a short focus timer, or let the user edit the protected minimum for an existing task. Before doing that, I should test the current simple version and make sure I understand each change.
