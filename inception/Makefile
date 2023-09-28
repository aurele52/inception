up:
	mkdir -p ~/data/mariadb
	mkdir -p ~/data/wordpress

	docker compose -f ./srcs/docker-compose.yml up --build -d

down:
	docker compose -f ./srcs/docker-compose.yml down

clean:
	docker builder prune -a
	docker system prune -a

show:
	docker ps
	docker volume ls -q
	docker container ls -q

renew:
	make down
	docker volume rm srcs_mariadb-vol
	docker volume rm srcs_wordpress-vol
	sudo rm -rf /home/athierry/data
	make clean
	make up

see:
	docker logs wordpress
	docker logs mariadb
	docker logs nginx

restart:
	make down
	make up

.PHONY: up down clean show renew see restart
