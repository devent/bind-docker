include ../docker-make-utils/Makefile.help
include ../docker-make-utils/Makefile.functions

export NAME := bind
export VERSION := 9.9.5-20170129
export IMAGE := sameersbn/$(NAME):$(VERSION)

SHELL := /bin/bash
.DEFAULT_GOAL := run

.PHONY: run
run: setup ##@targets Starts the containers.
	docker-compose -p $(NAME) -f compose.yaml up

.PHONY: stop
stop: ##@targets Stops the containers.
	docker-compose -p $(NAME) -f compose.yaml stop

.PHONY: rm
rm: stop ##@targets Stops the containers.
	docker-compose -p $(NAME) -f compose.yaml rm -f

.PHONY: clean
clean: stop rm ##@targets Removes docker containers and created files.
	sudo rm -rf root

.PHONY: setup
setup:
	for p in bind; do \
	mkdir -p root/$$p; \
	chmod o+rwX root/$$p ; \
	done
