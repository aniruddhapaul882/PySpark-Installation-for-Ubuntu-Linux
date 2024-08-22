#  For Ubuntu(linux)
###  Install Java Development Kit (JDK)
First, update the package index by running:
```
sudo apt update
```
Next, install the default JDK using the following command:
```
sudo apt install default-jdk
```
Verify the installation by checking the Java version:
```
java -version
```
### Install Apache Spark
Download the latest version of Apache Spark from the official website (https://spark.apache.org/downloads.html). At the time of writing, the latest version is Spark 3.5.2. Choose the package type as “Pre-built for Apache Hadoop 3.3 and later”. <br>
Use the following commands to download and extract the Spark archive:
```
wget https://archive.apache.org/dist/spark/spark-3.5.2/spark-3.5.2-bin-hadoop3.tgz
tar -xvzf spark-3.5.2-bin-hadoop3.tgz
```
Move the extracted folder to the /opt directory
```
sudo mv spark-3.5.2-bin-hadoop3 /opt/spark
```
###  Set Up Environment Variables
Add the following lines to your ~/.bashrc file to set up the required environment variables:
```
sudo nano /.bashrc
```
Add this two lines to you ~/.bashrc file and save it
```
export SPARK_HOME=/opt/spark
export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin
```
Source the updated ~/.bashrc file to apply the changes:
```
source ~/.bashrc
```
###  Install PySpark
Install PySpark using pip:
```
pip install pyspark
```
### Verify PySpark Installation
Create a new Python file called pyspark_test.py and add the following code:
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("PySpark Test").getOrCreate()

data = [("Alice", 34), ("Bob", 45), ("Cathy", 29)]

columns = ["Name", "Age"]

df = spark.createDataFrame(data, columns)

df.show()

spark.stop()
```
Run the script using:
```
python pyspark_test.py
```
If everything is set up correctly, you should see the following output:
```
+-----+---+
| Name|Age|
+-----+---+
|Alice| 34|
|  Bob| 45|
|Cathy| 29|
+-----+---+
```
