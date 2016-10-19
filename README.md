# SentimentAnalysis_usingKafkaAndSparkStreaming

This application has been tested on CDH 5.4.0 cluster.

# How to build
The applicaiton has two modules.

# twitter-kafka
*twitter-kakfa* consumes tweets from twitter using credentials provided in {{conf/producer.conf}}
 and produces those tweets to Apache Kafka whose information is also provided in {{conf/producer
 .conf}}. Modify the configuration file with suitable values before running the application.
 
## How to run
```
./gradlew :twitter-kafka:run -Pargs="<PATH_TO_CONF>"
```

If configuration file is not specified as an argument, then the app uses {{conf/producer.conf}} 
as configuration file by default.

# kafka-spark
*kafka-spark* consumes tweets from Apache Kafka whose information is provided in 
{{conf/analyzer.conf}} and performs sentiment analysis on the stream of tweets. Tweets along 
with sentiment analysis result is then persisted in Apache HBase. Modify the configuration file 
with suitable values before running the application.
 
## How to run
```
./gradlew :kafka-spark:run -Pargs="<PATH_TO_CONF>"
