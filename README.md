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

### When pushing your DB on prod environnement 
* use ```rake db:schema:load``` instead of rake db:migrate  


### When you want to drop your db and receive this message :
```PG::ObjectInUse: ERROR:  database "your_database" is being accessed by other users```

In your psql console, type this :
```SELECT pid, pg_terminate_backend(pid) as terminated FROM pg_stat_activity WHERE pid <> pg_backend_pid();```

### To access to your database console with rails command line
``` rails dbconsole ```

