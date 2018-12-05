# Docker Rails Starter KIt
1. ``` docker-compose run web rails new . --force --database=postgresql ```
2. もしここで何かgemを入れたかったら、Gemfileのgrounp:developmentに記載
3. ```docker-compose build```
4. config/database.yml
```default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
  pool: 5

development:
  <<: *default
  database: myapp_development


test:
  <<: *default
  database: myapp_test 
```

5. ```docker-compose up```
6. ```docker-compose exec web rails db:create```
