# Backend API for ACM website

### Steps to install and get running
1. Install the dependencies

   ```
   yarn install
   ```
   *You may use npm instead of yarn*

2. Install the cross-env package globally

   *Note that on linux systems this will need to be done as __sudo__*
   ```
   npm install -g cross-env
   npm install -g sequelize-cli
   npm install -g (mysql2 or sqlite3)
   ```

3. Ensure the database is running on your computer whether it is mysql or
another supported dialect
   + Following the global installs in step 2 run the Following
   ```
   sequelize init:config
   sequelize db:create
   sequelize db:migrate
   ```
   + Note: If you are getting an error about not finding migrations, create a migrations folder with ``` mkdir migrations ``` and you should be fine.
   + Note if you are using sqlite3 you should create a data folder and edit your database-config.json for development to be the following:
   ```
   development: {
     "storage": "data/dev-db.sqlite3",
     "dialect": "sqlite"
   }
   ```
   + Then you need to create the data folder and create the sqlite3 database with the following commands:
   ```
   mkdir data
   sqlite3 data/dev-db.sqlite3
   ```
   + This will create the database. (Note you must have done npm install -g sqlite3 earlier to do this)
4. **Optional:** If you wish to set up the envirment for testing and for using
squelize install the following globally

    *Note that on linux systems this will need to be done as __sudo__*

     ```
     npm install -g eslint
     npm install -g eslint-config-google
     ```
