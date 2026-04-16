# waf-safeline
# First of all main controll install or remove
```
bash -c "$(curl -fsSLk https://waf-ce.chaitin.cn/release/latest/manager.sh)" -- --en
```
# Step for romve all
## check docker
```
docker ps -a | grep safeline
docker images | grep chaitin
```
## remove folder install and docker (default)
```
rm -rf /opt/safeline
rm -rf ~/.docker/safeline
rm -rf /data/safeline
```
## verify the remove docker
```
docker compose down
```
## Optional check residue docker
```
docker images | grep chaitin-safeline | awk '{print $1":"$2}' | xargs docker rmi
```
run the result
## Clean up docker
```
docker image prune -f
docker volume prune -f
```
## Verify clean up docker
```
docker ps -a | grep safeline
docker images | grep safeline
```
