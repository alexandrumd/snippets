Helpers for working with docker

# cleanup
- Remove all stopped containers: `docker rm $(docker ps -aq)`
- Remove all untagged images: `docker rmi $(docker images | grep "^<none>" | awk '{print $3}')`
  - Works by using rmi with a list of image ids. To get the image ids we call `docker images` then pipe it to `grep "^<none>"`. The grep will filter it down to only lines with the value “<none>” in the repository column. Then to extract the id out of the third column we pipe it to `awk '{print $3}'`.

# useful commands
- copy a local file to a docker volume, with `/app` being the workdir set as destination and `local.file` a file located in $PWD: `docker run --rm -v $PWD:/source -v volume_name:/app -w /source container_name cp local.file /app`
