
# Data Analysis of Brazalian Ecommerce Dataset

**Author:**   
Bipin Ghimire - bipin.ghimire@fusemachines.com  

## Prerequisites

- Download Apache Spark
- Create a virtual environment
- Clone the repo 
- Install the requirement.txt file using  
   pip install -r requirements.txt
- Connect you postgres with the spark.
- Create a new .env file and add your username and password as 

      POSTGRES_USER=<Your Postgres Username>
      POSTGRES_PASSWORD=<Your Postgres Password>
- Run spark-submit Final_project_complete.py 

**For cronjob Task**
- Create a .sh file in Linux  
   Steps:  
   a. Open Linux Bash
   b. nano <filename>.sh  
            
            Example: nano run_spark.sh
   c. Type the following in the nano editor  

      /path/to/spark/bin/spark-submit \
      --master local \
      /path/to/project/Final_project_complete.py

      Note:  
      In /path/to/spark and /path/to/project give your required path

   d. In the bash terminaml run 

      crontab -e

   e. Inside crontab nano editor add the required cronjob task 

       */3 * * * * /path/to/.sh file/run_spark.sh >> /path to store log/spark_log.log 2>&1

       Note:  
       */3 * * * * is where you define the time you job runs again.

   




# Dataset Overview 
Brazilian ecommerce public dataset

https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce?select=olist_geolocation_dataset.csv  

The different CSV files are:

This project involves the analysis of multiple datasets related to Brazilian e-commerce. The datasets provide valuable insights into customer behavior, order details, product information, and more. The goal of this analysis is to gain a deeper understanding of the e-commerce business in Brazil, identify trends, and extract useful information.

## Datasets

### Customers Dataset

- **Customer_id**: Unique identifier for each customer. Links to orders.
- **Customer_unique_id**: A unique identifier for the customer.
- **Customer_zip_code_prefix**: The first five digits of the customer's zip code.
- **Customer_city**: The name of the customer's city.
- **Customer_state**: The state of the customer.

### Order Items Dataset

- **Order_id**: Unique identifier for each order.
- **Order_item_id**: Sequential number identifying the number of items in an order.
- **Product_id**: Unique identifier for the product.
- **Seller_id**: Unique identifier for the seller.
- **Shipping_limit_date**: Seller's shipping limit date.
- **Price**: Item price.
- **Freight_value**: Item freight value.

### Payment Dataset

- **Order_id**: Unique identifier for the order.
- **Payment_sequential**: Sequential number for multiple payment methods.
- **Payment_type**: Chosen payment method.
- **Payment_installments**: Number of installments chosen.
- **Payment_value**: Transaction value.

### Orders Dataset

- **Order_id**: Unique identifier for the order.
- **Customer_id**: Links to customer dataset.
- **Order_status**: Order status (e.g., delivered, shipped).
- **Order_purchase_timestamp**: Purchase timestamp.
- **Order_approved_at**: Payment approved timestamp.
- **Order_delivered_carrier_data**: Order posting timestamp.
- **Order_delivered_customer_date**: Actual order delivery date.
- **Order_estimated_delivery_date**: Estimated delivery date.

### Product Dataset

- **Product_id**
- **Product_category_name**
- **Product_name_length**
- **Product_description_length**
- **Product_photo_qty**
- **Product_weight_g**
- **Product_length_cm**
- **Product_height_cm**
- **Product_width_cm**

### Seller Dataset

- **Seller_zip_code_prefix**
- **Seller_city**
- **Seller_state**

### Product Category Name Translation Dataset

- **Product_category_name**
- **Product_category_name_english**

### Geolocation Dataset

- **Zip_code**
- **Geo_latitude**
- **Geo_longitude**
- **Geolocation_city**
- **Geolocation_state**

## Analysis Tasks

**Question 1:**  
Finding the distance between the seller
and customer for each order.  

![Question 1 Output](/OutputImages/question1.png)


Finding the average distance covered
by the sellers of each stat  
![Question 1 Output](/OutputImages/question2.png)


**Question 2:**  
Finding the revenue generated by each
product in each state.   
![Question 1 Output](/OutputImages/question3.png)


Finding the precentage contribution of each
product on states revenue  
![Question 1 Output](/OutputImages/question4.png)



