FROM a3dataops/spark-py:v3.3.2-hadoop3
  
# using root
USER root:root

#Install curl
RUN apt-get --allow-releaseinfo-change update && \
    apt-get install -y curl && \
    apt-get clean;

#Download this package because it's a large file to GitHub
RUN curl https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.459/aws-java-sdk-bundle-1.12.459.jar --output $SPARK_HOME/jars/aws-java-sdk-bundle-1.12.459.jar

#copy jars files
COPY ./jars/ $SPARK_HOME/jars

#copy and install python requirements
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

