# Storm Bundle

### Overview
![schema](https://github.com/Qrama/storm-bundle/blob/master/stormbundle.png?raw=true)

This repository contains the necessary yaml and json to deploy a storm bundle.
The bundle contains the following services:

#### Kafka
- Kafka is a messagebroker where a datastream will write his data.
- The Kafka Spout(storm) will then subscribe to a specific topic to get the data into Storm

#### Storm
- Storm consists of three parts in this bundle: 
  - Nimbus
  - Worker
  - StormTopology:
    - The Storm Topology will deploy the following bolts and spouts:
      - Kafka Spout
      - FilterData Bolt
      - TransformData Bolt
      - MongoDB Bolt
  - Storm also uses Zookeeper to maintain the cluster


#### Zookeeper
- Zookeeper has a relation with the Storm Nimbus and Worker but also With Kafka. In that way it can maintain the storm cluster but also check on Kafka.
    
#### MongoDB
- This is the Datastore that we use to store all the data that the is coming from the MongoDB Bolt

### usage
- this bundle can be deployed in your juju environment by cloning this repo and clone the required charms that are not avilable on the juju charm store. to deploy this bundle use:

```
juju deploy /path/to/bundle.yaml
```
