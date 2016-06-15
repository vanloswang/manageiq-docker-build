build:
	docker build -t alpine-postgresql --rm=true .

debug:
	docker run -i -t --entrypoint=sh alpine-postgresql

run:
	docker run -i -P alpine-postgresql
