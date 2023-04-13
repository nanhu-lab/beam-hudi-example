# beam-hudi-example
An example to show how to make Apache Beam write data to Apache Hudi, and read data from Apache Hudi.
## Quickstart
Test cases are given in the BeamHudiTest document.
1. Then, use testHudiWrite() to write the data to Apache Hudi. In testHudiWrite(), the simulated data is created, then the simulated data is converted by Apache Beam (converting the user_name to uppercase), and finally written to Apache Hudi.
2. At last, use testHudiRead() to read the data out of Apache Hudi, and then filter according to the user_age, and write the data that meets the criteria to text.  
## Configuration
A few important dependencies are shown below, and others are seen in the pom.xml  
```xml
<properties>  
    <spark.version>3.2.0</spark.version>
    <beam.version>2.41.0</beam.version>
     <hudi.version>0.11.1</hudi.version>
</properties>
<dependencies>
    <dependency>
        <groupId>io.github.nanhu-lab</groupId>
        <artifactId>beam-datalake</artifactId>
        <version>1.0.0</version>
    </dependency>
    <!-- beam -->
    <dependency>
        <groupId>org.apache.beam</groupId>
        <artifactId>beam-runners-core-java</artifactId>
        <version>${beam.version}</version>
        <scope>provided</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.beam</groupId>
        <artifactId>beam-runners-direct-java</artifactId>
        <version>${beam.version}</version>
        <scope>provided</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.beam</groupId>
        <artifactId>beam-sdks-java-core</artifactId>
        <version>${beam.version}</version>
        <scope>provided</scope>
    </dependency>
    <!-- spark -->
    <dependency>
        <groupId>org.apache.spark</groupId>
        <artifactId>spark-sql_2.12</artifactId>
        <version>${spark.version}</version>
        <scope>provided</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.spark</groupId>
        <artifactId>spark-core_2.12</artifactId>
        <version>${spark.version}</version>
        <scope>provided</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.spark</groupId>
        <artifactId>spark-streaming_2.12</artifactId>
        <version>${spark.version}</version>
        <scope>provided</scope>
    </dependency>
    <!-- hudi -->
    <dependency>
        <groupId>org.apache.hudi</groupId>
        <artifactId>hudi-spark3.2-bundle_2.12</artifactId>
        <version>${hudi.version}</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.hudi</groupId>
        <artifactId>hudi-client-common</artifactId>
        <version>${hudi.version}</version>
        <exclusions>
            <exclusion>
                <groupId>com.esotericsoftware</groupId>
                <artifactId>kryo-shaded</artifactId>
            </exclusion>
        </exclusions>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.hudi</groupId>
        <artifactId>hudi-common</artifactId>
        <version>${hudi.version}</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.hudi</groupId>
        <artifactId>hudi-java-client</artifactId>
        <version>${hudi.version}</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.commons</groupId>
        <artifactId>commons-lang3</artifactId>
        <version>3.12.0</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>com.esotericsoftware</groupId>
        <artifactId>kryo</artifactId>
        <version>4.0.2</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.apache.avro</groupId>
        <artifactId>avro</artifactId>
        <version>1.10.2</version>
    </dependency>
</dependencies>
```
