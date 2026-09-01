# 📋 Workout Logging Workflow & Rules

This rule file dictates the precise multi-file update process and formatting guidelines to execute automatically whenever the user uploads or logs a workout.

---

## 🔄 Multi-File Update Checklist

Every time a workout is uploaded/logged, the following files **must** be updated:

1. **Daily Workout Log (`YYYY-MM-DD.md`)**:
   - Location: `[Year]/[MM_Month]/[Week_XX]/[YYYY-MM-DD].md`.
   - **Strict Month-Wise Partitioning & Week Numbering**:
     - Files **MUST NEVER** cross month boundaries. All workout logs for month `MM` (e.g. `2026-08-31.md`) **MUST** stay in `[Year]/[MM_Month]/`. Never move an August file into September or vice versa.
     - Week numbering **ALWAYS resets to `Week_01` at the start of each new month** (e.g. `09_September/Week_01/`, `10_October/Week_01/`).
     - If a calendar week bridges two months (e.g. Aug 31 - Sep 06), August contains the August portion (e.g. `08_August/Week_06/2026-08-31.md`) and September starts with its own `Week_01` for September dates (e.g. `09_September/Week_01/2026-09-01.md`).
   - Format: Clean markdown detailing warm-up, strength exercises, circuits, holds, and mobility.
   - Status: All checkbox items default to completed `[x]`, since uploading implies completion.
   - Flow Diagrams: Use standard Unicode/ASCII text-based box diagrams for circuits/flows instead of Mermaid to guarantee rendering across all markdown viewers.

2. **Weekly Overview (`Week_XX/README.md`)**:
   - Update the day's schedule row from `Planned` to `🟩 Completed`.
   - Add the relative link to the new daily log.
   - Increment the **Total Workouts** count.
   - Recalculate the **Adherence Rate**.
   - Check off the weekly goals (e.g. `Complete 3 Calisthenics/HIIT sessions`) once targets are reached.

3. **Monthly Dashboard (`[MM_Month]/README.md`)**:
   - Increment **Total Sessions Completed**.
   - Mark the week's status as `🟩 Completed` in the table if the week's active workouts are done.

4. **Root Exercise Library (`exercise_library.md`)**:
   - Scan the daily log for any new unique exercises.
   - If found, add them to `exercise_library.md` under a **dedicated, individual H3 header** (do not group multiple exercises under a single header).
   - Include form cues, common mistakes, and a YouTube search link (`https://www.youtube.com/results?search_query=...`).

---

## 🔗 Portability & Linking Rules

- **Use Relative Paths only**: Do **NOT** write absolute `file:///` URLs. All links must be relative (e.g., `[Log](2026-08-10.md)` or `[Week 3](Week_03/README.md)`) so they navigate natively in all markdown readers and remain portable.

---

## 🤸 Exercise-Specific Guidelines

- **Hanuman Dand**: Ensure this is defined as a dynamic push-up with alternating single-leg step-lunges outside the hands during the descent. Do **not** redirect to or group with the standard Hindu push-up.
