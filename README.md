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
