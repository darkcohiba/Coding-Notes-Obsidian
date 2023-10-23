# Basic Commands

- Prior to initialization or running our application we can tell flask where the app.py is located or what port we want to run on

```zsh
export FLASK_APP=app.py
```

```zsh
export FLASK_RUN_PORT=5555
```

- Initialize our Flask project, this will create our migrations and instance folders

```zsh
flask db init
```

- Create revisions/migration based on the models file, both of the below commands do the same thing

```zsh
flask db revision –-autogenerate -m ‘message including table names’
```

```zsh
flask db migrate
```

- Push migrations to the DB

```zsh
flask db upgrade head
```

- Starts flask server

```zsh
flask run 
```

# Basic Tags
- #shell