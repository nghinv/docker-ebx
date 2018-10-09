# ebx 5.8.1.1067-0023, tomcat 9.0.12-jre11

works with tomcat9 & jre11. see https://hub.docker.com/_/tomcat/

## requirement

```
docker login
docker pull mickaelgermemont/ebx:5.8.1.1067-0027
```

## Docker build

```
put your ebxLicense in ~/.profile
export EBXLICENSE=XXXXX-XXXXX-XXXXX-XXXXX
source ~/.profile
docker build -t ebx:5.8.1-tomcat9.0.12-jre11 .
```

## Docker run

```
docker run --rm -p 9090:8080 --mount type=volume,src=ebx1,dst=/data/app/ebx -e "CATALINA_OPTS=-DebxLicense=$EBXLICENSE" --name ebx1 ebx:5.8.1-tomcat9.0.12-jre11
```

open your browser at ```http://localhost:9090/ebx```

## connect to running container

```
docker exec -it ebx1 /bin/bash
```
