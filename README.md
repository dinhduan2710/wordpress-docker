# Wordpress Docker Compose
A simple docker-compose setup for Wordpress development

## Quick start
```

# Change working directory
cd wordpress-docker

# Start containers
docker-compose up -d

# Stop containers
docker-compose stop

# Remove containers
docker-compose rm
```

## Configuration

### MYSQL root password
By default the root mysql password will be `rootpassword`, this can be changed in the docker-compose file

```
mysql:
  environment:
    MYSQL_ROOT_PASSWORD: rootpassword

wordpress:
  environment:
    WORDPRESS_DB_USER: root
    WORDPRESS_DB_PASSWORD: rootpassword
```

### MYSQL database name
By default the database name will be `mywordpresssite`, this can be changed in the docker-compose file

```
mysql:
  environment:
    MYSQL_DATABASE: mywordpresssite

wordpress:
  environment:
    WORDPRESS_DB_NAME: mywordpresssite
```

## Theme development
If you're only looking to develop themes, update the docker-compose file with:
```
wordpress:
  volumes:
    - ./src/wp-content/themes/theme_name/:/var/www/html/wp-content/themes/theme_name/
```

## Plugin development
If you're only looking to develop plugins, update the docker-compose file with:
```
wordpress:
  volumes:
    - ./src/wp-content/plugins/plugin_name/:/var/www/html/wp-content/plugins/plugin_name/
```
## site

### front-end: localhost:8080
### backend: localhost:8080/wp-admin
### phpMyadmin: 