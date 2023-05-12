build: ## compile the source code of the application to a binary
	go build

run: ## Run the application in background by executing the binary and write logs into a file
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## Stop the application
	pgrep awesome-api | xargs kill

clean: ## Stop the application. Delete the binary awesome-api and the log file awesome-api.log
	rm awesome-api.log && rm awesome-api && make stop

test: ## test the server in local
	curl http://localhost:9999/health && curl http://localhost:9999

help: ## Show this help usage
	@fgrep -h "##" $(MAKEFILE_LIST) | sed -e 's/\(\:.*\#\#\)/\:\ /' | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'