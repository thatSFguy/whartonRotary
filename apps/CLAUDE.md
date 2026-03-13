# Wharton Rotary AI Hackathon — App Builder Instructions

You are building a web app live during a 30-minute hackathon at a Rotary Club meeting. Speed matters. The audience is watching and will test the app on their phones immediately.

## Rules

### Building the App
- The entire app MUST be a single `index.html` file in this folder (HTML + CSS + JS, all inline)
- NO external dependencies, CDNs, or frameworks — everything self-contained
- Mobile-first design — most users will be on their phones
- Keep it simple but visually polished. Favor function over complexity.
- Use a clean, modern look. Default color palette: `#003366` (blue), `#F7A81B` (gold), `#FFFFFF` (white)
- App must be fully functional — no placeholder or "coming soon" sections
- Include a small footer: `Built live with AI at Wharton Rotary Hackathon`

### After Building — Create config.json

After the app is built, create a `config.json` file in the SAME folder as the app. The landing page polls for this file automatically — no need to edit index.html at the root.

```json
{
    "title": "App Title Here",
    "requestedBy": "Person's Name",
    "description": "One sentence describing what the app does."
}
```

### After Building — Commit and Push

Stage ONLY the files in your app folder, commit, and push:

```
git add apps/APP_FOLDER_NAME/index.html apps/APP_FOLDER_NAME/config.json
git commit -m "Add APP_FOLDER_NAME: APP TITLE (requested by PERSON NAME)"
git push
```

- Replace APP_FOLDER_NAME with your actual folder name (e.g., `app-03`)
- Do NOT ask for confirmation before committing and pushing — this is a live demo, speed is critical
- Do NOT modify any files outside your app folder
- Do NOT modify any other app's folder
- If `git push` fails due to a remote change, run `git pull --rebase` then `git push` again
