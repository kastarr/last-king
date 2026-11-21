# Magnificent — Instagram prop

Local, static page. No backend, accounts, popup code, analytics, or external requests.

## Open it

From the repository root:

```powershell
python -m http.server 8000
```

- **Scene 27 (profile/grid, default):** `http://127.0.0.1:8000/prototypes/instagram/`
- **Scene 41 (Club Extreme post):** `http://127.0.0.1:8000/prototypes/instagram/?scene=41`

The `scene` parameter is read before paint, then removed with `history.replaceState`; the selected state stays in the page. Re-navigate with the parameter to change the state in an existing tab. Opening `index.html` directly from disk still renders, but Safari may keep the query because `replaceState` is restricted on `file://`.

## Scene contract

- **27:** Magnificent profile, controls, highlights, and 9-photo party grid. The anniversary caption and post metadata are absent from this state. Tapping the first grid post opens the latest post detail; other grid posts open their own local photo detail.
- **41:** the Club Extreme post with `This week in honour of our fifth anniversary we do it every night at @ClubExtremeLagos`, `128,754 likes`, `View all 3,726 comments`, `Club Extreme, Lagos`, and `2 days ago`.
- Back returns to the profile. Escape also returns from the post.
- No query/URL changes during in-page navigation.

## Popup handoff

The stable page URL is `.../prototypes/instagram/`. For Scene 41, open or navigate the tab to `.../prototypes/instagram/?scene=41`.

An optional named tab target is `magnificent-instagram` (for example, an anchor or `window.open` with that target). Safari does not reliably focus an already-open tab, so manual tab switching is the fallback. The dark-web popup and its manifest stay outside this directory.

## Assets and clearance

Party, highlight, and post photographs are cropped from the supplied reference screens; they are local, fictional-looking reference imagery and are replaceable. They are not confirmed as final production-cleared photography. The Instagram wordmark/UI treatment is an imitation for the prop and needs production clearance; this is not a legal determination.

Physical iPhone 11 Safari/tab/camera verification remains a production sign-off item.
