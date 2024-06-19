# Fingerprint Based ATM System

This project is a Fingerprint-Based ATM System implemented using Flask and MySQL. It allows users to perform various ATM operations like Deposit, Withdraw, and View Balance after securely logging in with their fingerprint.

## Features
- User Authentication using Fingerprint
- Deposit Money
- Withdraw Money
- View Transaction History

## Technologies Used
- Flask (Python)
- MySQL
- HTML/CSS
- JavaScript

## Prerequisites
Before you begin, ensure you have met the following requirements:
- Python 3.x installed on your machine
- MySQL Server installed and running
- `pymysql` Python library installed
- Fingerprint data for users (saved as .png files)

## Installation

1. Clone the repository to your local machine:
    ```sh
    git clone https://github.com/your-username/fingerprint-atm-system.git
    cd fingerprint-atm-system
    ```

2. Create a virtual environment and activate it:
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```sh
    pip install Flask pymysql
    ```

4. Set up the MySQL database:
    - Create a database named `atm`.
    - Create two tables: `users` and `transaction` using the following SQL scripts:

    ```sql
    CREATE TABLE users (
        username VARCHAR(50) PRIMARY KEY,
        password VARCHAR(50),
        contact_no VARCHAR(15),
        emailid VARCHAR(50),
        address VARCHAR(100),
        gender VARCHAR(10)
    );

    CREATE TABLE transaction (
        username VARCHAR(50),
        transaction_amount FLOAT,
        transaction_type VARCHAR(50),
        transaction_date DATETIME,
        total_balance FLOAT,
        FOREIGN KEY (username) REFERENCES users(username)
    );
    ```

## Usage

1. Run the Flask application:
    ```sh
    python app.py
    ```

2. Open your web browser and go to `http://127.0.0.1:5000`.

3. You will be presented with the following options:
    - Sign Up: Create a new user account.
    - Log In: Log into an existing account using your username, password, and fingerprint.
    - Deposit: Deposit money into your account.
    - Withdraw: Withdraw money from your account.
    - View Balance: View your transaction history and current balance.

## File Structure

- ├── templates
- │ ├── Deposit.html
- │ ├── Withdraw.html
- │ ├── index.html
- │ ├── Login.html
- │ ├── Signup.html
- │ ├── UserScreen.html
- │ ├── ViewBalance.html
- ├── app.py


## Contributing

Contributions are always welcome! Please follow these steps:
1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.

