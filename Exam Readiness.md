
## Data Engineering

#### Amazon S3 with SageMaker

- Amazon S3 is integrated with SageMaker to store training data and model training output.
- S3 [data] -> SageMaker Training Job -> S3 [model artifacts] -> SageMaker Endpoint

#### Amazon FSx for Lustre

- When your data is in S3 and you run training jobs serveral times using different algorithms and parameters, use FSx for Lustre.
- FSx automatically copy data from S3 and make it avaiable to SageMaker so that the data doesn't need to be downloaded from S3 again and again. 
- FSx speed up training jobs

#### Amazon S3 with Amazon EFS

- With EFS, it can be used as training data source. 
- For example, a data scientist can use a Jupyter notebook to do initial cleansing on a training set, launch a training job from Amazon SageMaker, then use their notebook to drop a column and re-launch the training job, comparing the resulting models to see which works better.


### Data Ingestion

- Batch processing - group data in data ingestion layer and send to S3, use Glue ETL or AWS database migration service (AWS DMS)
- Stream processing - real-time processing. Data is sourced, manipulated and loaded as soon as it is created or recognized by the data ingestion layer.

#### Amazon Kinesis for streaming data
- Kinesis Video Stream - ingest and analyze video and audio data.
- Kinesis Data Analytics - process and transform data streams from Kinesis Data Streams or Kinesis Data Firehose using SQL. 
- Kinesis Data Stream - use Kinesis Producer Library (KPL) and Kinesis Data Stream API data to write. Use Kinesis Client Library (KCL) to build own application to preprocess streaming data and emit for downstream analysis.
- Kinesis Data Firehose - Near real time data stream ingestion to batch and compress data to generate  incremental views. Allow custom transformation logics with Lambda.

### Data Preparation

Distributed computation frameworks like MapReduce and Apache Spark provide a protocol of data processing and node task distribution and management. They also use algorithms to split datasets into subsets and distribute them across nodes in a compute cluster.

Apache Spark on Amazon EMR to process massive quantities of data. As EMR support instance types with high CPU , it is well suited for high performace computing applications.

For ETL, Glue, Athena (manage data files using SQL), Redshift Spectrum.

![[Screenshot from 2023-03-01 09-14-26.png]]

# EDA

- **identifying correlation is important**, high correlation between two attributes can sometimes lead to poor model performance. 
- **Scatter plots visualize relationships between numerical variables** - when you have more than two numerical variables in a feature dataset and you want to understand their relationship, use scatter plot for visualization. 
- **Correlation matrices help you quantify the linear relationships among variables** - 
  one - X and Y are proportional to each other
  minus - X is proportional to - Y
  zero - no linear relationship between X and Y. 

- Standize the data
- Make data is on same scale
  scaling techniques
-   Mean/variance standardization
-   MinMax scaling
-   Maxabs scaling
-   Robust scaling
-   Normalizer
  
- Make sure a column doesn't include multiple features
- Careful about outliners ( clean or they skew values away from normal values)
- Missing data handling 
   remove missing data column or rows
   Fill missing value with mean, zero or use imputation. (when dataset is small and can't afford to loss data points, use imputation)

### Feature Engineering

- When you dimensionality of dataset is high, use Principal Component Analysis (PCA) or t-distributed stochastic neighbor embedding for dimensionality reduction.
- For numerical features, squaring, cubing, multiplication of feature as transformation. (multinomial or polynomial)
- Categorical Data - Ordinal (categories are ordered), Nominal (categories not ordered)
  convert categorical data to numerical data. But not recommended to convert nomial data to numerical, instead encode using one-hot encoding. 
  
  