Please read https://sequelize.readthedocs.io/en/latest/docs/migrations/

**Never execute DB alter scripts directly and manually.** All changes to the database must have corresponding sequelize migrate scripts which must be committed in git.

## Execute DB Migration
To migrate the DB, use the command `npx sequelize-cli db:migrate`.

To migrate the QA environment, use `npx sequelize-cli db:migrate --env qa`

## Alter Table Structure

1. Create a new file in db/migrations/. Include the date in the filename (pattern: `<YYYYMMDDHHMMSS>-<change/create/remove>-<table name>-<columns / short desc>.js`)
2. Use sequelize to change table structure. (Please check [Sequelize DB Migration Doc](http://docs.sequelizejs.com/manual/migrations.html) and [QueryInterface API](http://docs.sequelizejs.com/class/lib/query-interface.js~QueryInterface.html) for more details)
3. Execute the Sequelize DB migration command