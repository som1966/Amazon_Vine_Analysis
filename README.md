# Amazon_Vine_Analysis
## Overview
  This week's challenge was analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. Utilizing a Amazon review for the product tools dataset; Pyspark was used to perform the ETL process then connected to an AWS RDS and load the four seperate tables into pgAdmin.
  
![image](https://user-images.githubusercontent.com/89953246/146844571-53cea718-f7c5-4836-948b-6a4de432d8e6.png)
  
## Vine_Review_Analysis Process
 A Vine_Review_Analysis was completed in Pyspark on the vine_table. 
 
 1. The dataset was filtered by total_votes >= 20; total count was 35312.
 ![image](https://user-images.githubusercontent.com/89953246/146845651-0c25eb0b-eb7e-4920-8cc9-7992a59070e3.png)

 2. A new table was created (helpful_votes) was created that retrieved all the rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%. This further reduce the data rows to 31830.
 3. Another table was created by that retrieved all the rows where a review was written as part of the Vine program (paid), vine == 'Y'.
 ![image](https://user-images.githubusercontent.com/89953246/146846197-d62495e1-8c2c-4edd-8451-f560059c4fab.png)

 4. Votes from the unpaid part of the program were isolated. In the filtered helpful_votes, there were not any helpful votes that were in the unpaid program.
 
 ![image](https://user-images.githubusercontent.com/89953246/146848462-6290a934-bdc0-434e-9a34-1a830ce9865e.png)

