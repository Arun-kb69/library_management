# Library Management — SQL Schema

A PostgreSQL schema for a simple **Library Management** system.  
This project defines tables for users, authors, publishers, books, staff, readers, book issues, and basic settings.

> ⚠️ This SQL file is written for **PostgreSQL** and uses `SERIAL`, schema-qualified table names, and `CASCADE` in the `DROP SCHEMA` statement.

---

## Contents

- `library_management.sql` — main schema file (creates schema + tables)
- `README.md` — this file
- (optional) `.gitignore`, sample data files, and docs

---

## Schema summary

Schema name: `library_management`

Tables:
- `user_login` — users and credentials (currently stores `user_password` as TEXT; **hash passwords** before inserting in production)
- `publisher` — publisher details
- `author` — authors and publication counts
- `books` — book records (FK → `author`, `publisher`)
- `staff` — library staff and shifts
- `readers` — people who borrow books
- `books_issue` — issue / return records (references `books` and `readers`)
- `settings` — global settings (issue limit, fine per day, return period)

---

## Quickstart — Run locally (PgAdmin GUI)

1. Install PostgreSQL (includes `psql`) and PgAdmin (if not already installed).  
   https://www.postgresql.org/download/

2. Open PgAdmin → connect to your local server.

3. Create a new database:
   - Right click **Databases** → **Create** → set `Name` to `library_db` (or any name) → Save.

4. Open Query Tool for `library_db`:
   - Right click the database → **Query Tool**.

5. Paste the contents of `library_management.sql` and click **Run (▶)**.

6. Verify:
   - In PgAdmin: `library_db → Schemas → library_management → Tables`.

---

## Quickstart — Run from terminal (psql)

1. Save `library_management.sql` to a local folder.

2. Create a database (if not already):
```bash
createdb library_db
