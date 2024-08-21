# App for Kids to Sell Products Online

## Brief Description
This front-end application allows users to create and manage their profiles and stores, add products to their stores, and includes a storefront where users can view and add products to their cart and check out through PayPal.

## How to Run the App

### Prerequisites
- **Docker**
- **Visual Studio Code**

### Steps to Run

1. **Clone the Repositories:**
   - [Main Repository](https://github.com/adseawright/software_architecture_mvp_main)
   - [Frontend Repository](https://github.com/adseawright/software_architecture_mvp_frontend)
   - [Backend Repository](https://github.com/adseawright/software_architecture_mvp_backend/tree/main/software_architecture_mvp_backend)

2. **Open the Workspace:**
   - Open the `software_architecture_mvp_main` workspace in Visual Studio Code.

3. **Start the Application:**
   - Open a PowerShell terminal in the `software_architecture_mvp_main` directory.
   - Run the following command:
     ```sh
     docker-compose up --build
     ```

4. **Access the Application:**
   - Open your browser and navigate to:
     [http://localhost:3000/login](http://localhost:3000/login)

### API Endpoints
- **`/login`**: Login API
- **`/register`**: Register API
- **`/profile`**: Profile API
- **`/stores`**: Store API
- **`/products`**: Product API
- **`/create-order`**: Order API

## External Component: PayPal API
The application integrates with the PayPal API to handle payment processing, allowing users to make secure payments through their PayPal accounts, thereby enhancing the safety and reliability of transactions.

### How PayPal API is Used

1. **Create a PayPal Developer Account:**
   - Visit [PayPal Developer](https://developer.paypal.com/home/) to create a developer account.
   - If you already have a PayPal account, you can use the same credentials.

2. **API Endpoint:**
   - The PayPal API endpoint is used to create payment orders and capture payments.

3. **Integration:**
   - The frontend interacts with the PayPal API to initiate payments and handle responses.
   - The backend validates payment confirmations received from the PayPal API.
   - To test a payment, you can use any of the [PayPal Sandbox Test Card Numbers](https://developer.paypal.com/tools/sandbox/card-testing/#link-testcardnumbers).

4. **Environment Variables:**
   - Edit the `.env` file in the root directory with the necessary environment variables for PayPal integration:
     ```sh
     SECRET_KEY='your_secret_key'
     PAYPAL_CLIENT_ID="your_paypal_client_id"
     PAYPAL_CLIENT_SECRET="your_paypal_client_secret"
     ```

5. **External API Call Files:**
   - **Backend**: The file that implements the PayPal API connection is `order.py`.
     - [Backend File: `order.py`](https://github.com/adseawright/software_architecture_mvp_backend/blob/main/software_architecture_mvp_backend/app/views/order.py)
   - **Frontend**: The file that handles the buying process is `Checkout.js`.
     - [Frontend File: `Checkout.js`](https://github.com/adseawright/software_architecture_mvp_frontend/blob/main/src/components/Checkout.js)

## Architecture Diagram
![Architecture Diagram](/kidstore_architecture.PNG)
