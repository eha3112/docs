


# TODO
1. working with a dockerhub registery 
2. working a local registery using docker registery container 
3. usefull commands 


> login to a registery 
``` bash
docker login -u "$CI_REGISTRY_USER" -p "$CI_REGISTRY_PASSWORD" $CI_REGISTRY
```

> push an image from a registory 
``` bash
docker push IMAGE_NAME:TAG
```

> pull an image from a registery 
``` bash
docker pull IMAGE_NAME:TAG
```