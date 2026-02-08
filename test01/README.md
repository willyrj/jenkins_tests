docker build -t my-nginx-landing .
docker run -d -p 9000:80 --name nginx-landing my-nginx-landing
docker stop nginx-landing
docker rm nginx-landing
docker logs nginx-landing

