# Student Management GUI

A simple student management web application built with Flask and MySQL, featuring a clean GUI for adding, viewing, and deleting student records — including profile photo uploads.

## Features

- **Add students** — name, class, and a profile photo upload
- **View all students** — dashboard listing every student with their photo and class
- **Delete students** — remove a student record (and their uploaded photo) with one click
- **Automatic image handling** — uploaded photos are saved with unique generated filenames to avoid overwrites
- **Auto-creates database table** — the `students` table is created automatically on first run if it doesn't exist

## Tech Stack

- **Backend:** Python, Flask
- **Database:** MySQL
- **Frontend:** HTML, Jinja2 templates

## Project Structure

```
Student-Management-GUI/
├── app.py                  # Main Flask application (routes + MySQL logic)
├── templates/
│   └── index.html           # Dashboard — add/view/delete students
└── static/
    └── uploads/              # Uploaded student photos (auto-created)
```

## Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install flask mysql-connector-python
   ```
3. Create the database in MySQL:
   ```sql
   CREATE DATABASE STUDENT_MANAGEMENT;
   ```
4. Update your MySQL credentials in `app.py`:
   ```python
   db_host = "localhost"
   db_user = "root"
   db_password = "your_password_here"
   db_name = "STUDENT_MANAGEMENT"
   ```
5. Run the application:
   ```bash
   python app.py
   ```
6. Open `http://127.0.0.1:5000` in your browser

## How It Works

1. Fill in a student's **name**, **class**, and upload a **photo** on the dashboard
2. The student is added to the list, with their photo stored in `static/uploads/`
3. Click delete next to any student to remove their record and photo
4. The `students` table is created automatically the first time the app runs

## Notes

- Database credentials are hardcoded in `app.py` for simplicity — consider moving them to environment variables before deploying or pushing publicly.
- A single shared MySQL connection/cursor is used at startup; for production use, consider connection pooling or per-request connections.

## Future Improvements

- Edit existing student records
- Search/filter students by name or class
- Pagination for large student lists
- Move database credentials to a `.env` file

## License

MIT License — feel free to fork, modify, and share.
