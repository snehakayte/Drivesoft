In this project I have created following 3 apis:

1] /api/auth
  This api will enable user to authenticate against a prestored user in properties file. For a valid user, api will return token.
  This token can be used in subsequent requests.

2] /api/v1/accounts/populateData
  This api is used to add entries of account information in mysql db. 
  The account information is fetched from the "/api/account/GetAccountList" api through WebClient.
  This response is converted to required entity & stored in DB.
  This api is secured with JWT token generated from "/api/auth" api.
  
3] /api/v1/accounts/fetchpopulatedData
   This api is used to retrive entries of account information added in mysql db using "/api/v1/accounts/populateData" api . 
   This api is secured with JWT token generated from "/api/auth" api.

Following is the sql query to create table in db:

 CREATE TABLE account (
    acct_id INT PRIMARY KEY,                   -- AcctID as the primary key
    acct_type VARCHAR(255),                    -- Account Type (e.g., 'O')
    sales_group_person1_id INT,                -- Sales Group Person ID (e.g., '104748')
    contract_date DATETIME,                    -- Contract Date (e.g., '11/26/2024 12:00:00 AM')
    collateral_stock_number VARCHAR(255),      -- Collateral Stock Number (e.g., 'R344364')
    collateral_year_model INT,                 -- Collateral Year Model (e.g., '2016')
    collateral_make VARCHAR(255),              -- Collateral Make (e.g., 'Chevrolet')
    collateral_model VARCHAR(255),             -- Collateral Model (e.g., 'Equinox')
    borrower1_first_name VARCHAR(255),         -- Borrower 1 First Name (e.g., 'KATELYN')
    borrower1_last_name VARCHAR(255)           -- Borrower 1 Last Name (e.g., 'KING')
);

To complete this project following techstacks were used:

Spring Boot,
Hibernate,
JPA,
Mapstructs,
Lombok,
MySQL DB,
Spring Security.
