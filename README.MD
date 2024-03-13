# How to execute
Download the docker compose file and run `docker compose up`. It will start the docerk containers.
After it we can access `http://localhost:8080` where we will be able to see the kafka UI.

# Creating topics via CLI
To do it we can access the container and execute the CLI command inside the container. To access the conatiner CLI we can use `docker exec -it kafka-udemy-learn /bin/bash` and if we want to see the log from the container we can use `docker logs container_name`.
Once inside the container we can navigate throught the bash terminal to explore the paths and files.
Inside the `./bin` we have have the files about kafka and insite `./etc/kafka` we have the config files that we can use to config our kafka.

# Kafka CLI commands
- List topics
`kafka-topics --bootstrap-server localhost:9092 --list`
- Get specifique topic description
`kafka-topics --bootstrap-server localhost:9092 --topic topic_name --describe`
- Create a new topic
`kafka-topics --bootstrap-server localhost:9092 --topic topic_name --create`
- Create a new topic with partitions
`kafka-topics --bootstrap-server localhost:9092 --topic topic_name --create --partitions 3`
- Create a new topic with a replication factor
`kafka-topics --bootstrap-server localhost:9092 --topic topic_name --create --partitions 3 --replication-factor 1` we can not have a `--replication-factor` more than a number of brokers.
- Delete a topic
`kafka-topics --bootstrap-server localhost:9092 --topic topic_name --delete`