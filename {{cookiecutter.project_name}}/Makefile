.PHONY: help check clean all base dev upgrade

help:
	@echo 'Usage:'
	@sed -n 's/^##//p' ${MAKEFILE_LIST} | column -t -s ':' | sed -e 's/^/ /'

## check: check pip-tools installed
check:
	@if ! command -v pip-compile > /dev/null; then echo "pip-tools not installed!"; fi

## clean: clean all *.txt files
clean: check
	- rm *.txt

## all: build all .txt files
all: base dev

## base: build requirements.txt
base: pyproject.toml
	pip-compile --verbose --generate-hashes --output-file requirements.txt $<

## dev: build dev-requirements.txt
dev: pyproject.toml base
	pip-compile --verbose --extra dev --generate-hashes --output-file dev-requirements.txt $<

## pip.install: install all dependencies
pip.install: requirements.txt dev-requirements.txt
	pip-sync --ask requirements.txt dev-requirements.txt

## pip.install-base: install base dependencies only
pip.install-base: requirements.txt
	pip-sync --ask requirements.txt

## pip.upgrade: upgrade base dependencies only
pip.upgrade: requirements.txt
	pip-compile --upgrade --generate-hashes $<
