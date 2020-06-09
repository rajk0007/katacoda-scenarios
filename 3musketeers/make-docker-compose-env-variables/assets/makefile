COMPOSE_RUN_MUSKETEERS = docker-compose run --rm musketeers
ENVFILE ?= env.template

envfile:
	cp -f $(ENVFILE) .env

shell: 
	$(COMPOSE_RUN_MUSKETEERS) sh -l