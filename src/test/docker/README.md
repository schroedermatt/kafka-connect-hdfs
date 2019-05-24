# Hadoop 3.x Docker Setup

*Prerequisite:* Download the hadoop-3.1.2 distribution and place it in `src/test/docker/hadoop-3.1.2`. The file is
too large for git and will be ignored once placed in that directory.

[Download Hadoop 3.1.2](https://www.apache.org/dist/hadoop/common/hadoop-3.1.2/hadoop-3.1.2.tar.gz)

## Running Hadoop

From the `/docker` directory, run `docker-compose up` to build the docker image and start the container.

### Hadoop

```sh
# hop onto the hadoop container
docker exec -it hadoop3 bash

# run the admin report to see the health of things
> hdfs dfsadmin -report
```

You can navigate to `http://127.0.0.1:9870` for a top level look at the NameNode and DataNode. A [file explorer](http://localhost:9870/explorer.html) is also available.

The DataNode should be available at `http://127.0.0.1:9864`

### NameNode

The NameNode connection is done via `hdfs://127.0.0.1:9000`

### Rebuild Image

If you've made changes to settings or the Dockerfile, you can rebuild by running `docker-compose up --build`.
