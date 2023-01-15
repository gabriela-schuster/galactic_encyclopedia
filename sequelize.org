#+TITLE:sequelize

* generate migration
npx sequelize-cli migration:generate --name 'name-here'

* do migration
npx sequelize-cli db:migrate --name 'name-here'

* undo migration
npx db:migrate:undo --name 'name-here'
db:migrate:undo:all

* migrate
npx sequelize-cli db:migrate

* generate model and migration for it
npx sequelize-cli model:generate --name outlookAccount --attributes accessToken:string,expiresOn:date,smtpId:integer,clientId:integer
