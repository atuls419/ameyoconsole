# Ameyo Console

Single-page portal (`index.html`) for Ameyo campaign, user and list reporting.

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole portal |
| `users.json` | Published portal users (hashed passwords). Starts empty `[]` |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## How sign-in works
- **On this website:** the "Create the first admin" option **never appears**. People can only sign in with an account that exists in `users.json`. If `users.json` has no active admin, the site shows "Portal not configured".
- **On your own computer** (double-click `index.html`, or `localhost`): the first run lets you create the first admin. After one admin exists, that option never appears again.
- Only admins see **Users & Access** and **Activity Logs**.

## One-time setup (create the first admin)
1. Download this folder. Double-click `index.html` to open it on your PC.
2. Create the first admin account.
3. Open **Users & Access**, add your users and choose what each may see.
4. Click **⬇ users.json** and replace `users.json` in this folder with the downloaded file.
5. Commit/upload `index.html`, `users.json` and `.nojekyll` to the repository `ameyoconsole`.

## Publish on GitHub Pages
1. Create a repository named `ameyoconsole` (prefer **Private**; Pages on private repos needs a paid GitHub plan).
2. Upload the three files to the `main` branch root.
3. Repository **Settings -> Pages -> Build and deployment -> Source: Deploy from a branch -> main / (root) -> Save**.
4. Open `https://<your-username>.github.io/ameyoconsole/` after about a minute.

## Changing users later
Open the live site, sign in as admin, edit users, click **⬇ users.json**, replace the file in the repository and commit. Changes apply to everyone once the new file is live. (Edits made on the live site are kept in your browser only until you publish.)

## Important limits
- This is a static page: access rules are enforced in the browser and are a convenience, not strong security. Anyone who can reach the site and holds a valid Ameyo session could bypass them with browser tools.
- `users.json` is public if the repository/site is public. It holds names, logins, access rules and password hashes, so use strong passwords and prefer a private repository / restricted access.
- Activity logs live in each person's own browser.
- Browsers may block calls to `univoapp.ameyo.net` (CORS). Ask your Ameyo admin to allow `https://<your-username>.github.io`.
- Forgotten admin password: open the page locally, clear the site's browser data, and run the one-time setup again.
