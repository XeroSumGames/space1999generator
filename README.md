# space1999generator

A standalone Space: 1999 RPG character generator, built on Modiphius's 2d20
system (the engine used by the Space: 1999 Roleplaying Game). Walks a player
through the book's character-creation steps: Concept (department), Skills &
Attitudes, Focuses & Talents, and Finishing Touches (Spirit, Hope, Traits,
Signature Item), then prints a Moonbase Alpha personnel dossier.

Single self-contained static page: `index.html` (no build step, no dependencies,
no CDN).

## Hosting

Deployed as its own Vercel project. It is surfaced at
`https://thetapestry.distemperverse.com/space1999` via a proxy rewrite in the
TheTapestry app (that app rewrites `/space1999` to this deployment), so the
public URL sits on the main site while the code lives here, out of the
commercial TheTapestry repo (per that repo's AGENTS.md rule against mixing in
unrelated projects).

Because the rewrite is a proxy, the page runs on the
`thetapestry.distemperverse.com` origin, so the built-in visit beacon (bottom of
`index.html`) posts a `page='/space1999'` visit to the shared `log-visit` edge
function - the `/ape-log` dashboard in TheTapestry reads those.

## Rules source

Built from the Space: 1999 RPG "Creating a Character" chapter (Modiphius 2d20).
All allocation rules match the book: Skills start at 4 (set one to 6, one to 5
with at least one a department specialty, then spend 3 bonus points, max +2
each, cap 8); Attitudes start at 4 and add 10 (cap 8); 4 Focuses (at least one
from the department); 3 Talents (skill/attitude-tagged talents bind to a
choice); Spirit = 4 + 1 per Attitude of 7+ (+1 with Strong Will).

## Notes

- Visit logging respects the owner opt-out (`localStorage tapestry_no_log = '1'`).
- Minimum font size anywhere in the generator is 12px.
- Plain ASCII hyphens only in code and copy (no em/en dashes).
- "Inspire Trust" is listed as a suggested department talent in the book but is
  not defined in the Character Creation chapter (it appears to have been renamed
  to "Trustworthy"). It is shown only as suggestion text, not a selectable
  talent, pending confirmation.

## Legal

Space: 1999 (c) Anderson Entertainment Ltd. The Space: 1999 Roleplaying Game is
published by Modiphius Entertainment. This is an unofficial fan-made tool, not
affiliated with or endorsed by the rights holders. All game rules and content
remain the property of their respective owners.
