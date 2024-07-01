# NextCoin
The NextCoin API provides a programmatic interface for interacting with the NextCoin database. This enables developers to integrate NextCoin functionality into their applications, facilitating various use cases within the NextCoin ecosystem.

Currently, this API offers methods for querying, updating, and managing data within the NextCoin database.

## Support
Please send any ideas, questions, errors, or bugs to hotpepper156@gmail.com

## Javascript Fetch Requests
Currently, the NextCoin API lacks a formal JavaScript fetch request process. If you're interested in enabling JavaScript integration, consider contributing to the project's development.

## Possible Future Features
The following potential features are envisioned for future development, subject to community contributions and support:

Multiple Passwords: This functionality would cater to scenarios where multiple parties require authorization for transactions. For instance, a company might implement this feature to safeguard against unauthorized withdrawals by requiring approval from both investors and the CEO.

## Terms of Service
Money Generation: NextCoin generation adheres to the principle of requiring a "viable personage" who actively desires 250nc to be credited to their account. This helps maintain the integrity of the system.

2% of the transaction money will go to the account of Thomas Smith. If 2% of the money transfered is less than 1nc, the float will be added to the balance of your account.

## API
### Users
#### POST `user/register`
name: The name of your user
email: The email of your user
password: This password is encrypted.

