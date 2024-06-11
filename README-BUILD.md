## Label-studio
```
git clone https://github.com/PRNDcompany/label-studio.git
```

## run
```
# .env
# LABEL_STUDIO_URL=http://localhost:8080
# LABEL_STUDIO_API_KEY=
# LABEL_STUDIO_LOCAL_FILES_SERVING_ENABLED=true
# LABEL_STUDIO_LOCAL_FILES_DOCUMENT_ROOT=/data2
```
```
export $(grep -v '^#' .env | xargs)
```
```
cd label-studio
poetry install

# run db migrations
poetry run python label_studio/manage.py migrate

# collect static files
poetry run python label_studio/manage.py collectstatic

# start the server in development mode
poetry run python label_studio/manage.py runserver
```

### build frontend
```
cd web
yarn
```

- real time watch
    ```
    yarn ls:watch
    ```

    ```
    # new terminal
    yarn lsf:watch
    ```

- build
    ```
    yarn build
    ```