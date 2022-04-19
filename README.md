# authentication-system-v2
User authentication system, using express.js, JWT, MySql. Improved security.
## Functionality and Description

This is a simple authentication system project where you can register a new user, the data is saved on a mySQL database, using bcrypt to encrypt the password and validating if is correct, also using JWT to generate a token which is save on a httpOnly cookie.
## Utilization

Node modules used:
- bcrypt ^5.0.1
- cookie-parser ^1.4.6
- cors ^2.8.5"
- dotenv ^16.0.0
- ejs ^3.0.2
- express ^4.17.3
- jsonwebtoken ^8.5.1
- mysql2 ^2.3.3

### Cloning and installing modules

Open cmd and clone this repository:

git clone https://github.com/Helisy/authentication-system-v2.git

With node.js installed:

cd your-clone-directory

npm install

### Setting up MySql users table

Open you desired schema or create a new one, set the chosen schema as default and execute this querry:

create table users(
id int not null auto_increment,
first_name varchar(255) not null,
last_name varchar(255) not null,
email varchar(255) not null,
password varchar(255) not null,
role varchar(255) DEFAULT 'basic',
verified boolean DEFAULT false,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
updated_at DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,  
primary key(id)
);

### Creating a .env

It's necessary to create a .env on the root directory file with the following variables:

TOKEN_SECRETE=secret <-Used by JWT to create tokens.

DB_HOST=host
DB_USER=user
DB_PASS=password
DB_DB=database

PORT=port

### Starting the server

Open the cloned repository directory on cmd and start the server:

npm start
