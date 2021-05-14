# Company X

<h3> Table of Contents</h3>

1. [Overview](#overview)
   1. [Customers](#customers)
      1. [Introduction](#customers-introduction)
      2. [The Advantages](#customers-benefits)
      3. [Steps on how it works?](#customers-work)
   3. [Developers](#developers)
      1. [Introduction](#developers-introduction)

### Overview <a name="overview"></a>

Company X presents a new mobile application called "_CashOut_" which has provided a seamless way of sending money to foreign banks accounts. The mobile app uses an appropriate currency exchange level, and the international transfer fees are cheap.

### For customers <a name="customers"></a>

#### Introduction <a name="customers-introduction"></a>

The company X mobile application now allows you to send and receive money with your company x's account internationally. You can search for any foreign bank to make a transaction to that foreign bank account number.

#### The Advantages <a name="customers-benefits"></a>

1. It saves a lot of time and keeps track of the money remitted.
2. It proves to be much cheaper and faster to send money abroad than other solutions around.
3. It is effortless to use, secure and reliable.

#### Steps on how it works? <a name="customers-work"></a>

1. Log in to the mobile app and open the sidebar menu.
2. Click on the menu option called "international transfers" and search for the bank's name to make a transaction.
3. Once the bank name is gotten successfully, you can send money to a given account number.

-----

### For developers <a name="developers"></a>

#### Introduction <a name="developers-introduction"></a>

The international payments API is designed to make international transactions seamless. This documentation gives an in-depth description on how the API works.

#### To search for a bank across the world.

The search API presents a way to search for any foreign bank and account number across the world.

<h4> API Route:  </h4>

| HTTP Verb    | Path         | Description                                                  |
|   ---        | ---          | ------                                                       |
|  `POST`      | `lookup`     | requires ths bank's `country_code` and `account_number`      |


<h4>Sample API response for a successful return of a particular `bank`, `account number` and `account name`</h4>

```

{ 
    "status": 200, 
    "success": true, 
    "message": "success", 
    "data": { 
       "bank_name": 'bank xyz', 
       "bank_code": '00001', 
       "account_name": 'john doe', 
     } 
} 

```

<h4>Sample API error response</h4>

```

{ 
    "status": 500, 
    "success": false, 
    "message": "invalid bank name", 
    "data": [] 
} 

```

#### Response codes:

Status code `200` depicts a success, whilst error `500` depicts an error in transaction.

| Status Codes | Indication                                                                      |
|   ---        | ---                                                                             |
|  `200`       | This status code indicates that the bank exists.                                |
|  `500`       | This status code indicates that there was an error getting the requested bank   |


#### To transfer to any bank account number across the world.

The transfer API presents a way to transfer to any foreign bank account number.

<h4> API Route:  </h4>

| HTTP Verb    | Path           | Description                                                  |
|   ---        | ---            | ------                                                       |
|  `POST`      | `transfer`     | requires the `amount`, `bank` and `sort_code`     |


<h4>Sample API response for a successful transaction </h4>
  
```

{ 
    "status": 200, 
    "success": true, 
    "message": "transfer successfull", 
    "data": { 
        "bank_name": 'bank xyz', 
        "sort_code": '00001', 
        "amount": '10000', 
    } 
} 
 

```

<h4>Sample API error response for an unsuccessful transaction</h4>

```

{ 
    "status": 500, 
    "success": false, 
    "message": "unsuccessful", 
    "data": [] 
}


```

#### Response codes:

Status code `200` depicts a success, whilst error `500` depicts an error in transaction.

| Status Codes | Indication                                                                        |
|   ---        | ---                                                                               |
|  `200`       | This status code indicates that the transaction is successful.                    |
|  `500`       | This status code indicates that there was an error in performing the transaction  |

