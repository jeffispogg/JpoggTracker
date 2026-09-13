# JPOGGTracker repair status

The repair branch is being used to fix the current library regression before it is promoted to `main`.

## Confirmed issue

The Supabase `titles` table uses `media_type`, not `type`. The current frontend was checking `title.type`, so existing entries can load while Anime and Manga filters/counts both show zero.

The database also stores totals as `total_episodes` / `total_chapters` and favorites as `is_favorite`. The frontend needs to map those fields correctly.

## Planned repair

- Map `media_type` correctly for Anime/Manga libraries.
- Map episode/chapter totals correctly.
- Map favorite state correctly.
- Make Add Title write the current database schema.
- Keep the Jikan search, poster, and details work already prepared locally.
- Verify the repaired source before moving it to `main`.
