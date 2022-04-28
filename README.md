# Pratilipi-assignment

There are two files:
1. preprocessing
2. Model building

The preprocessing file:

    a. reads the the data using dask. 
    b. changes dtype of 'updated_at' to datetime
    c. checks null values
    d. divides the dataset into 2 partitions
    e. sorts one partition and saves the file
  
 The model building file:
 
    a. reads the partitioned data into chunks
    b. uses the read_percent as (similar to ratings, the more the person likes the pratilipi more the person reads)
    c. converts the read_percent on the scale of 0 to 5
    d. loads the data and divides it into train and test
    e. builds ,odel and calculates the rmse
    
  The model is not good since
    a. the RMSE is very high
    b. A model is built for each chunk and does not update previous model
    
  A different approach can be using a neural model where model gets updated for each batch
