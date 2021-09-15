# security-strategy
Security Strategy

## Login Password Storage Strategy
### 1. Plain Password In DB
#### Mechnisam
##### Registration
Store the password in plain text form.
##### Login
Compare the user input passwrd with stored passowrd.
#### Pros
1. Very simple implmentaion.
2. Passowrd retrival is possible.
#### Cons
1. Very bad strategy - if Db is hacked or opeartion engineer can see password.

### 2. Digested Password In DB
#### Mechnisam
##### Registration
Hash the user password and store in DB - preferably SHA256 hashing.
#### Pros
1. Better than the plain text one.
#### Cons
1. If 2 passwords are same, the hash code will be same. So, easy to guess the common password strings.
2. Passowrd retrival is not possoble. Only password reset can be done.

### 3. Digested Password along with Salt In DB
#### Mechnisam
##### Registration
Hash the user password by adding random salt and store in DB along with random salt - preferably SHA256 hashing.
##### Login
Hash the user input password by adding stored salt and compare with stored hashed password.
#### Pros
1. Hashed password will be diffrent even the two passwords are same. So, hard to break.
#### Cons
1. Additional salt storage is needed.
2. Passowrd retrival is not possoble. Only password reset can be done.

### 4. Digested Password using BCrypt In DB
#### Mechnisam
##### Registration
Hash the user password using BCrypt and store in DB. BCrypt adds the salt and then hashes the password. The salt is added to the hashed password. No additional salt storage needed.
##### Login
Use BCrypt to compare the userinput and hased stired password.
#### Pros
1. Hashed password will be diffrent even the two passwords are same. So, hard to break.
2. No need to store salt in additional column.
#### Cons
2. Password retrival is not possoble. Only password reset can be done.

### 5. No Password Storage in DB
#### Mechnisam
##### Registration
Use AES (Symetric Encryption Mechnisam) to encrypt the userid, use password as encryption key. Store the encrypted userid, no need to store the password.
##### Login
Use AES to decrypt the userid, use password as decryption key and compare.
#### Pros
1. No need to store the password.
#### Cons
