# Adjust My Plan

**Repository:** [github.com/YuqingWu-Nina/adjust-my-plan](https://github.com/YuqingWu-Nina/adjust-my-plan)

## Project idea

**Adjust My Plan** is a small browser prototype for students who procrastinate or are interrupted by unexpected tasks. It is a daily planner: every assignment stays today. When a new task arrives, the page automatically squeezes flexible time blocks instead of asking the student to drag tasks by hand.

This is a learning prototype, not a full calendar or a real deadline-management system. It uses a fixed planning window from 3:00 PM to 6:00 PM so that the scheduling rules are easy to see and test.

## How to run it

1. Open the `adjust-my-plan` folder.
2. Double-click `index.html` to open it in a browser.
3. Enter a task name, choose its minimum time, ideal time, and importance, then click **Add & auto-adjust**.

No installation, account, internet connection, or external library is needed.

## Open the HTML file

[Open `index.html` on GitHub](./index.html)

## Simple scheduling rules

1. Every task is scheduled for **Today**; nothing is automatically moved to tomorrow.
2. **High** importance comes before **Medium**, then **Low**.
3. Each task starts at its student-chosen **ideal time** and can shrink only to its **minimum time needed**.
4. When the day is too full, the planner squeezes lower-priority work first. When importance is equal, it squeezes existing work before a new task.
5. The 30-minute break is kept when possible and can only shrink to 15 minutes.
6. If every task is already at its minimum and the day still cannot fit, the page reports the exact conflict. It never silently deletes work.

## What changed?

After each adjustment, the page lists its decisions in plain language. For example: “Shortened ‘Work on presentation’ by 30 minutes, but kept its 30-minute minimum.” This makes the automatic scheduling visible rather than mysterious.

## Design revision: a phone-like daily calendar

Research into [Tiimo’s visual planning approach](https://www.tiimoapp.com/product/visual-planning) informed an original revision to this learning project. Tiimo uses visual timelines, flexible scheduling, clear task views, and a review of unfinished work. In this prototype, that idea becomes a mobile-first, phone-like daily calendar with an original and auto-adjusted view. It uses an original design and does not copy Tiimo’s visual identity or assets.

This project keeps one beginner-friendly interaction: responding to unexpected daily tasks without manually dragging a calendar.

## AI prompt used

> Build a small browser-based prototype called “Adjust My Plan” for students who procrastinate or get interrupted by unexpected tasks. Keep every assignment in one daily calendar. Each new task needs a minimum required time, ideal time, and importance. Automatically squeeze lower-priority flexible tasks without asking the student to drag blocks manually. Use one `index.html` with embedded CSS and JavaScript only; do not use external libraries or services. Make it look calm, friendly, phone-like, and easy to read, with beginner-friendly comments and documentation.

## Experience reflection

### What phenomenon or experience is your project representing?

This project represents the moment when a student’s daily plan is interrupted by a new assignment, message, or responsibility. The difficulty is not only having more work; it is the mental effort of deciding what to shorten, what to do first, and whether the whole day is now impossible.

### What part of that experience matters most?

The most important part is reducing the decision pressure. Instead of making the student manually drag every calendar block after an interruption, the prototype protects each task’s minimum useful time and automatically reshapes the rest of today. It also explains what changed, so the student does not feel that the planner made a mysterious decision for them.

### Does the current prototype represent that experience well? What does it capture or leave out?

The current prototype captures a small but realistic version of this experience: a new daily task arrives, lower-priority tasks become shorter, and every task remains visible in one phone-like calendar. It also honestly reports when the protected minimum times cannot fit. However, it leaves out real-life details such as changing energy levels, fixed meetings, travel time, long-term deadlines, and the student’s own choice about which task is acceptable to shorten. It is therefore a focused learning prototype, not a complete personal calendar system.

## Reflection placeholder

_After testing, I will write about what felt helpful, what was confusing, which scheduling rule worked or failed, and what I would improve next._
