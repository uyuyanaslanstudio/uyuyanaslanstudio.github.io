# uyuyanaslanstudio.github.io

Privacy policy pages for UyuyanAslan's games and apps, served by GitHub Pages
at **https://uyuyanaslanstudio.github.io/**.

Google Play requires a publicly reachable privacy policy URL for every listing.
That is the only job this repository has.

- `index.html` — studio landing page, links to each policy
- `blastaway.html` — https://uyuyanaslanstudio.github.io/blastaway.html
- one page per title, same shape, same filename convention
- `.nojekyll` — serves the files as-is, with no Jekyll build step in between

`fitaway.html` is the first page here for something that is not a game. It says
"training data" rather than "game data", it has no "More games" section because
the app has no such button, and it carries a section the game pages do not: the
JSON backup the user writes through Android's file picker. Copy the page that
matches what you are publishing.

> **The repository name is not cosmetic.** GitHub serves a site at the bare
> `https://<owner>.github.io/` only when the repository is named exactly
> `<owner>.github.io`. The org is `uyuyanaslanstudio`, so the repository has to
> be `uyuyanaslanstudio.github.io`. Named anything else — including
> `uyuyanaslan.github.io`, which is close enough to look right — it becomes a
> *project* site and the URL grows a path segment:
> `https://uyuyanaslanstudio.github.io/uyuyanaslan.github.io/blastaway.html`.
> That URL works, but it goes into every Play listing, so it is worth the
> twenty seconds to rename.

No build, no dependencies, no analytics. Every page is a single self-contained
HTML file with its CSS inline and **no external requests at all** — no web
fonts, no CDN, no images from elsewhere. A privacy policy that quietly contacted
a third party to render itself would be an odd thing to publish.

## Adding a game or app

Copy `blastaway.html` (a game) or `fitaway.html` (an app), change the title, the
`<h1>`, the app name in the body, and the date. Add a line to the list in
`index.html`. Then paste the new URL into that title's Play Console listing.

> **Read the "Links out of the app" section before you copy it.** It describes
> a "More games" button, and a title that does not have one — FitAway does not —
> would be making a false claim about itself in its own privacy policy. Two
> titles have shipped with the wrong version of this section. Check what the
> app actually does, then write that.

> **Verify the internet claim before you publish a page.** Every page says the
> app "is not granted the INTERNET permission". That was checked against
> BlastAway's actual release bundle — not against its source, and not by
> assumption. Before publishing a policy for another game, confirm it for that
> game's artifact:
>
> ```powershell
> & 'D:\dev\android-sdk\build-tools\36.0.0\aapt2.exe' dump permissions <that app>.apk
> ```
>
> If a title ever gains a dependency that pulls in `INTERNET`, its page has to
> say something different. The full method, including why a bundle needs a
> different check from an APK, is in `D:\Projects\BlastAway\RELEASE.md`.

## Publishing

Pages serves the `main` branch root. Settings → Pages → Source: *Deploy from a
branch*, branch `main`, folder `/`. First deploy takes a minute or two; after
that a push is live within seconds.
