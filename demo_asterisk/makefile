.PHONY: help
help: ## Show this help message.
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'

.PHONY: run-docker
run-docker: ## Run the app in a docker container.
	docker-compose -f docker-compose.yml up -d

.PHONY: kill-docker
kill-docker: ## Stop the running docker container.
	docker-compose -f docker-compose.yml down