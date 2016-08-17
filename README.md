###Docker Commands
- `docker network ls`
- `docker network create --subnet=172.18.0.0/16 psnet`
- `docker build -f Dockerfile-dataservice -t ps/dataservice .`
- `docker images`
- `docker run --name dataservice --ip=172.18.0.10` --net=psnet -P --rm -it ps/dataservice
- `docker build -f Dockerfile-web -t ps/web .`
- `docker run --name web --ip=172.18.0.11 --net=psnet -P --rm -it -- ps/web --dataservice=http://172.18.0.10:4000`