# INSTALL MONGODB BNR-SERVER

docker run -d \
  --name mongodb-shared \
  --restart always \
  -p 27018:27017 \
  -v /opt/mongo-data:/data/db \
  mongo:4.0

docker ps

docker ps -a

docker stop mongodb-shared

docker start mongodb-shared

docker restart mongodb-shared

docker exec -it mongodb-shared mongo

docker exec -it mongodb-shared mongo -u <username> -p

docker exec -it mongodb-shared mongo my_db

exit

