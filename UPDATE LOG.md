# Bike Sync update log

Every publicly distributed update is recorded here when its signed package and manifest are published.

## 2.2.9 — August 14, 2026

- Hid the midnight placeholder used for workouts without a confirmed start time.
- Showed a time beside a workout only when the event has a confirmed start time or a matching activity supplies a completion time.
- Used elapsed activity time when available to calculate when a completed workout ended.

## 2.2.8 — August 14, 2026

- Showed a clear green check beside a scheduled workout once its matching completed activity reaches Intervals.icu.
- Recognized safe Strava and Intervals.icu title prefixes while still requiring the same date and compatible duration.
- Kept completed and overdue incomplete workouts visible in today's list.
- Marked incomplete workouts scheduled for today with a matching red right-pointing indicator.
- Avoided repeating a matched workout in the separate completed-activity section.

## 2.2.7 — August 14, 2026

- Made targeted duplicate deletion verify the exact Bike-Sync-owned event ID, date, title, and ownership before deletion.
- Prevented a targeted cleanup from deleting every managed workout on the same date.
- Started the first private coaching synchronization directly during application initialization.
- Included the Intervals date-and-time, launch-time synchronization, safe replacement, and calendar deduplication fixes developed in 2.2.5–2.2.6.

## 2.2.6 — August 14, 2026

- Sent full local date-and-time values for Intervals.icu coaching, health, weather-replacement, and copied calendar events.
- Started private coaching synchronization as soon as Bike Sync launches, without requiring the menu to be opened.
- Replaced older Bike-Sync-owned workouts while preserving manual races and subscribed calendar events.
- Restored recognition of Bradley's original legacy Intervals.icu Keychain entry.

## 2.2.5 — August 12, 2026

- Removed duplicate calendar-subscription rows that could accumulate across repeated refreshes.
- Combined equivalent subscribed and Intervals-backed calendar rows while retaining genuinely distinct rides.
- Preserved one cached event during a temporary calendar outage and replaced it on the next successful refresh.

## 2.2.4 — August 12, 2026

- Baselined the complete existing private request folder during the first universal sync.
- Prevented older files omitted from a stale legacy ledger from being processed after an upgrade.
- Limited processing to requests added or changed after the safe baseline.

## 2.2.3 — August 12, 2026

- Allowed safety-checked description-only corrections to legacy training events created by earlier Bike Sync versions.
- Continued to protect manual events by verifying the exact event ID, date, name, and managed identifier.

## 2.2.2 — August 12, 2026

- Migrated earlier Bike Sync request history before checking for new coaching requests.
- Prevented historical request files from being processed as newly approved calendar changes after an upgrade.

## 2.2.1 — August 12, 2026

- Expanded workout and optional-event cards now show their complete text in the scrollable menu.
- Added one-click animated demonstrations for recognized strength and mobility exercises.
- Restored connections saved under earlier Bike Sync credential labels.
- Added a safety-checked description-only correction for Bike Sync-managed workouts; manual Intervals.icu events remain protected.

## 2.2.0 — August 12, 2026

- Activated the signed public update feed.
- Added automatic verified installation at startup and every six hours when enabled.
- Added automatic retry after network failures and retained the previous application as a backup.
- Added the installed version, release notes, update status, and cumulative update log to the app.
- Included the 2.1.2 cache correction so calendar-only data cannot hide fuller Intervals.icu training data.
