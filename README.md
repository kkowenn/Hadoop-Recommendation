# Hadoop Project

## Project Overview

This project is designed to leverage Apache Hadoop for big data processing and analysis. It provides a framework for distributed storage and processing of large datasets across clusters of computers using simple programming models.

### What This Project Can Do

- **Data Processing**: Efficiently process large datasets using Hadoop's MapReduce framework.
- **Data Storage**: Store vast amounts of data in a distributed file system (HDFS).
- **Scalability**: Scale horizontally by adding more nodes to the cluster.
- **Fault Tolerance**: Ensure high availability of data with built-in redundancy.

## Requirements

Before you begin, ensure you have met the following requirements:

- Java Development Kit (JDK) version 8 or higher
- Apache Hadoop version 3.x installed
- A configured Hadoop cluster or a single-node setup
- Appropriate access permissions for HDFS

## Installation

1. **Install Java**:
   - Make sure you have Java installed. You can check by running:
     ```bash
     java -version
     ```

   - If Java is not installed, you can download and install it from [Oracle's official website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

2. **Install Apache Hadoop**:
   - Download Hadoop from the [Apache Hadoop releases page](https://hadoop.apache.org/releases.html).

   - Extract the downloaded archive:
     ```bash
     tar -xzf hadoop-x.x.x.tar.gz
     ```

   - Move it to your desired installation directory:
     ```bash
     mv hadoop-x.x.x /usr/local/hadoop
     ```

   - Add Hadoop to your PATH by editing your `.bashrc` or `.zshrc` file:
     ```bash
     export HADOOP_HOME=/usr/local/hadoop
     export PATH=$PATH:$HADOOP_HOME/bin
     ```

3. **Configure Hadoop**:
   - Edit the configuration files located in `$HADOOP_HOME/etc/hadoop` to suit your setup. Key files include:
     - `core-site.xml`
     - `hdfs-site.xml`
     - `mapred-site.xml`
     - `yarn-site.xml`

   - Start the Hadoop services:
     ```bash
     start-dfs.sh
     start-yarn.sh
     ```

## Running the Project

1. **Upload Data to HDFS**:
   - Use the following command to upload a file to HDFS:
     ```bash
     hdfs dfs -put /local/path/to/your/data.txt /hdfs/path/to/data.txt
     ```

2. **Execute MapReduce Job**:
   - To run a MapReduce job, use the following command:
     ```bash
     yarn jar /path/to/your/hadoop-project.jar com.example.YourMainClass /hdfs/path/to/data.txt /hdfs/output/path
     ```

3. **View Output**:
   - After the job completes, you can view the output stored in HDFS:
     ```bash
     hdfs dfs -cat /hdfs/output/path/part-r-00000
     ```
