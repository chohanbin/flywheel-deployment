# Flywill Trading App

<img width="297" alt="Screenshot 2024-06-09 at 10 07 19 PM" src="https://github.com/chohanbin/flywheel-deployment/assets/5660356/1f062af3-d511-4e73-ba1b-065f79254baa">
<br/>
<br/>
Tiny actions compounded over time leads to remarkable results, like the momentum of a flywheel!
Flywill Trading App is the haven for your big dreams, packed with features to keep your actions compounding in the right direction! You will see your will fly! 🪽
<br/>
<br/>
In truth, this app is not there yet. But! It has taken an important step. Being born! Tiny actions from here on out, compounded over time will indeed lead to great results. 😎
<br/>
<br/>
This app lets the beta customers registered on [Sample Analytics Dataset](https://www.mongodb.com/docs/atlas/sample-data/sample-analytics/#sample-analytics-dataset) to view their transaction history for each acccount. You can play with it too, if you have a [Sample Analytics Dataset](https://www.mongodb.com/docs/atlas/sample-data/sample-analytics/#sample-analytics-dataset) to connect to!

This app was built with:
- Backend: Node.js, TypeScript, [Apollo GraphQL Server](https://www.apollographql.com/docs/apollo-server/), [MongoDB Node Driver](https://www.mongodb.com/docs/drivers/node/current/)
- Frontend: Node.js, TypeScript, [Next.js React Framework](https://nextjs.org/), [Apollo GraphQL Client](https://www.apollographql.com/docs/react/)

## Setup

This repo allows launching the entire app with one command, `docker-compose up`.
- If you'd like to launch each service of this app separately, please checkout:
  - [flywheel-data-service/README.md](https://github.com/chohanbin/flywheel-data-service/blob/main/README.md)
  - [flywheel-web-service/README.md](https://github.com/chohanbin/flywheel-web-service/blob/main/README.md)
- Otherwise, let's set this up! You only need to do this one on your machine.

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

Set this secret to `AUTH_SECRET` key in `.env` file.
Also, specifiy which MongoDB the data service should target, by setting `DB_CONN_STRING`:

```shell
# .env
AUTH_SECRET=your-new-secret
DB_CONN_STRING='mongodb+srv://...'
```

### Build and run services
```shell
docker-compose up
```

### Interact with the app

Once the app is deployed,
- Play with Data Service API at <http://localhost:4000>
- Play with the Web App at <http://localhost:3000>

Here's a demonstration of:
- Launching the app with `docker-compose up`
- Fetching a customer data by their `email` from the Data Service API
  - Don't worry, the data shown in the video is fake. Try looking up their home address.
- Logging into the Web App with their `email`
https://github.com/chohanbin/flywheel-deployment/assets/5660356/dab6b3c3-3ba3-458e-b23d-59e588e89292

Here's a demonstration of:
- Fetching transactions by the customer's `accountId` from the Data Service API
- Using the Web App to fetch the same transactions for the same `accountId`

https://github.com/chohanbin/flywheel-deployment/assets/5660356/8c4de6dd-2479-4f62-9786-5936ee652af6

Try it out yourself!
Play with the data found in your [Sample Analytics Dataset](https://www.mongodb.com/docs/atlas/sample-data/sample-analytics/#sample-analytics-dataset).
- On how to play with Data Service API, see [flywheel-data-service/README.md](https://github.com/chohanbin/flywheel-data-service?tab=readme-ov-file#supported-graphql-apis)
- On how to play with Web App, check out the videos above!


### Stop the service
```shell
docker-compose down
```

# Author
Hanbin Cho
