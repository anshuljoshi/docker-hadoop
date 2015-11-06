## Dockerfile and other files required to create docker image of hadoop.

Docker image is available on docker hub.
Get the image using:

```docker pull anshuljoshi/docker-hadoop:latest```

### Current version - 2.7.1

- Configure passwordless ssh across all cluster containers.
- Download, install and configura Java.
- Download, install and configure Apache Yarn:
- Configure Namenode and Datanode connectivity.
- Enable dynamic Datanodes to connect to Namenode.
- Configure Network:
- Network connectivity.
- Expose Yarn ports required by Administration UI and Node communication.

##### Steps:

- Fork the repository and clone it, or directly clone it.
- Go to the version directory that you want.

```docker build  -t anshuljoshi/docker-hadoop:2.7.1 .```

To create the container:

```docker run -it anshuljoshi/docker-hadoop /etc/bootstrap.sh -bash```

To run a demo job:

```cd $HADOOP_PREFIX```

> run the mapreduce

```bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.1.jar grep input output 'dfs[a-z.]+'```

> check the output

```bin/hdfs dfs -cat output/*```
