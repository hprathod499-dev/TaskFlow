# TaskFlow

A Todoist-style task manager (single `index.html`) with Google sign-in and Firebase Realtime Database sync.

- Deploy: host `index.html` on any static host (Netlify, GitHub Pages, Firebase Hosting).
- Firebase: enable Google sign-in, create a Realtime Database, publish `database.rules.json`, and add your site's domain under Authentication > Settings > Authorized domains.

## Google Drive backup

Settings > Google Drive backup saves a copy of all tasks to a "TaskFlow Backups" folder in the signed-in user's Drive
(scope `drive.file`, only files this app creates). Requires the **Google Drive API** to be enabled for the Firebase/Google Cloud project.
