Bike Sync update log

2.4.16 — August 19, 2026
- Gives Bike Coach one reusable read-only batch request for the exact Intervals.icu streams from as many as 25 activities, including Di2 front gear, rear gear, ratio, and pedaling gear code when recorded.
- Lets read-only activity-history queries span up to five years by safely dividing them into one-year Intervals.icu calls, so recurring rides and long-distance rides can be found without repeated manual requests.
- Accepts the earlier `resource` field as a backwards-compatible alias for `query_resource`, preventing a harmless request-format mismatch from derailing a coaching analysis.
- Explicitly requires Bike Coach to report exact stream availability per activity and never pretend cadence or speed reveals an exact gear when the FIT file lacks Di2 telemetry.

2.4.15 — August 18, 2026
- Restores the missing 1-second polygon node in the season power radar.
- Uses the published Cycling Analytics male 1-second power distribution for that node because Intervals.icu precomputes rankings only from 5 seconds onward.
- Labels the 1-second percentile as approximate and identifies its all-men comparison group; all other nodes continue to use the selected Intervals.icu age group.
- Replaces the large always-visible next-ride forecast with a compact today-through-Sunday weather strip.
- Labels each day Morning, Evening, Any, or Indoor and separately recommends Bike Commute or Transit; only daylight windows with dry pavement, rain at or below 10%, temperatures from 40–90°F, and acceptable AQI qualify.
- Shows each day's detailed temperature, perceived temperature, humidity, rain, cloud, wind, AQI, pavement, and best window on hover while keeping route-specific weather inside each planned ride's arrow expansion.
- Uses the existing Strava connection to recommend a saved Illinois segment under 2 miles only when a consistent tailwind stays above 10 mph and within 15 degrees of its direction.

2.4.14 — August 18, 2026
- Adds exact 1-second power and watts per kilogram to the season power radar.
- Leaves the 1-second percentile line blank because Intervals.icu supplies age-group rankings from 5 seconds onward; Bike Sync never substitutes or invents a percentile.
- Keeps ordinary automatic app updates password-free after the initial installation; release-building access to developer signing keys is now handled as a separate publisher workflow and is never part of an end user's update.
- Reduces a release build to one developer-identity signing operation and reuses the stable publisher helper, eliminating the repeated password cascade caused by rebuilding and re-signing intermediate copies.
- Consolidates saved service credentials into one app-owned Keychain vault. Legacy records are migrated once as they are used; subsequent launches and automatic updates open one stable vault instead of six separate Keychain items.

2.4.13 — August 18, 2026
- Shows one-decimal watts per kilogram beside every watt value in the season power radar.
- Uses lowercase `w` and `w/kg` in the eFTP headline.
- Adds a hover graph to VO₂ max using a true 365-day Intervals.icu wellness history, with exact dated values available on each point.
- Keeps private exercise-selection and equipment constraints out of visible workout text while still applying them when the coach selects exercises.

2.4.12 — August 17, 2026
- Replaces the cramped “%ile” shorthand with the full, unambiguous “th percentile” label beneath eFTP and every power-radar value.

2.4.11 — August 17, 2026
- Removes the Polar skin-temperature setting, display, recovery rule, and API request because the connected Polar Loop supplies no skin-temperature measurement.
- Centers the compact wellness-detail lines and hides wellness items that have no measured value.
- Shows current eFTP as watts and one-decimal watts per kilogram using the current Intervals.icu weight.
- Shows the Intervals M/F age-group percentile for this season's eFTP beneath the current eFTP and displays a hover radar for this season's 5-second through 1-hour power, with an exact Intervals percentile under every watt value.
- Uses Intervals' 5-second rank as the shortest radar axis because Intervals does not supply a 1-second age percentile.
- Gives Bike Sync one stable, app-specific signing identity so macOS can recognize future updates as the same app instead of repeatedly asking for every saved credential.
- Keeps the independent publisher signature and checksum as the update trust boundary while recognizing the pinned local app identity on Macs where its certificate is intentionally not a general system trust root.
- Preserves the verified Polar readiness, ANS Recharge, sleep score, lowest sleeping heart rate, and VO2-max data added in 2.4.10.

2.4.10 — August 17, 2026
- Repairs the direct Polar connection to use the supported AccessLink v3 service and preserves previously authorized connections in macOS Keychain.
- Shows Polar Nightly Recharge readiness as six status circles with a parenthetical percentage; Polar values use Polar status colors and Intervals.icu values retain the Intervals accent.
- Reads ANS Recharge and the lowest five-minute sleep heart-rate sample directly from Polar, including the sleep samples Polar itself attaches to the night.
- Reads the current dated Polar VO2 max and can fill only a missing Intervals.icu VO2-max entry; existing values and all Polar weight data are protected from overwrite.
- Keeps Apple Health and Wyze scale data on the existing iPhone Health Sync path because macOS cannot read the iPhone Health database and Wyze publishes no supported scale-data API.
- Adds a packaged bicycle application icon while retaining the smaller menu-bar bicycle.

2.4.9 — August 17, 2026
- Keeps the eFTP, VO2 max, Fitness, Fatigue, and Form cards prominent.
- Replaces the six separate wellness cards with a compact three-column text list beneath them.
- Removes individual wellness backgrounds and borders while preserving values, dates, targets, sources, and missing-data labels.

2.4.8 — August 17, 2026
- Places current Intervals.icu eFTP and the newest dated VO2 max measurement above Fitness, Fatigue, and Form.
- Rebuilds the wellness area as six prominent tiles: ramp versus target, sleep, readiness, Polar ANS Recharge, lowest sleep heart rate, and latest blood pressure.
- Uses the newest complete Intervals.icu systolic/diastolic record and shows its date; incomplete or missing readings remain visibly unavailable.
- Calculates lowest sleep heart rate only from Polar heart-rate samples inside Polar's recorded sleep start/end interval, including sleep that crosses midnight.
- Adds VO2 max and blood pressure to Bike Coach's read-only wellness data, while direct Polar sleep details include the recovered nightly minimum.

2.4.7 — August 17, 2026
- Mirrors the eFTP displayed in Intervals.icu Sport Settings by reading the newest cycling fitness signature from daily wellness.
- Keeps that displayed eFTP distinct from configured FTP, indoor FTP, the separate `mmp_model` curve, and activity-specific historical estimates.
- Shares the same displayed eFTP, eW′, and ePmax with Bike Coach and uses only displayed eFTP for the optional FTP synchronization rule.
- Adds regression coverage for the exact case where Intervals displays eFTP 311 W while configured FTP and the separate curve model are 295 W.

2.4.6 — August 17, 2026
- Labels an empty planned day as Rest day in the Today-through-Sunday list instead of displaying a generic no-event message.
- Keeps completed-activity matching separate, so Rest day describes the plan and does not claim that an activity was completed.

2.4.5 — August 17, 2026
- Gives every approved coaching request its own stable Intervals.icu identifier, so a same-day warm-up, TT Pace workout, and between-race re-warm remain three separate workouts instead of overwriting one another.
- Keeps the existing exact-name and exact-duration duplicate repair in place, so retrying one request still cannot create repeated copies.
- Removes the redundant TT Pace refresh preference: percentage-based TT workouts follow the configured FTP, so the one Intervals.icu FTP-sync checkbox is sufficient and workouts are not rewritten.
- Discovers race-like events from connected optional calendars for the next 180 days, while keeping each athlete's Entered choice separate from the shared calendar.
- Creates a course-distance TT Pace workout only for an entered time trial after the course distance, turnaround, and expected duration have been reviewed.
- Shares official event pages and route links with Bike Coach for strategy; road races never create TT Pace files.
- Flags multiple or conflicting published course distances for review instead of guessing.

2.4.4 — August 17, 2026
- Uses Intervals.icu's current athlete-wide cycling model for eFTP and never substitutes a historical eFTP stored on an individual activity.
- Can keep configured cycling FTP equal to athlete-wide eFTP, then refresh every future percentage-based workout containing TT Pace in its name so connected bike platforms rebuild the targets.
- Adds an optional one-time Strava profile connection for keeping Strava FTP equal to the same athlete-wide Intervals.icu value; credentials and refresh tokens stay in macOS Keychain.
- Gives Bike Coach a bounded activity-stream query for core temperature and other device or custom streams that Intervals.icu exposes, while excluding GPS/location streams.
- Teaches Bike Coach to name every actual time-trial pacing workout with TT Pace and to keep warm-ups and between-race re-warms separate.

2.4.3 — August 16, 2026
- Lets Bike Coach list athletes the Intervals.icu account follows or coaches and request an explicitly selected athlete's profile, power curves, activities, analyzed intervals, calendar, and wellness data.
- Keeps all secondary-athlete access read-only and verifies the athlete ID against Intervals.icu before returning any data.
- Repeats the selected athlete's ID and name in every result so one rider's FTP, recovery, or power history cannot be silently applied to another.
- Clearly reports Intervals.icu's Strava forwarding restriction instead of estimating missing coached-athlete records.

2.4.2 — August 16, 2026
- Repairs existing duplicate Bike Sync-managed calendar workouts automatically before Fitness, Fatigue, Form, ramp rate, or coaching data are read.
- Removes every managed weather replacement when the associated outdoor ride is only an optional note, subscription entry, race, or otherwise absent from the planned workout calendar.
- Keeps at most one weather replacement per ride and date even when Intervals.icu accepts repeated event identifiers.
- Collapses same-day managed workout duplicates created by older bridge identifiers while preserving manual and third-party events.
- Rechecks Intervals.icu after cleanup so duplicate planned load cannot produce a false overnight fatigue or Form change.

2.4.1 — August 15, 2026
- Prevents calendar-only subscriptions from being created as executable bike-computer workouts; copied subscription entries remain visible as notes.
- Requires every Bike Sync-created cycling workout to return a real Intervals.icu workout document with nonzero duration and structured steps.
- Rolls back a newly created blank workout, or restores the last working description after a failed edit, instead of allowing a 0:00 entry to sync to a head unit.
- Creates and validates an automatic recovery or weather-substitution workout before removing the workout it replaces, so a parsing failure cannot empty the day.
- Updates the private coaching instructions so every executable cycling step uses native dash-prefixed Intervals.icu workout-builder syntax.

2.4.0 — August 15, 2026
- Adds an editable rider profile with development priorities, priority event, and success goal to both the app and private coaching reports.
- Includes Intervals.icu respiration together with current load, wellness history, recent activities, power curves, configured FTP, modeled FTP, and critical power.
- Expands the default private coaching report to up to 500 recent activities over 365 days, 90 days of wellness, and calendar context from 28 days past through 180 days ahead, including cadence and other decision-relevant activity summaries when Intervals.icu supplies them.
- Lets the connected phone coach request bounded read-only activity, analyzed-interval, activity-history, calendar, or wellness detail when the base report is insufficient, without enabling calendar writes or exposing credentials and GPS tracks.
- Adds an optional direct Polar connection for supplemental Nightly Recharge context, detailed sleep, skin-temperature trend, and recovery tests while keeping Intervals.icu primary for overlapping measurements.
- Treats same-night Polar recovery measurements as one correlated cluster and keeps Polar fitness-test VO2 max separate from cycling FTP and power targets.
- Strengthens Bike Coach instructions so personalization must reconcile rider type, goals, current recovery, recent work, calendar, and the existing training plan without false confidence.
- Allows an editable automatic-adjustment policy to convert ordinary Bike Sync-managed plan workouts into an executable 30-minute recovery ride, while protecting races, pacing files, openers, key sessions, manual events, group rides, and completed activities.
- Counts the night's related wearable measurements as one recovery cluster and lets each user decide whether one clearly poor cluster is enough to reduce an ordinary workout automatically.
- Adds an editable workout-preparation policy: short pre-ride activation, post-ride mobility, strength-day core progression, long-ride posture reminders, and one-click animated demonstrations.
- Keeps preparation inside the athlete's time budget and preserves key intervals by trimming only easy riding when a workout is capped.
- Keeps bike work, activation, mobility, and strength as separate Intervals.icu items by default and uses Intervals.icu's paired-event identifier—or a conservative distinctive-title and duration fallback—to recognize recorder-named completions such as “Zwift - Openers.”
- Includes two editable optional longer mobility resources recommended by Johannes while keeping them separate from the short automatic block.
- Adds a customizable blocked-source policy that removes exactly matched completed-activity sources before Fitness, Fatigue, Form, ramp rate, recovery decisions, or coaching reports are calculated. Bradley's supplied profile blocks Intervals Companion while a clean install leaves this destructive policy off.
- Keeps automatic updates verified, installed in place, and relaunched without changing each user's preferences or credentials.

2.3.1 — August 15, 2026
- Refreshes the private coaching instructions during ordinary synchronization when the installed update contains newer safety rules.
- Existing users now receive the same athlete-scoping, data-completeness, false-confidence, and calendar-confirmation safeguards as a fresh connection without repeating setup.

2.3.0 — August 15, 2026
- Gives the private coaching report the connected athlete's cycling FTP, weight, power zones, selected 42-day, one-year, and all-time power-curve points, up to 200 recent activity summaries, and recent wellness trends.
- Identifies the one athlete represented by each report so coaching data cannot be silently reused for another person.
- Separately reports whether detailed Intervals.icu data are complete, partial, or disabled and marks the synchronization incomplete when power-curve or recent-activity retrieval fails.
- Directs Bike Coach to distinguish configured FTP, modeled FTP, and historical best power and to disclose missing evidence instead of presenting generic targets with false confidence.
- Keeps future planned-load projections out of the current recovery status and wellness history.
- Immediately rereads Intervals.icu after a coaching calendar change and confirms the returned event in the same report that carries the applied request filename.
- Adds a privacy preference for detailed coaching data while continuing to exclude credentials, authentication keys, raw workout files, and GPS tracks.

2.2.9 — August 14, 2026
- Hides the midnight placeholder used for workouts without a confirmed start time.
- Shows a time beside a workout only when the event has a confirmed start time or a matching activity supplies a completion time.
- Uses elapsed activity time when available to calculate when a completed workout ended.

2.2.8 — August 14, 2026
- Shows a clear green check beside a scheduled workout once its matching completed activity reaches Intervals.icu.
- Recognizes safe Strava and Intervals.icu prefixes while still requiring the same date and a compatible duration.
- Keeps the completed workout in today's list after its scheduled time passes.
- Marks each incomplete workout scheduled for today with a matching red right-pointing indicator and keeps overdue workouts visible through the day.
- Avoids repeating the same workout in a separate completed section; unmatched activities remain visible there.
- Gives the completion check an accessibility label so VoiceOver also announces the workout as completed.

2.2.7 — August 14, 2026
- Honors a coaching request's exact target event ID, date, and title when deleting a duplicate Bike-Sync-owned event.
- Refuses a targeted deletion if the event moved, was renamed, or is not owned by Bike Sync.
- Keeps date-wide cleanup available only when the coaching request does not name a target event.
- Starts the first synchronization directly during application initialization so it cannot wait for the menu to be opened.

2.2.6 — August 14, 2026
- Sends full local date-and-time values to Intervals.icu for coaching, health, weather-replacement, and copied calendar events.
- Starts Intervals.icu and private coaching synchronization as soon as Bike Sync launches; opening the menu is no longer necessary.
- Makes a coaching “replace” request remove only older Bike-Sync-owned workouts on that date before creating the revised workout; manual races and subscribed calendar events remain protected.
- Recognizes Bradley's original legacy Intervals.icu Keychain entry during upgrades.

2.2.5 — August 12, 2026
- Removes duplicate calendar-subscription rows that could accumulate across repeated refreshes.
- Shows one combined row when a calendar-backed Intervals.icu event differs only by generic calendar, route-type, or distance labels.
- Keeps genuinely distinct rides visible, including different rides at the same start time.
- Retains one cached event only when its calendar is temporarily unavailable, then replaces it on the next successful refresh.

2.2.4 — August 12, 2026
- Baselines the complete existing private request folder during the first universal sync.
- Prevents older files omitted from a stale legacy ledger from being processed after an upgrade.
- Processes only requests added or changed after that safe baseline.

2.2.3 — August 12, 2026
- Allows description-only corrections to legacy training events that were created and managed by earlier Bike Sync versions.
- Still verifies the exact event ID, date, and name and refuses to edit manual events.

2.2.2 — August 12, 2026
- Migrates the earlier coaching-request ledger before the bridge checks for new requests.
- Prevents historical coaching files from being processed as newly approved calendar changes after an upgrade.

2.2.1 — August 12, 2026
- Shows the complete text when any workout or optional event is expanded.
- Keeps long workout text readable by using the menu's existing vertical scrolling.
- Adds one-click animated exercise demonstrations for recognized strength and mobility movements.
- Restores existing Intervals.icu and private coaching connections saved by earlier Bike Sync versions.
- Allows an explicitly approved managed workout description to be updated without changing its prescription or touching manual events.

2.2.0 — August 12, 2026
- Activates the signed public update feed.
- Automatically downloads and installs verified releases when the preference is enabled.
- Checks at startup and every six hours while Bike Sync remains open.
- Keeps the previous application as a recoverable backup during an update.
- Shows the installed version, current release notes, update status, and this update log inside the app.
- Retains complete Intervals.icu training data when a newer calendar-only cache exists.

2.1.2 — August 12, 2026
- Preserves the fuller Intervals.icu training cache when a newer calendar-only cache exists.
- Combines optional calendar entries and route weather with cached training status and workouts.

2.1.0 — August 11, 2026
- Introduces the portable universal Intel and Apple-silicon application.
- Adds customizable calendars, recurring rides, weather, recovery adjustments, optional coaching, diagnostics, and guided setup.
