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
