### DB Management

Enter DB:
```sh
❯ psql "postgres://greenlight:pa55word@localhost:6543/greenlight"
```

### Migrations

Create a migration:
```sh
❯ migrate create -seq -ext=.sql -dir=./migrations add_movies_check_constraints
```

Execute up migrations:
```sh
❯ migrate -path=./migrations -database='postgres://greenlight:pa55word@localhost:6543/greenlight?sslmode=disable' up
```

Execute down migrations (just one step down):
```sh
❯ migrate -path=./migrations -database='postgres://greenlight:pa55word@localhost:6543/greenlight?sslmode=disable' down 1
```

Force the DB to a specific version (useful for when you have a broken migration that was partially applied):
```sh
❯ migrate -path=./migrations -database='postgres://greenlight:pa55word@localhost:6543/greenlight?sslmode=disable' force 1
```
