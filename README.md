## Test combination of Cake and Gitlab piplines

### Setup
Steps: 
* set bridge network - `docker network create -d=bredge git-net`
* run gitlab -  `docker run --rm -d -p 8111:80 --name gitlab --network git net gitlab/gitlab-ce`
* run runner - `docker run --rm -f --network git-net -v //var/run/docker.sock:/var/run/docker.sock --name git-run gitlab/gitlab-runner`
* execute runner register command - `docker exec -it git-run gitlab-runner register`
