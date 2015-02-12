##Table of contents

* [Rspec](#rspec)
	* [Refreshing RSPEC every 2sec](#refreshing-rspec-every-2sec)
* [Database](#database)
	* [Load db structure from your schema](#load-db structure-from-your-schema)
	* [When you want to drop your db and receive this message](#when-you-want-to-drop-your-db-and-receive-this-message)
	* [To access to your database console with rails command line](#to-access-to-your-database-console-with rails-command-line)
	* [To import file into your db](#to-import-file-into-your-db)
	
### Refreshing RSPEC every 2sec

* add spec_helper.rb file with this script:
```RSpec.configure do |config|
  config.color = true
  config.tty = true
  config.formatter = :documentation # :progress, :html, :textmate
end```

* Add require './spec_helper' to your spec file

* Run this command in your shell:
```watch --color bash rspec```

## Database

### Load db structure from your schema
* use ```rake db:schema:load``` instead of rake db:migrate  


### When you want to drop your db and receive this message
```PG::ObjectInUse: ERROR:  database "your_database" is being accessed by other users```

In your psql console, type this :
```SELECT pid, pg_terminate_backend(pid) as terminated FROM pg_stat_activity WHERE pid <> pg_backend_pid();```

### To access to your database console with rails command line
``` rails dbconsole ```

### To import file into your db
```psql -h IP_ADDRESS -p 5432 -U app -d DATABASE_NAME -f your_file_name.sql```