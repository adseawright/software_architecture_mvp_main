# App for Kids to Sell Products Online

## Brief Description
This front-end application allows users to create and manage their profiles and stores, and add products to their stores. It also includes a storefront where users can view and add products to their cart and check out through PayPal.
 
## How to run the app?

1. Required software:
   Docker
   Visual Studio Code

2. Copy the following repositories to your local machine:
   https://github.com/adseawright/software_architecture_mvp_main
   https://github.com/adseawright/software_architecture_mvp_frontend
   [https://github.com/adseawright/software_architecture_mvp_backend](https://github.com/adseawright/software_architecture_mvp_backend/tree/main/software_architecture_mvp_backend)

3. Open the Code Worspace Source File software_architecture_mvp_main in Visual Studio Code
   
4. Open PowerShell terminal on software_architecture_mvp_main
   
5. Run the following code docker-compose up --build
   
6. You'll be able to see the application in your browser:

http://localhost:3000/login

### API Endpoints
- `/login`: Login API
- `/register`: Register API
- `/profile`: Profile API
- `/stores`: Store API
- `/products`: Product API
- `/create-order`: Order API

## External Component: PayPal API
- Used the PayPal API to handle payment processing in our application. This API allows users to make secure payments through their PayPal accounts, enhancing the safety and reliability of transactions.

### How PayPal API is Used
      To be able to test the paypal API with your credentials, you'll need to create a PayPal developer account on 
      
      https://developer.paypal.com/home/
      
      If you already have a Paypal account, you can use the same credentials.
      
#### API Endpoint:
        The PayPal API endpoint is used to create payment orders and capture payments.

#### Integration:
        The frontend interacts with the PayPal API to initiate payments and handle responses.
        The backend validates payment confirmations received from the PayPal API.
        You can use any of the fake credit card numbers to test a payment 
        
        https://developer.paypal.com/tools/sandbox/card-testing/#link-testcardnumbers

#### Environment Variables:
        Edit the `.env` file in the root directory with the necessary environment variables for PayPal integration.
        ```sh
        SECRET_KEY='your_secret_key'
        PAYPAL_CLIENT_ID="your_paypal_client_id"
        PAYPAL_CLIENT_SECRET="your_paypal_client_secret"
        ```
        
#### External API CALL File

    The backend file that implements the Paypal API connection is order.py 
    
    https://github.com/adseawright/software_architecture_mvp_backend/blob/main/software_architecture_mvp_backend/app/views/order.py 
    
    The frontend file that handles the buying process is Checkout.js 
    
    https://github.com/adseawright/software_architecture_mvp_frontend/blob/main/src/components/Checkout.js
    
## Architecture Diagram
![Architecture Diagram](/kidstore_architecture.PNG)
