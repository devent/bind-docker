include ../docker-make-utils/Makefile.help
include ../docker-make-utils/Makefile.functions
include ../docker-make-utils/Makefile.container

# Container name.
NAME := bind

VERSION := 9.9.5-20170129

IMAGE_NAME := sameersbn/bind:$(VERSION)

PORTS := -p 53:53/tcp -p 53:53/udp -p 10000:10000/tcp

DATA_DIR := /var/bind

# Docker command to create the container.
define DOCKER_CMD :=
docker run \
-d \
--name $(NAME) \
$(PORTS) \
-v "$(DATA_DIR):/data" \
$(IMAGE_NAME)
endef

.PHONY: run
run: setup _run ##@default Starts the container.

.PHONY: rerun
rerun: _rerun ##@targets Stops and starts the container.

.PHONY: stop
stop: _stop ##@targets Stops the container.
	sudo rm -rf $(DATA_DIR)

.PHONY: rm
rm: _rm ##@targets Stops and removes the container.

.PHONY: clean
clean: _clean ##@targets Stops and removes the container and removes all created files.
	sudo rm -rf $(DATA_DIR)

.PHONY: test
test: _test ##@targets Tests if the container is running.
	
.PHONY: restart
restart: _restart ##@targets Restarts the container.

.PHONY: setup
setup:
	sudo mkdir -p "$(DATA_DIR)"
	sudo chmod o+rwX "$(DATA_DIR)"
