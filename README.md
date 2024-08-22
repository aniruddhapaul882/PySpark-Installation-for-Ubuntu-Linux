#  Install Java Development Kit (JDK)
First, update the package index by running: <br>
```
$ sudo apt update
```
Next, install the default JDK using the following command: <br>
$ sudo apt install default-jdk <br>
#Verify the installation by checking the Java version: <br>
$ java -version <br>

Install Apache Spark <br>
#Download the latest version of Apache Spark from the official website (https://spark.apache.org/downloads.html). At the time of writing, the latest version is Spark 3.5.2. Choose the package type as “Pre-built for Apache Hadoop 3.3 and later”. <br>
#Use the following commands to download and extract the Spark archive: <br>
wget https://archive.apache.org/dist/spark/spark-3.5.2/spark-3.5.2-bin-hadoop3.tgz  <br>
tar -xvzf spark-3.5.2-bin-hadoop3.tgz <br>
#Move the extracted folder to the /opt directory <br>
sudo mv spark-3.5.2-bin-hadoop3 /opt/spark <br>

###Set Up Environment Variables <br>
#Add the following lines to your ~/.bashrc file to set up the required environment variables: <br>
sudo nano /.bashrc <br>
#Add this two lines to you ~/.bashrc file and save it <br>
#	export SPARK_HOME=/opt/spark <br>
#	export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin <br>
#Source the updated ~/.bashrc file to apply the changes: <br>
source ~/.bashrc <br>

###Install PySpark <br>
#Install PySpark using pip: <br>
pip install pyspark <br>
