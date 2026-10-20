# AGENTS.md

Instructions for an AI agent working in this repo.

This is a Rails app for learning Ruby and databases. Run everything from the top folder (where
README.md is).

- Run a Ruby file with `bin/rails runner <path>`. Run the tests with `bin/rails test`.
- Change the database's structure only with a migration: `bin/rails generate model` or
  `bin/rails generate migration`, then `bin/rails db:migrate`. Never edit `db/schema.rb`;
  Rails writes it.
- `bin/reset-db` rebuilds the database from the migrations and deletes every row. Ask before
  running it.
- Explain what you changed in plain English, file by file.
