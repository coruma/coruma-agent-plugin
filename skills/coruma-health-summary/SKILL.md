---
name: coruma-health-summary
description: Summarize the user's authorized Apple Health activity, sleep, heart rate, energy, workouts, or body measurements stored in Coruma. Use for bounded personal-history comparisons and summaries, not diagnosis or medical advice.
---

# Coruma health summary

Use Coruma only for the authenticated user's records and only when the user asks about their personal health or fitness history.

1. Determine the requested period and categories. If no period is supplied, use the last seven days and state that assumption.
2. Call `get_sync_status` to report server time, authorized categories, and synchronization freshness.
3. Call `list_health_records` with a bounded range and only the categories relevant to the request.
4. Follow pagination when the user needs a complete result for the requested period. Do not silently treat the first page as complete.
5. Summarize only what the returned records support. State the queried range, categories, freshness, and any incompleteness.

An empty result means only that no accessible synchronized records were returned for that range and those categories. It does not prove inactivity, missing Apple Health records, or denied device permission.

Do not diagnose, assign risk, recommend treatment, change medication, or claim clinical significance. For symptoms, emergencies, or medical decisions, explain that Coruma is not a medical service and advise the user to seek appropriate professional help.
