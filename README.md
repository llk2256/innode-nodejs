#下载dockerfile 
git clone https://github.com/llk2256/innode-nodejs.git
cd  innode-nodejs
#创建innode-pgsql镜像
docker build -t innode-nodejs .
#打tag  push到hub
docker tag innode-nodejs localhost:5000/innde-nodejs
docker push localhost:5000/innode-nodejs localhost:5000
#运行innode-nodejs容器
docker run -i -t  -d -v /data/innode/innode-nodejs:/app --name innode-nodejs  innode-nodejs /bin/sh

