# php-docker-compose
Docker Compose for PHP development environment

## Usage

1. Copy `docker-compose.yml` and `.env` to your php project.

2. Start containers in the background. This command creates containers if don't exist or recreates them if `docker-compose.yml` has been modified.

    ```bash
    docker-compose up -d
    ```

3. Access your app via [http://localhost/](http://localhost/). Access your bd via `phpmyadmin` [http://localhost:8080/](http://localhost:8080/) or connect via port 3306 with `mysql-workbench` or similar software.

_Execute `docker-compose help` for more commands_

## Environment variables

You can use `.env` file to change versions and define mysql variables. 

## Create a new Project with Composer

#### Silex

```bash
docker run --rm -v $(pwd):/app -u $(id -u):$(id -g) composer/composer create-project silex/silex .
```

#### Symfony

```bash
docker run --rm -v $(pwd):/app -u $(id -u):$(id -g) composer/composer create-project symfony/framework-standard-edition .
```

## Install composer packages

```bash
docker run --rm -v $(pwd):/app -u $(id -u):$(id -g) composer/composer install
```
