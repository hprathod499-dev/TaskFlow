# TaskFlow

A Nokri Book-style task manager (single `index.html`) with Google sign-in and Firebase Realtime Database sync.

- Deploy: host `index.html` on any static host (Netlify, GitHub Pages, Firebase Hosting).
- Firebase: enable Google sign-in, create a Realtime Database, publish `database.rules.json`, and add your site's domain under Authentication > Settings > Authorized domains.

## Google Drive backup

Settings > Google Drive backup saves a copy of all tasks to a "TaskFlow Backups" folder in the signed-in user's Drive
(scope `drive.file`, only files this app creates). Requires the **Google Drive API** to be enabled for the Firebase/Google Cloud project.

## Data storage

All data (tasks, history, chapters) is kept permanently in the signed-in user's Firebase account. There is no 7-day limit. Google Drive backup (Settings) saves a full copy that can be restored on a new device; older items that earlier versions archived on a device are moved back to the live list automatically.

## Study planner pages

- **Today's task, Task calendar, Upcoming, Filters & Labels, Completed**: the main task views. Task calendar is a month grid with a day panel for the tapped day (tasks, reminders, exam days).
- **My Subjects**: folders hold subjects. Tasks belong to a subject; a folder page shows all tasks of its subjects.
- **Manage Book**: keep a list of books and link tasks to a book from the task window.
- **Event & Reminder**: reminders with date, time and repeat. They alert while TaskFlow is open (and as a system notification if allowed); a web page cannot ring when it is closed.
- **Exam plan**: exams with a countdown and progress (finished tasks in the chosen subjects).
