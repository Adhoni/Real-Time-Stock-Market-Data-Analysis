# Real-Time Stock Market Analysis with Kafka and AWS S3

This project simulates real-time stock market data streaming using Kafka and AWS S3. It integrates a producer that streams stock market data and a consumer that listens to the Kafka topic and stores the data in AWS S3.

## Architecture Overview

![Real-Time Stock Market Analysis Architecture](https://github.com/Adhoni/Real-Time-Stock-Market-Data-Analysis/blob/master/Architecture.jpg)

The architecture consists of:
1. **Stock Market App Simulation:** Simulates stock market data using Python.
2. **Kafka (Amazon EC2):** Acts as a broker, where the producer sends data and the consumer retrieves it.
3. **AWS S3:** Data is stored in an S3 bucket for further analysis.
4. **AWS Glue and Athena:** Used for cataloging and querying the stored data.

## Prerequisites

- **Python 3.x**
- **Kafka server** (Running on EC2 or local)
- **AWS S3 bucket**
- **Kafka Python Library (`kafka-python`)**
- **S3 FileSystem (`s3fs`)**
- **pandas**

## Setup Instructions

### Step 1: Clone the Repository

```bash
git clone https://github.com/username/real-time-stock-analysis.git
```


### Step 2: Install Dependencies
Install the required Python libraries:
```bash
pip install kafka-python s3fs pandas
```

### Step 3: Start Kafka Server
If you haven't already started your Kafka server, you can do so by running:
```bash
bin/kafka-server-start.sh config/server.properties
```
### Step 4: AWS Credentials Configuration
Ensure that you have AWS CLI configured with appropriate credentials to access your S3 bucket. Run the following to configure:
```bash
aws configure
```
### Step 5: Run Producer and Consumer
1. Run the Producer to send stock market data to the Kafka topic:



```bash
python producer.py
```
2. Run the Consumer to consume messages from the Kafka topic and store the data in the AWS S3 bucket:

```bash
python consumer.py
```

### Step 6: Verify Data in S3 Bucket

After running both the producer and the consumer, check your S3 bucket to verify that the data is being stored correctly.


