# Documentation

## Building

### Scala Versions
You can choose to build, assemble and run both Spark and the Spark Cassandra Connector against Scala 2.12

#### Version Cross Build
This produces artifacts for both versions:
Start SBT:

     sbt

Run in the SBT shell:

     + package


### Building The Assembly Jar
In the root directory run

    sbt assembly

To build the assembly jar against Scala 2.11:

     sbt -Dscala-2.11=true assembly

A fat jar will be generated to both of these directories:
   - `spark-cassandra-connector/target/scala-{binary.version}/`

### Building General Artifacts
All artifacts are generated to the standard output directories based on the Scala binary version you use.

In the root directory run:

    sbt package
    sbt doc

The library package jars will be generated to:
  - `spark-cassandra-connector/target/scala-{binary.version}/`
  - `spark-cassandra-connector-java/target/scala-{binary.version}/`

The documentation will be generated to:
  - `spark-cassandra-connector/target/scala-{binary.version}/api/`
  - `spark-cassandra-connector-java/target/scala-{binary.version}/api/`

#### Using the Assembly Jar With Spark Submit
The easiest way to do this is to make the assembled connector jar using

     sbt assembly

This jar can be used with spark submit with `--jars`

    spark-submit --jars spark-cassandra-connector-assembly.jar


This driver is also compatible with Spark distribution provided in
[DataStax Enterprise](https://www.datastax.com/products/datastax-enterprise).

[Next - The Spark Shell](13_spark_shell.md)    
