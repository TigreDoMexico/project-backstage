# Tigre Backstage

Project to test all functionalities of [Backstage](https://backstage.io) locally

## How to Start Locally

First, to compile all docs, it's required to install the following packages:

```sh
pip install mkdocs
pip install mkdocs-techdocs-core
```

Next, it's necessary to start the Postgres DB using the following docker compose command:

```sh
docker compose -f docker-compose-local.yaml up -d
```

Then, is required to insert all GitHub credentials in [app-config.yaml](./app-config.yaml) file.:
<br/>

Finally, to start the Backstage Server, run the following commands:

```sh
yarn install
yarn dev
```

## How to Run all Docker

Copy all content of app-config.docker.yaml and paste in app-config.yaml, then run the following command:

```sh
docker compose -f docker-compose.yaml up -d
```

## How to Deploy on K8s

All steps are [here](./deploy)