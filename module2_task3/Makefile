build: ## compile the source code of the application to a binary
	make lint && go build

run: ## Run the application in background by executing the binary and write logs into a file
	./awesome-api > ./awesome-api.log 2>&1 &

stop: ## Stop the application
	pgrep awesome-api | xargs kill

clean: ## Stop the application. Delete the binary awesome-api and the log file awesome-api.log
	-make stop
	-rm awesome-api.log && rm awesome-api
	rm coverage-units.out && coverage-integrations.out

test: ## test the server in local
	curl http://localhost:9999/health && curl http://localhost:9999

lint: ## detect all arrors
	golangci-lint run

unit-tests: ## check unit-tests
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## check integration tests
	go test -v -coverprofile=coverage-integrations.out

help: ## Show this help usage
	@fgrep -h "##" $(MAKEFILE_LIST) | sed -e 's/\(\:.*\#\#\)/\:\ /' | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'