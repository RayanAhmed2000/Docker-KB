## Docker Conatiner ka Backup kaise lena hai

```
docker commit <conatiner-name> <image-name>
```

```
docker save <container-name> <filename>.tar
```


## Docker conatiner PORT-MAPPING
- can only be done at the time of conatiner creation
- first port is of Host(EC2)
- second port is of container(80-apache2)

```
docker run -it -p 7777:80 --name=<conatiner-name> ubuntu /bin/bash
```


