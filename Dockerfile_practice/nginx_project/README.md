cd nginx_project

docker build -t nginx-demo .

mkdir data

cd data

pwd

cd ..

docker run -d -v pastepath:/app -p 80:80 nginx-demo

docker ps

docker exec -it containerid bash

echo "hello" > demo-file.txt

ls

exit

cd data

ls

cat demo-file.txt

vim dummy-from-host.txt

(this is from host machine)

docker exec -it containerid bash