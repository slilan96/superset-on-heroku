# One Click Heroku Deploy

Superset is a data exploration platform designed to be visual, intuitive, and
interactive. Visit the project's website at <https://superset.incubator.apache.org/>

## Things you should know

### After deployment

- Superset will be accessible at `YOURAPPNAME.herokuapp.com`.
- Log in to the bash and run the following `heroku run bash`.

```{bash}
# Initialize the database
superset db upgrade

# this should have been already been set from the heroku dashboard
export FLASK_APP=superset

# Create an admin user
superset fab create-admin

# Create default roles and permissions
superset init
```

- If after adding a DB, no tables are populating, try altering this table in
the Heroku Postgres DB:

```{SQL}
ALTER TABLE table_columns ALTER COLUMN type TYPE VARCHAR(64);
```
