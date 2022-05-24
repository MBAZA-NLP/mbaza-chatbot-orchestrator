.PHONY: help
help: ## Show this help message.
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'


.PHONY: run-docker
run-docker: ## Run the app in a docker container.
    docker run -d --restart unless-stopped -p 8000:8000 rasa/duckling
    docker run -d --restart unless-stopped -p 5056:5055 rasa/financial-demo
#     cd /root/dorin/financial-demo && source venv/bin/activate && rasa run --enable-api --cors "*" -p 5005
	docker-compose -f docker-compose.yml up -d

.PHONY: kill-docker
kill-docker: ## Stop the running docker container.
    docker stop rasa/duckling
    docker stop rasa/financial-demo
	docker-compose -f docker-compose.yml down