# Learn diesel, SQL ORM

## Installation

### Requirements

- Rust/cargo
- PostgreSQL
- diesel_cli (rust package)

### Setup the Database

```bash
# Install Postgres
brew install postgres

# start Postgres database
brew services start postgresql
# and $ brew services stop postgresql # to stop

# Create main user and set role
psql postgres
# Then type this in the interactive term
> CREATE ROLE username WITH LOGIN PASSWORD 'password';
> ALTER ROLE username CREATEDB;

# Then type \q + Enter to quit.
```

### Setup project

```bash
git clone https://github.com/juliencrn/diesel_demo
cd diesel_demo

# Add the db url in env
echo DATABASE_URL=postgres://username:password@localhost/diesel_demo > .env

# Setup
diesel setup

# Create migration (if doesn't exists)
# diesel migration generate create_posts

# Exec migration
diesel migration run
diesel migration redo
```

## Usage

There are some executables to interact with the DB (CRUD)

```bash
cargo run --bin write_post
cargo run --bin show_posts
cargo run --bin publish_post {uint id}
cargo run --bin delete_post {string title}
```
