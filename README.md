# Kafka - A distrubuted streaming platform

## Kafka-Installation

To start working with Kafka commands, you have to install Kafka first.

[Download Kafka](https://apache.osuosl.org/kafka/2.7.0/kafka_2.13-2.7.0.tgz)

Untar the downloaded file using the below command in GitBash
```
tar -xzf kafka_2.13-2.7.0.tgz
```
Now, change the directory to the Kafka folder
```
cd kafka_2.13-2.7.0
```
## Kafka running commands

Run the below comand in PowerShell as an administrator in Kafka folder
```
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```
By running this command, an instance of the Zookeeper coordination service starts.

Minimize this window to keep the process running and open another window in the same Kafka location and run the below command
```
$ bin/kafka-server-start.sh config/server.properties
```
This command is to have a basic Kafka environment running and ready to use

Next step is to create your own topic.

My topic is my-trailblazer-story.

Run the below command in another PowerShell terminal in the same location
```
 .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic my-trailblazer-story
 ```
 Your topic will be created.

Now, run the below command in the same terminal.  This command will display the list of topics created by you.
```
 .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
 ```
A Kafka client communicates with the Kafka brokers via the network for writing (or reading) events. Once received, the brokers will store the events in a durable and fault-tolerant manner for as long as you need—even forever.

In another terminal, run the command to write a few events into your topic. By default, each line you enter will result in a separate event being written to the topic.
 ```
 .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic my-trailblazer-story
 ```
 Open another terminal and run the command to let the client read the events you just created
 ```
 .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic my-trailblazer-story --from-beginning
 ```
