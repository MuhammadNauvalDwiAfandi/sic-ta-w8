## Content of Repository

|File|Content  |
|--|--|
|sendToMongoDB.py|Contain all function to send, delete, read, and modify data from MongoDB|
|main.py|Main script for flask service|


## How to Use
**Requirement**

 - Python
 - Python library; Flask, Flask-PyMongo, python-dotenv, geocoder (optional)
 - Or, after python is already installed, type `pip install -r requirements.txt`
 - Postman

**Running the script**

 Type `main.py` inside terminal
 ![Terminal running](https://raw.githubusercontent.com/MuhammadNauvalDwiAfandi/sic-ta-w8/master/images/Screenshot%202022-08-25%20132716.png)

## Functionality
**http://localhost:5000/send/**



 - `POST` method, enter params, id_transaksi: int, kecepatan: float, longitude: float, latitude: float

 ![send data](https://raw.githubusercontent.com/MuhammadNauvalDwiAfandi/sic-ta-w8/master/images/Screenshot%202022-08-25%20132747.png)

 - If the id_transaksi already exist in MongoDB, return *id_transaksi already exist, use /modify instead*

	![id_transaksi already exist](https://raw.githubusercontent.com/MuhammadNauvalDwiAfandi/sic-ta-w8/master/images/Screenshot%202022-08-25%20132816.png)

 - If one of the params is missing or doesn't match expected data type, return *400*
![send 400](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20140114.png)

 - `GET` method, return *Only for POST request!*
![send GET](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20140007.png)
 
**http://localhost:5000/modify/**

 - `POST` method, enter params, id_transaksi: int, kecepatan: float, longitude: float, latitude: float. id_transaksi is the identifier of data that wants to be modified in the database. (kecepatan, longitude, latitude) is the new data. Return *Succes! Data with id_transaksi x has been modified. Show old data then new data*
 ![modify data](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20133125.png)

 - If one of the params is missing or doesn't match expected data type, return *400*

 - If data with id_transaksi specified doesn't exist in MongoDB, return *No data with id_transaksi 10 found in the database!*
![modify doesn't exist](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20142610.png)

 - `GET` method, return *Only for POST request!*

**http://localhost:5000/show/**

 - `POST` method, enter params, id_transaksi: int. Return *Showing data with id_transaksi x, `data`*
 ![show data](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20132948.png)
 - If data with id_transaksi specified doesn't exist in MongoDB, return *No data with id_transaksi x found in the database!*
![show doesn't exist](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20143335.png)
 
 - `GET` method, return *Latest data found in the database: `data`*
 ![get method show](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20133007.png)

**http://localhost:5000/delete/**

 - `POST` method, enter params, id_transaksi: int. Return *Succes! Data with id_transaksi x has been deleted! Deleted data: `data`*
 ![delete](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20133146.png)
 - If data with id_transaksi specified doesn't exist in MongoDB, return *No data with id_transaksi 10 found in the database!*
 ![delete doesn't exist](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20143907.png)
 - `GET` method, return *Only for POST request!*
 ![delete get](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20144108.png)

**Note**
Timestamps are automatically appended in the data that sent to MongoDB

## Result
**Terminal**
![terminal](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20133202.png)

**MongoDB**
![mongodb](https://github.com/MuhammadNauvalDwiAfandi/sic-ta-w8/blob/master/images/Screenshot%202022-08-25%20133235.png)

## About Repository

This repository is for Samsung Innovation Campus 3 Technical Assignment Week 8: IoT Software API & Database

Here's the problem:

> Kalian diminta untuk membuat sebuah backend services untuk menerima
> sebuah data kecepatan, latitude dan longitude dalam sebuah body json.
> Dan kalian juga diharapkan untuk menyimpan data tersebut beserta
> dengan timestampnya.

Copied from: [SIC Stage 3 Technical Assignment Week 8](https://github.com/impactbyte/iot-with-python-technical-assignments/tree/main/08-IoT-Software-1)
