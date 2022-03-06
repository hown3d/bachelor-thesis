all: up browser

@PHONY: up
up:
	podman run --replace --name presentation --rm -d -p 1948:1948 -v $(shell pwd):/slides webpronl/reveal-md:latest

@PHONY: browser
browser:
	open http://localhost:1948/presentation.md#/