# Flywheel Trading App - Full Stack Deployment

This repo allows launching the mighty Flywheel Trading App with one command, using `docker-compose up`.

This avoids having to launch each service of the App individually. But if you'd prefer to launch them separately, follow these instructions.
- Launching Data Service: https://github.com/chohanbin/flywheel-data-service/blob/main/README.md
- Launching Web Service: https://github.com/chohanbin/flywheel-web-service/blob/main/README.md

Otherwise, let's set this up! You only need to do this setup once!

## Setup

### Clone this Repository
```shell
git clone git@github.com:chohanbin/flywheel-deployment.git
cd flywheel-deployment
```

### Initialize submodules
```shell
git submodule init
git submodule update
```

### Create .env file for environment variables

Create `.env` file
```shell
touch .env
```

Store a secret that the user authentication service should use.
Generate a new secret with:
```shell
openssl rand -base64 32
```

In `.env` file, set the secret to `AUTH_SECRET` var.
Also, specifiy which MongoDB the data service should target, by setting `DB_CONN_STRING`:

```shell
# .env
AUTH_SECRET=your-secret-key
DB_CONN_STRING='mongodb+srv://...'
```

### Build and run services
```shell
docker-compose up --build
```

### Interact with the app

- Play with Data Service API at <http://localhost:4000/graphql>
- Play with the Web App at <http://localhost:3000> 

### Stop the service
```shell
docker-compose down
```

