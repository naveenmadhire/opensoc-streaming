#OpenSoc Streaming Using Apache Flink

This repo uses Apache Flink and Apache Storm connector to have all the Storm Topologies actually run on Apache Flink. All the existing Storm topologies can be run with very minimal changes.

More info of the Flink and Storm connector can be found [here](https://ci.apache.org/projects/flink/flink-docs-master/apis/storm_compatibility.html)

Apache Flink can be run on any multi-node hadoop/yarn cluster. More information can be found [here](https://ci.apache.org/projects/flink/flink-docs-master/setup/yarn_setup.html)

# How to run the repo

```
git clone "Github directory"
cd opensoc-streaming

mvn clean install
```

This will create a fat jar under /target folder.


For running Apache Flink on Yarn,

a. Start a Yarn Session,

Eg,

```
./bin/yarn-session.sh -n 10 -tm 8192 -s 32
```

This will create an YARN Session with 10 task manager with 8 GB of memory and 32 processing slots each

b. Now submit job to a YARN Session using

```
./bin/flink run "Location of the fat jar" -c "Fully qualified name of Main program" "Arguments to the Main program"
```



#Current Build

The latest build of OpenSOC-Streaming is 0.6

We are still in the process of merging/porting additional features from our production code base into this open source release. This release will be followed by a number of additional beta releases until the port is complete. We will also work on getting additional documentation and user/developer guides to the community as soon as we can. At this time we offer no support for the beta software, but will try to respond to requests as promptly as we can.

# OpenSOC-Streaming

Extensible set of Storm topologies and topology attributes for streaming, enriching, indexing, and storing telemetry in Hadoop.  General information on OpenSOC is available at http://opensoc.github.io

# Documentation

Please see documentation within each individual module for description and usage instructions. Sample topologies are provided under OpenSOC_Topologies to get you started with the framework. We pre-assume knowledge of Hadoop, Storm, Kafka, and HBase.
