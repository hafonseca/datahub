# Makefile

DOCKER_NETWORK=ds-net

# Check if the Docker network exists, if not, create it
check-network:
	@if [ -z "$$(docker network ls --filter name=$(DOCKER_NETWORK) -q)" ]; then \
		echo "Network '$(DOCKER_NETWORK)' not found. Creating network..."; \
		docker network create $(DOCKER_NETWORK); \
	else \
		echo "Network '$(DOCKER_NETWORK)' already exists."; \
	fi

# Bring up the Docker services after ensuring the network exists
up: check-network
	docker compose up -d

# Bring down the services
down:
	docker compose down
