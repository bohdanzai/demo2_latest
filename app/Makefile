TAG               ?= v1
REPO_REGION       ?= us-east-2
ECR_REPO_URL      ?= 873432059572.dkr.ecr.us-east-2.amazonaws.com
APP_NAME          ?= demo2
ENV_NAME          ?= dev

.PHONY: build
build:
	aws ecr get-login-password --region $(REPO_REGION) | docker login --username AWS --password-stdin $(ECR_REPO_URL)
	docker build -t $(APP_NAME)-$(ENV_NAME):$(TAG) .
	docker tag $(APP_NAME)-$(ENV_NAME):$(TAG) $(ECR_REPO_URL)/$(APP_NAME)-$(ENV_NAME):$(TAG)
	docker push $(ECR_REPO_URL)/$(APP_NAME)-$(ENV_NAME):$(TAG)