export AWS_ACCESS_KEY_ID := $(shell terraform output -state terraform/terraform.tfstate publish-user-access-key)
export AWS_SECRET_ACCESS_KEY := $(shell terraform output -state terraform/terraform.tfstate publish-user-secret-key)

.PHONY: build push

build:
    hugo -b http://dotariel.com/
dev:
    hugo server -t ghostwriter -b http://localhost:1313/ --buildDrafts
push: build
    aws s3 sync public/ s3://dotariel.com/
