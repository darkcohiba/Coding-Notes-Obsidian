
# Basic Commands

- Creates alembic ini and folder structure, should be inside DB when you run this maybe

```zsh
alembic init migrations
```

- First commit with nothing built out

```zsh
alembic revision -m ‘empty init’
```


- Creates new migration file, should be inside DB when you run this

```
alembic revision –autogenerate -m ‘message’
```

- Push migration to the DB

```
alembic upgrade head
```

# Basic Tags
- #CLI 
