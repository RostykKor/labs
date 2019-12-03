.DEFAULT_GOAL := all

all: install test run deploy

install:
	@echo "Installing pipenv and dependencies..."
	@pip install pipenv
	@pipenv --python 3.7
	@pipenv install requests
	@pipenv install pytest

test:
	@echo "\n"
	@echo "Starting tests..."
	@pipenv run pytest tests/tests.py | tee results.txt

run:
	@echo "\n"
	@echo "Running Python app..."
	@pipenv run python app.py | tee -a results.txt
	
deploy:
	@echo "\n"
	@echo "Adding and Committing results.txt to git..."
	@git add results.txt
	@git commit -m "Auto pushing results.txt"
	@git push origin master
