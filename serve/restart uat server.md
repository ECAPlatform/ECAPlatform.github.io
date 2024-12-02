# User Acceptance Test Environment  Guide :

##### Admin portal url

https://uatsd01.novonordiskchina.cn/backstage

##### Agent chat portal url

https://uatsd01.novonordiskchina.cn/service/login.html

#####   How to start application service  after  restart  uat linux server?

```
# start  redsi service 
cd /home/admintalu/tools/redis-install/bin &&  sudo ./redis-server ./redis.conf
# start nginx service
sudo /usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
# start nginx application
cd /home/admintalu/u01/application  &&   sudo sh deploy-jar.sh
```

##### Deploy-jar.sh script：

```
#!/bin/bash
log_date=`date +%Y-%m-%d`
log_file="jeecg-boot-module-system-$log_date.out"
jar_file="spring-boot-module-system-2.3.0.jar"
echo "publish================="

process_id=`ps -ef | grep $jar_file | grep -v grep |awk '{print $2}'`
if [ $process_id ] ; then
      kill -9 $process_id
fi
ps -ef | grep $jar_file

source /etc/profile
nohup java -jar -Dspring.profiles.active=test ./$jar_file > ./log/$log_file 2>&1 &

echo "end publish"
tail -f ./log/$log_file
```

