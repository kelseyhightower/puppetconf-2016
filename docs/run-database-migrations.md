# Run Database Migrations

## Run the Rails database migrations

Create the database schema job:

```
kubectl create -f jobs/lobsters-db-schema-load.yaml
```

Create the database seed job:

```
kubectl create -f jobs/lobsters-db-seed.yaml
```

Once the `lobsters-db-seed` job completes you'll be able to login to the lobsters UI using the following credentials:

```
username: test
password: test
```
