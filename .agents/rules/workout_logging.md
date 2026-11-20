# 📋 Workout Logging Workflow & Rules

This rule file dictates the precise multi-file update process and formatting guidelines to execute automatically whenever the user uploads or logs a workout.

---

## 🧘 Plain, Simple & Clean Documentation Style (Core Principle)

Keep workout logs clean, minimalist, readable, and free of unnecessary visual complications or bloat:

1. **No "Status" Column in Exercise Tables**:
   - Exercise tables (warm-up, strength, mobility, circuits) **MUST NOT** include a redundant `Status` column with repetitive `🟩 Completed` entries.
   - The presence of the log itself implies completion. Keep tables focused strictly on `Movement`, `Volume / Target`, and `Execution Focus`.

2. **No Separate Instructions per Set**:
   - **NEVER** write separate instructions or repetitive commentary for each individual set (e.g. avoid `*Set 1:* ...`, `*Set 2:* ...`, `*Set 3:* ...`).
   - Group sets cleanly (e.g. `- 3 Sets × 10 Reps` or `- 3 Sets × 1 Minute Hold`).

3. **Generalize Pain-Free Cues at the Top**:
   - State form guidelines and pain-free execution cues once, generalized directly underneath the exercise name/heading (e.g. `*Form & Safety: Keep elbows tucked, brace core, pain-free full range of motion.*`).

4. **Eliminate Redundant Duplication**:
   - Do **NOT** list exercises in a table and then repeat the exact same items as a checklist directly underneath. Choose one clean, readable format.

5. **Avoid Visual Clutter**:
   - Avoid massive, complicated ASCII art boxes or nested multi-level bullet structures. Use clean standard markdown headings, compact tables, and concise lists.

---

## 🔄 Multi-File Update Checklist

Every time a workout is uploaded/logged, the following files **must** be updated:

1. **Daily Workout Log (`YYYY-MM-DD.md`)**:
   - Location: `[Year]/[MM_Month]/[Week_XX]/[YYYY-MM-DD].md`.
   - **Strict Month-Wise Partitioning & Week Numbering**:
     - Files **MUST NEVER** cross month boundaries. All workout logs for month `MM` (e.g. `2026-08-31.md`) **MUST** stay in `[Year]/[MM_Month]/`. Never move an August file into September or vice versa.
     - Week numbering **ALWAYS resets to `Week_01` at the start of each new month** (e.g. `09_September/Week_01/`, `10_October/Week_01/`).
     - If a calendar week bridges two months (e.g. Aug 31 - Sep 06), August contains the August portion (e.g. `08_August/Week_06/2026-08-31.md`) and September starts with its own `Week_01` for September dates (e.g. `09_September/Week_01/2026-09-01.md`).
   - Format: Clean, plain markdown detailing warm-up, strength exercises, circuits, holds, and mobility following the simple style rules above.
   - Hyperlinks: Every exercise must link directly to its anchor in `../../../exercise_library.md#<slug>`.

2. **Weekly Overview (`Week_XX/README.md`)**:
   - Update the day's schedule row from `Planned` to `🟩 Completed`.
   - Add the relative link to the new daily log.
   - Increment the **Total Workouts** count.
   - Recalculate the **Adherence Rate**.
   - Check off weekly goals once targets are reached.

3. **Monthly Dashboard (`[MM_Month]/README.md`)**:
   - Increment **Total Sessions Completed**.
   - Mark the week's status as `🟩 Completed` in the table if the week's active workouts are done.

4. **Root Exercise Library (`exercise_library.md`)**:
   - Scan the daily log for any new unique exercises.
   - If found, add them to `exercise_library.md` under a **dedicated, individual H3 header** (do not group multiple exercises under a single header).
   - Include form cues, common mistakes, and a YouTube search link (`https://www.youtube.com/results?search_query=...`).

---

## 🔗 Portability & Linking Rules

- **Use Relative Paths only**: Do **NOT** write absolute `file:///` URLs in the markdown documents. All links must be relative (e.g., `[Log](2026-08-10.md)` or `[Week 3](Week_03/README.md)`) so they navigate natively in all markdown readers and remain portable.

---

## 🤸 Exercise-Specific Guidelines

- **Hanuman Dand**: Ensure this is defined as a dynamic push-up with alternating single-leg step-lunges outside the hands during the descent. Do **not** redirect to or group with the standard Hindu push-up.
