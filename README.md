[![N|Solid](https://github.com/billiedark/coinbaseapi/blob/main/Coinbase.png?raw=true)](https://github.com/billiedark)

![Python](https://img.shields.io/badge/-Python-0a0a0a?style=for-the-badge&logo=python&logoColor=24e387)

This library was created to simplify the creation and receipt of payments from the Coinbase api, [provided on the official website](https://docs.cloud.coinbase.com/commerce/docs), in the Python programming language.  


## Features

- Checking token validity  
- Creating a bill for payment  
- Information about the bill  


## Installation 

[Python](https://www.python.org/) version 3.2 or higher must be installed  

```cmd
pip install CoinbaseAPI
```

## Using 
To get your Api key, you need to register in Coinbase Commecre and get your key [by following this link](https://beta.commerce.coinbase.com/settings/security)  

### Quick example of account creation and payment verification  
Every 5 seconds the code will check the payment:  
``` python
from CoinbaseAPI import CoinbaseAPI
from time import sleep

api_key = "YOUR_API_KEY"
api = CoinbaseAPI(api_key)

payment = api.create_charge("Test title", "Test description", 5.00, "USD")
print(payment.url)

while True:
    if payment.is_paid():
        print("Payment is paid!")
        break

    sleep(5)
```

## License  

GNU General Public License (GPL)  
