# NextCoin
The NextCoin API provides a programmatic interface for interacting with the NextCoin database. This enables developers to integrate NextCoin functionality into their applications, facilitating various use cases within the NextCoin ecosystem.

Currently, this API offers methods for querying, updating, and managing data within the NextCoin database.

The url endpoint at which requests can be made is `https://pct4k7-3000.csb.app`

## Support
Please send any ideas, questions, errors, or bugs to Thomas Smith.

## Javascript Fetch Requests
Currently, the NextCoin API lacks a formal JavaScript fetch request process. If you're interested in enabling JavaScript integration, consider contributing to the project's development.

## Possible Future Features
The following potential features are envisioned for future development, subject to community contributions and support:

Multiple Passwords: This functionality would cater to scenarios where multiple parties require authorization for transactions. For instance, a company might implement this feature to safeguard against unauthorized withdrawals by requiring approval from both investors and the CEO.

## Terms of Service
Money Generation: NextCoin generation adheres to the principle of requiring a "viable personage" who actively desires 250nc to be credited to their account. This helps maintain the integrity of the system.

2% of the transaction money will go to the account of Thomas Smith. If 2% of the money transfered is less than 1nc, the float will be added to the balance of your account.

Those searching for money to be generated with their account can contact Thomas Smith.

## API
### Users
#### POST `user/register`
`name`: The name of your user<br>
`email`: The email of your user<br>
`password`: This password is encrypted.<br>

This function will create a user, along with a default wallet with the user called 'Default Wallet.'

Returns the user id and the wallet id.

**Errors**
`{ error: :password_is_greater_than_12 }`
When the password length is greater than 12.

`{ error: :email_is_empty }`
When the email length is zero.

`{ error: :name_is_empty }`
When the email length is zero.

#### GET `user/get_all_users`
Gets all the users along with the wallets associated with the accounts.

#### GET `user/get_user`
`user_id`: The user id of your user<br>
*or*
`email`: The email of your user<br>

Returns the user with the email, along with the wallets accociated with the account.

#### POST `user/check_password_equality`
`user_id`: The user id of your user<br>
`password`: The password _you think_ belongs to the user.<br>

Returns a boolean. True means the password is correct.

### Wallets
#### GET `wallet/get_wallet`
`wallet_id`: The wallet id of your wallet<br>

Returns the wallet.

#### GET `wallet/get_all_wallets`
`user_id`: The id of the user.<br>

Returns the wallets associated with the user.

#### POST `wallet/update_wallet_name`
`email`: The email of the user.<br>
`password`: The password of the user.<br>
`wallet_id`: The id of the wallet.<br>
`new_name`: The new name of the wallet.<br>

**Errors**
`{ error: :authentication_information_is_incorrect }`
When the user authentication information is incorrect.

#### POST `wallet/create_wallet`
`email`: The email of the user.<br>
`password`: The password of the user.<br>
`name`: The name of the new wallet.<br>

**Errors**
`{ error: :authentication_information_is_incorrect }`
When the user authentication information is incorrect.

#### POST `wallet/transfer`
`recipient_wallet_id`: The wallet id where the money will be sent.<br>
`owner_user_email`: The email of the user sending the money.<br>
`owner_user_password`: The password of the user sending the money.<br>
`owner_wallet_id`: The wallet id where the money will be taken out of.<br>
`coin_amount`: The amount of coins to be take out of the wallet.<br>

**Errors**
`{ error: :not_enough_money }`
When the user does not have enough money in the wallet.

