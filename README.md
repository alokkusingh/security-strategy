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
#### Cons
### 2. Digested Password In DB
#### Mechnisam
##### Registration
Hash the user password and store in DB - preferably SHA256 hashing.
##### Login
Hash the user input password and compare with stored hashed password.
#### Pros
#### Cons
### 3. Digested Password along with Salt In DB
#### Mechnisam
##### Registration
Hash the user password by adding random salt and store in DB along with random salt - preferably SHA256 hashing.
##### Login
Hash the user input password by adding stored salt and compare with stored hashed password.
#### Pros
#### Cons
### 4. Digested Password using BCrypt In DB
#### Mechnisam
##### Registration
Hash the user password using BCrypt and store in DB. BCrypt adds the salt and then hashes the passwrod. The salt is added to the hashed password. No additional salt storage needed.
##### Login
Use BCrypt to compare the userinput and hased stired password.
#### Pros
#### Cons
### 5. No Password Storage in DB
#### Mechnisam
##### Registration
Use AES (Symetric Encryption Mechnisam) to encrypt the userid, use password as encryption key. Store the encrypted userid, no need to store the password.
##### Login
Use AES to decrypt the userid, use password as decryption key and compare.
#### Pros
#### Cons
