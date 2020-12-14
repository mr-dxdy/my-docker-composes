up:
	docker-compose up -d

down:
	docker-compose down

syntax:
	docker-compose exec nginx nginx -t

reload:
	docker-compose exec nginx nginx -s reload 

tail:
	docker-compose logs nginx -t

create_self_ssl:
	openssl req -newkey rsa:4096 -nodes -sha256 -keyout certs/domain.key -x509 -days 365 -out certs/domain.crt
