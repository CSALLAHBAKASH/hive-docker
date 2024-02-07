# hive-docker

mkdir Hive
cd Hive
touch docker-compose.yml
touch hadoop-hive.env
mkdir employee
cd employee
touch employee_table.hql
touch employee.csv


root@dc86b2b9e566:/employee# hive -f employee_table.hql
docker exec -it hive-server /bin/bash
hadoop fs -put employee.csv hdfs://namenode:8020/user/hive/warehouse/testdb.db/employee

hadoop fs -rm  hdfs://namenode:8020/user/hive/warehouse/testdb.db/employee/employee.csv
