#!make
include .env
export $(shell sed 's/=.*//' .env)

login:
	$$(aws ecr get-login --no-include-email --region us-east-1)

init:
	docker-compose pull
	docker-compose up -d --build
	@echo "System ready!"

pull:
	docker-compose pull
	docker-compose up -d

	docker-compose restart

	@echo "System updated"

update: login pull
