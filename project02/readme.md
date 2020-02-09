Postgres:


logstash:

sudo sysctl -w vm.max_map_count=262144

localhost:
  image: docker.elastic.co/elasticsearch/elasticsearch:7.5.1
  environment:
    - LOGSTASH_JDBC_URL=jdbc:postgresql://postgres:5432/postgres_test
    - LOGSTASH_JDBC_DRIVER=org.postgresql.Driver
    - LOGSTASH_JDBC_DRIVER_JAR_LOCATION=./config_ls/postgresql.jar
    - LOGSTASH_JDBC_USERNAME=postgres_test
    - LOGSTASH_JDBC_PASSWORD=postgres_test
  volumes:
    - ./config_ls/logstash.conf:/usr/share/logstash/pipeline/logstash.conf
  ports:
    - 9600:9600
    - 5044:5044

sudo docker run -it \
  --name logstash_test \
  -v config_ls/logstash.conf:/usr/share/logstash/pipeline/logstash.conf \
  docker.elastic.co/elasticsearch/elasticsearch:7.5.1


  INSERT INTO my_test (client_id, value, last_changed)
  VALUES ('1234','2000','1985');

  SELECT * FROM my_test;


  file {
  path => "/output"
  codec => "json_lines"
}
