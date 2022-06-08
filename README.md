# WordPress website (Apache/PHP and MariaDB) with Docker

A WordPress based website and local Docker-based development environment. 


## Directory/file structure:

* `app/` – The WordPress application files are in this directory.
* `db_data/` – MariaDB dump files go here.
* `docker/` – Files required by the Docker setup are in this directory.
* `README.md` – Every project needs a README!
* `docker-compose.yml` – Development orchestration config file.

## File `/app/wp-config.php`

```php
// ...
/** The name of the database for WordPress */
define('DB_NAME', $_SERVER['DB_NAME'] ?? $_ENV['DB_NAME'] ?? null);
 
/** MariaDB database username */
define('DB_USER', $_SERVER['DB_USER'] ?? $_ENV['DB_USER'] ?? null);
 
/** MariaDB database password */
define('DB_PASSWORD', $_SERVER['DB_PASSWORD'] ?? $_ENV['DB_PASSWORD'] ?? null);
 
/** MariaDB hostname */
define('DB_HOST', $_SERVER['DB_HOST'] ?? $_ENV['DB_HOST'] ?? null);
// ...
```

```php
// ...
define('WP_DEBUG', (bool) ($ENV['WP_DEBUG'] ?? false));
define('WP_DEBUG_LOG', (bool) ($ENV['WP_DEBUG'] ?? false));
// ...
```


## Installation

Create a new .env file from example and change APP_NAME 

```bash
cp .env-example .env
```


## Start up

Start up with:

```bash
docker-compose up
```

Go to http://localhost:8000 and start work.

To rebuild the containers:

```bash
docker-compose up --force-recreate --build
```

To delete the `db_data` volume:

```bash
docker-compose down -v
```
## Ports
Web 8000
DB 3306

You can change the ports on .env file