# Wharton Rotary AI Hackathon

Live 30-minute AI hackathon demo for the Rotary Club of Wharton, TX. Audience members submit web app ideas on paper, Claude Code builds them in real time, and everyone tests the apps on their phones.

## Pre-Presentation Checklist

### One Week Before
- [ ] Do a dry run — practice building 2-3 sample apps end-to-end to get the timing down
- [ ] Print handouts — open `handout.html` in your browser and print enough copies for attendees
- [ ] Verify QR codes on printed handouts scan correctly
- [ ] Delete any test apps from dry runs (`apps/app-XX/index.html` and `config.json`)

### One Day Before
- [ ] **Make the repo public** — GitHub repo Settings > Danger Zone > Change visibility > Public
- [ ] **Enable GitHub Pages** — GitHub repo Settings > Pages > Source: "Deploy from a branch" > Branch: `main` > Folder: `/ (root)` > Save
- [ ] Verify GitHub Pages is live at https://thatsfguy.github.io/whartonRotary/
- [ ] Verify both QR codes resolve correctly (live site + repo)
- [ ] Commit and push any final changes

### Day Of (Before the Presentation)
- [ ] Pull latest changes: `git pull`
- [ ] Open 2-3 terminal windows, each `cd`'d into a different app folder:
  ```
  cd apps/app-01 && claude --dangerously-skip-permissions
  cd apps/app-02 && claude --dangerously-skip-permissions
  cd apps/app-03 && claude --dangerously-skip-permissions
  ```
- [ ] Open the landing page in a browser tab to show on screen (https://thatsfguy.github.io/whartonRotary/)
- [ ] Test that the landing page auto-polls (no manual refresh needed)
- [ ] Hand out the idea cards to attendees as they arrive
- [ ] Pro tip: **Win + H** enables Windows speech-to-text for faster dictation

### During the Hackathon
For each app idea:
1. Read the idea to the audience
2. Dictate (Win + H) or type the prompt into the next available Claude Code terminal:
   `Build a [app idea]. Requested by [name].`
3. Claude builds `index.html` + `config.json`, commits, and pushes automatically
4. Landing page auto-detects the new app within 10 seconds — no manual editing needed
5. Audience sees the new app appear on their phones

**Run multiple terminals in parallel** to build several apps simultaneously!

### After the Presentation
- [ ] Consider making the repo private again if desired

## How It Works (Technical)

The landing page (`index.html`) polls `apps/app-01/config.json` through `apps/app-10/config.json` every 10 seconds. When a `config.json` is found, the app card appears automatically. Each Claude Code instance is fully isolated — it only writes to its own folder, so there are zero merge conflicts.

### config.json format
```json
{
    "title": "App Title",
    "requestedBy": "Person's Name",
    "description": "One sentence describing what the app does."
}
```

## Repo Structure

```
index.html              ← Landing page (auto-polls for new apps)
handout.html            ← Printable handout with QR codes + idea form
README.md               ← This file
apps/
  CLAUDE.md             ← Instructions for each Claude Code instance
  app-01/
    index.html          ← The app (single self-contained file)
    config.json         ← Metadata (title, requester, description)
  app-02/
    ...
  app-10/
    ...
```

## Links

- **Live Site:** https://thatsfguy.github.io/whartonRotary/
- **GitHub Repo:** https://github.com/thatSFguy/whartonRotary
