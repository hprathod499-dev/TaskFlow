# TaskFlow

A Nokri Book-style task manager (single `index.html`) with Google sign-in and Firebase Realtime Database sync.

- Deploy: host `index.html` on any static host (Netlify, GitHub Pages, Firebase Hosting).
- Firebase: enable Google sign-in, create a Realtime Database, publish `database.rules.json`, and add your site's domain under Authentication > Settings > Authorized domains.

## Google Drive backup

Settings > Google Drive backup saves a copy of all tasks to a "TaskFlow Backups" folder in the signed-in user's Drive
(scope `drive.file`, only files this app creates). Requires the **Google Drive API** to be enabled for the Firebase/Google Cloud project.

## Weekly archive

Completed tasks and activity older than 7 days are kept off the live site to keep it fast and inside the free Firebase limits.

- Open tasks always stay live on every device.
- Every 7 days the app asks for a Google Drive backup before it moves older completed work off the live list. Nothing is removed until Drive confirms the upload.
- Each backup file holds the live tasks plus the full archive, so the newest file is all you need to restore.
- The archive is kept on each device in the browser (IndexedDB) and shown under Activity, Older history.
- Restoring on a new device adds missing tasks and puts anything older than 7 days into that device's archive.

## Study planner pages

- **Today's task, Task calendar, Upcoming, Filters & Labels, Completed**: the main task views. Task calendar is a month grid with a day panel for the tapped day (tasks, reminders, exam days).
- **My Subjects**: folders hold subjects. Tasks belong to a subject; a folder page shows all tasks of its subjects.
- **Manage Book**: keep a list of books and link tasks to a book from the task window.
- **Event & Reminder**: reminders with date, time and repeat. They alert while TaskFlow is open (and as a system notification if allowed); a web page cannot ring when it is closed.
- **Exam plan**: exams with a countdown and progress (finished tasks in the chosen subjects).
