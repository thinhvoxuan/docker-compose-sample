bootstrap: 
	make build && make up && make composer-install

build:
	docker-compose build --no-cache

up:
	docker-compose up -d --force-recreate

ssh:
		docker-compose exec php-fpm /bin/bash

composer-install:
		docker-compose exec php-fpm /bin/bash -c "cd /application/blog && composer install" 
	
composer-update:
		docker-compose exec php-fpm /bin/bash -c "cd /application/blog && composer install" 