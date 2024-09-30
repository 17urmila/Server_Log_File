# Project Title : Server Log Data Extraction and User History Database Update

## Technologies Used

Python, SQL , SQlite, MongoDB, REgex

## Problem Statement

The task is to fetch data from a server log file, extract all email addresses along with their corresponding dates,
and upload this data into a user history database. The goal is to ensure the extracted data is clean, accurate, and
accessible for further analysis and historical tracking.

### Steps Followed :

   Step 1 : From the given url the data is downloded
   
      https://drive.google.com/file/d/13qr0NacvjeqC1jPESa8A3ViFY8XtEQAb/view 
      
   Step 2 : Script to read the download file from local
   
       log_file=open('/content/mbox.txt','r').read()
       
   Step 3 : Using Regular expression the email's and the corresponding date and time  is retrieved
   
        pattern = r'From ([a-z0-9]+[\.]?[a-z0-9]+[\@][a-z]+[\.]?[a-z]+[\.]?[a-z]+[\.]?[a-z]+[\s]+[A-Za-z]+[\s]+[A-Za-z]+[\s]+[\d]+[\s]+\d+[:]\d+[:]\d+[\s]\d+)'

   Step 4 : Script used to retrive the data
   
        import re
        pattern = r'From ([a-z0-9]+[\.]?[a-z0-9]+[\@][a-z]+[\.]?[a-z]+[\.]?[a-z]+[\.]?[a-z]+[\s]+[A-Za-z]+[\s]+[A-Za-z]+[\s]+[\d]+[\s]+\d+[:]\d+[:]\d+[\s]\d+)'
        match=re.findall(pattern,log_file)
  
   Step 5:  Format of the date and time column is converted into a standard format (eg. YYYY-MM-DD HH:MM:SS) 

   Step 6 :  Pymongo is installed to connect to mongoDB
        
        !python -m pip install "pymongo[srv]"
   
   Step 7 : The processed data is saved into mongoDB database with collection name "user_history"

   Step 8 : Data is fetched back from mongoDB into a dataframe
   
   Step 9 : sqlalchemy installed to insert DataFrame into database
   
        !pip install sqlalchemy
   
   Step 10 :  Data is uploded into a relational database(SQLite) using python code

   Step 11 :  Table is created with the name "user_history"

   Step 12 :  Stream is installed

       !pip install streamlit -q
       
   Step 13 :  Localtunnel is installed    

       !npm install -g localtunnel

   Step 14 :  SQL queries written in a app.py file 

   Step 15 :  SQL queries run on the database and output is shown in streamlit

  





