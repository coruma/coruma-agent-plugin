---
name: coruma-workout-review
description: Review the authenticated user's authorized workout history in Coruma and retrieve an optional workout GPS route. Use for workout comparisons, recent workouts, and route requests, not medical conclusions.
---

# Coruma workout review

1. Confirm or infer a bounded date range. State an inferred range.
2. Call `get_sync_status`, then call `list_health_records` with the `workout` type.
3. Paginate before making totals or comparisons for the full requested period.
4. Call `get_workout_route` only when the user asks for location or route details and the required scope is authorized.
5. For routes, fetch every page using the returned `snapshotId`. Restart if the snapshot changes. Group chunks by `routeKeyHash`, sort by `chunkIndex`, and verify completeness before describing a route as complete.

Missing route data does not prove the workout was indoors or that location permission was denied. Never infer a diagnosis, injury, health risk, or medical recommendation from workout records.
