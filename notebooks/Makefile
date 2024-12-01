SHELL:=/bin/bash
.DEFAULT_GOAL := help
.PHONY: help venv env renv act dact deps notebook

CURRENT_DIR:=$(shell dirname $(realpath $(lastword $(MAKEFILE_LIST))))
USER_ID:=$(shell id -u ${USER})
USER_GROUP:=$(shell id -g ${USER})
APPLICATION_ENV=.venv


help:
	@echo ''
	@echo 'Makefile for '
	@echo '     make help			show this information'
	@echo '     make env			create application virtual environment'
	@echo '     make renv			remove existing virtual environment'
	@echo '     make act			enable virtual environment. e.g.: source $(make act)'
	@echo '     make deps			install all required dependencies into virtual environment. See requirements.txt'
	@echo '     make dact			disable virtual environment. e.g.: $(make dact)'
	@echo '     make notebook		run jupyter notebook'
	@echo ''

venv:
	sudo apt install python3.10-venv

env:
	python3 -m venv $(APPLICATION_ENV)

renv:
	rm -rf $(APPLICATION_ENV)

pip:
	$(APPLICATION_ENV)/bin/pip install -U pip setuptools

act:
	$(eval ENV_ACTIVATE := $(shell echo $(CURRENT_DIR)/$(APPLICATION_ENV)/bin/activate))
	@echo $(ENV_ACTIVATE)

dact:
	@echo deactivate

deps:
	pip install -r $(CURRENT_DIR)/requirements.txt

notebook:
	$(CURRENT_DIR)/$(APPLICATION_ENV)/bin/jupyter notebook

jlab:
	$(CURRENT_DIR)/$(APPLICATION_ENV)/bin/jupyter lab