# 𝌡 Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- HOOK:APPEND_TO_CHANGELOG -->

# [1.22.9] - 2024-11-07
## :fire: HOT FIXES
- Email not going on Failed Validation.
- for the Failed Validation emails they need to be edited. Message is the same for ACH or Draft.
     **When DATAX Fails:-** A transaction has failed Bank Account Validation. Please contact the service provider for a new payment method.
     **When YODLEE Fails:-** A transaction has failed due to Insufficient Funds. Please contact the service provider for a new payment method.

# [1.22.8] - 2024-11-05

## 🔥 HOT FIXES
- On Merchant accounts page, ability to choose the status and update it's status

## 🧱 DATABASE UPDATE
- add_column :merchant_accounts, :woocommerce_order_statuses, :array
- Update the woocommerce_order_statuses for merchants

Query -

UPDATE public.merchant_accounts
SET woocommerce_order_statuses = ARRAY
        '{
            "name": "created",
            "value": "Processing"
        }'::jsonb,
        '{
            "name": "received",
            "value": "No Action"
        }'::jsonb,
        '{
            "name": "processed",
            "value": "Completed"
        }'::jsonb
    
   WHERE 'Woocommerce with OTP' = ANY(integration_type)
  OR 'Woocommerce without OTP' = ANY(integration_type);

# [1.22.7] - 2024-10-15

## 🔥 HOT FIXES
- If the BAV code is not selected, transactions should show the Failed Validation - P1
- BAV codes are not showing for merchant accounts

# [1.22.6] - 2024-10-11
## :fire: HOT FIXES
- Edit the upcoming transactions, it should populate the data in the form and spinner should not continue to spin

# [1.22.5] - 2024-10-04


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Shopify SSL fix.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.22.4] - 2024-10-03

## 🐞 BUG FIXES
- ACH - TEL Implementation



# [1.22.3] - 2024-10-03


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Upcoming tab showing past transactions.


## 🔧 SYSTEM IMPROVEMENTS





## 🧱 DATABASE UPDATE

# [1.22.2] - 2024-10-03


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS
- If Recurring PR/Invoice has 12 transactions (3 processed, 4th failed) so it will create 8 transactions further which are in cancelled state. What we got to know from tony is that we don't need transactions which are cancelled due to payment so ideally we don't have to create such transactions.




## 🧱 DATABASE UPDATE

# [1.22.1] - 2024-10-03


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Woocommerce required fields check removed.
- Magento required fields check removed.

## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.22.0] - 2024-10-01


## 🔥 HOT FIXES

## 🚀 NEW FEATURES
- WooCommerce Plugin to mark the transaction as Processed/Paid when action Processed clicked and Cancelled when transaction is marked as Cancelled.


## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE
- create_table :woocommerce_orders
- add_column :merchant_accounts, :woocommerce_store_url, :string
- add_column :merchant_accounts, :woocommerce_username, :string
- add_column :merchant_accounts, :woocommerce_password, :string


# [1.21.2] - 2024-10-01


## 🔥 HOT FIXES


## 🚀 NEW FEATURES
- When we go to create transaction or Pr or Invoice page, first selection is merchant, then 2nd should be Individual/business as a dropdown to select between either of those. If merchant is selected, it should show the current form as it is however when Individual is selected, then it should show first name and last both as mandatory fields.

## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE
- add_column :transactions, :is_consumer, :boolean
- add_column :payment_requests, :is_consumer, :boolean
- add_column :invoices, :is_consumer, :boolean

# [1.21.1] - 2024-09-20


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Migration fix.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.21.0] - 2024-09-20
## 🔧 SYSTEM IMPROVEMENTS
- Magento Plugin to mark the transaction as Processed/Paid when action Processed clicked and Cancelled when transaction is marked as Cancelled.
## 🧱 DATABASE UPDATE
- Update merchant_accounts-table-_created-column - magento_username 
- Update merchant_accounts-table-_created-column - magento_password 
- Update merchant_accounts-table-_created-column - magento_store_url 
- Added new table  - magento_order 

# [1.20.9] - 2024-09-18


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Duplicate Fees getting created.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.8] - 2024-09-11


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Pick the merchant name from merchant object on api side.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.7] - 2024-09-09


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Report issue fixed - WEB TEL records showing incorrectly.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.6] - 2024-09-06


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Fix to check the insufficient funds against available_balance instead of current_balance from the data returned by yodlee.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.5] - 2024-08-23


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- When we are creating a PR or invoices and if the validation fails, all the upcoming transactions associated with that PR/Invoice should be created but in cancelled status. Currently when validation fails, it's creating the transactions in Upcoming next occurrences.
- If validation fails after creating invoice / PR, it should show the validation failed message instead of success message.

## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.4] - 2024-08-21


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Same day upcoming fix.

## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.3] - 2024-08-15


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES


## 🔧 SYSTEM IMPROVEMENTS
- Shopify zip code allow only first 5 characters.
- While restricting a consumer, there should be a first option as All on top of the dropdown to restrict all consumers instead of selecting those one by one.



## 🧱 DATABASE UPDATE

# [1.20.2] - 2024-08-13


## 🔥 HOT FIXES


## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Update - Microbilt service call need to stop for now.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.1] - 2024-08-05


## 🔥 HOT FIXES

## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Fix - Inside the system users tab disabled users are not displaying.


## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE

# [1.20.0] - 2024-07-25


## 🔥 HOT FIXES

## 🚀 NEW FEATURES
- Microbilt Feature


## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE
- create_table :microbilt_validation_codes
- create_table :service_validations
- add_column :microbilt_validation_codes, :property_message, :string
- Microbilt validation codes bav codes entry

# [1.19.4] - 2024-07-23


## 🔥 HOT FIXES

## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Fix - Same transaction on main page is showing 4.33 AM and on details page showing 4.30 PM. Created date never changes, so it should not have changed anything there.
- Fix - Merchant is only able to see the transactions till jul 15 2024 pm pst but all the above transactions are not seen when master / merchant admin from Blue.


## 🔧 SYSTEM IMPROVEMENTS




# [1.19.3] - 2024-07-18


## 🔥 HOT FIXES

## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- FILTER fixes - Same day and Next day fixes.
- CCD Transaction same vs next day fixes.


## 🔧 SYSTEM IMPROVEMENTS




# [1.19.2] - 2024-07-18


## 🔥 HOT FIXES

## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Shopify issue fix for lawless and freedom merchants.


## 🔧 SYSTEM IMPROVEMENTS




# [1.19.1] - 2024-07-17


## 🔥 HOT FIXES

## 🚀 NEW FEATURES


## 🐞 BUG FIXES
- Transactions which are created through billed fee giving the issue while creating the ACH.


## 🔧 SYSTEM IMPROVEMENTS




# [1.19.0] - 2024-07-16


## 🔥 HOT FIXES

## 🚀 NEW FEATURES
- ACH - TEL Implementation.

## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS



## 🧱 DATABASE UPDATE
- add_column :merchant_accounts, :is_tel_enabled, :boolean
- add_column :payment_methods, :is_tel_enabled, :boolean
- remove_column :merchant_accounts, :is_tel_enabled, :boolean
- create_table :processing_institution_sec_codes
- rename_table :processing_institution_sec_codes, :processing_institution_not_supported_sec_codes

# [1.18.0] - 2024-07-16


## 🔥 HOT FIXES

## 🚀 NEW FEATURES
- Nacha file - Same Day vs Next Day ACH.

## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE
- add_column :merchant_accounts, :same_day_processing, :boolean, default: false
- remove_column :merchant_accounts, :same_day_processing, :boolean, default: false
- add_column :transactions, :is_same_day_transaction, :boolean, default: false
- add_column :limit_payment_types, :same_day_processing, :boolean, default: false
- UPDATE limit_payment_types
          SET same_day_processing = true
          WHERE financial_processing_institution_id = 3

# [1.17.30] - 2024-07-16


## 🔥 HOT FIXES

## 🚀 NEW FEATURES
- When a New or Received Transaction is placed On Hold, the system should place the associated Validation fee & Processing Fee on hold. Once the Hold has been removed the fees should go to Ready to Bill status. When a Merchant places a new Transaction On Temporary Hold, the system should only place the Processing fee On Hold. Once the Temp Hold has been removed the fees should go to Ready to Bill status.

## 🐞 BUG FIXES



## 🔧 SYSTEM IMPROVEMENTS
- Rename SalesReps and Sales Rep to Resellers and Reseller.





# [1.17.29] - 2024-07-03


## 🔥 HOT FIXES

## 🚀 NEW FEATURES

## 🐞 BUG FIXES
- Fix - Shopify domain code updation and include only dynamic domain.


## 🔧 SYSTEM IMPROVEMENTS



# [1.17.28] - 2024-06-26
## :fire: HOT FIXES
- Fix - Lawlesslabsusa - Shopify order not updating it as Paid or Cancelled.
## :bricks: DATABASE UPDATE
- Update merchant_accounts-table-created-column - shopify_store_url 


# [1.17.27] - 2024-06-21

## 🐞 BUG FIXES
- Fix - Report commission - supplementary section showing deactivated records of deactivated merchants.



## 🔧 SYSTEM IMPROVEMENTS
- Test case failing so version updated from 3.3.0-dev to 3.3.0 from tool-versions file.



# [1.17.26] - 2024-06-11
## 🐞 BUG FIXES
- Fix - There is a production issue where one of the transaction did show the validation BAV codes but it has shown the validation type as None . I know it's not reproducible but do check logically when this can happen.
## 🔧 SYSTEM IMPROVEMENTS
- Password expiry time update and change of checking only last password while resetting.
## 🧱 DATABASE UPDATE
- Update users-table-passowrd_created-column - By update query - UPDATE users SET password_created = CURRENT_DATE  where password_created IS NOT NULL 

# [1.17.25] - 2024-06-07

## 🔥 HOT FIXES
- Fix - Merchant cancel PR/invoice


# [1.17.24] - 2024-06-05

## 🔥 HOT FIXES
- Fix - System is allowing for Received Transactions to be Cancelled when a merchant cancels a Payment Request or Invoices.

## 🐞 BUG FIXES
- Fix - Transactions on Page number 2 and onward in data table are not able to create a credit due to the pagination issue.
- Fix - When we export the transactions, for eDebitDirect LLC transactions are coming as Bank of America but not eDebitDirect LLC.

# [1.17.23] - 2024-05-30
## 🐞 BUG FIXES
- Fix - Autofill changes.
- Active Sales/Reps are not getting loaded in the commission report.

# [1.17.22] - 2024-05-29
## 🚀 NEW FEATURES
- Trigger the refund emails.
- Restricted consumer feature.
## 🐞 BUG FIXES
- Fix - Commission report fix.
- Temporary hold text and color change from payment schedule and payment history.
## 🧱 DATABASE UPDATE

- restricted_reasons - new table added
- restricted_reason_id - added new column to the table restricted_consumers

# [1.17.22] - 2024-05-29
## 🚀 NEW FEATURES
- Trigger the refund emails.
- Restricted consumer feature.
## 🐞 BUG FIXES
- Fix - Commission report fix.
- Temporary hold text and color change from payment schedule and payment history.
## 🧱 DATABASE UPDATE

- restricted_reasons - new table added
- restricted_reason_id - added new column to the table restricted_consumers

# [1.17.21] - 2024-05-16

## 🔥 HOT FIXES


- Fix - Subscription cancelation popup fix on transaction.



## 🐞 BUG FIXES




## 🔧 SYSTEM IMPROVEMENTS




## 🧱 DATABASE UPDATE


# [1.17.20] - 2024-05-14
## :rocket: NEW FEATURES
- Introduce new status Temporary hold
## :bricks: DATABASE UPDATE
- delayed_hold_expiry - added new column to the table transactions
- is_delayed_hold - added new column to the table transactions

# [1.17.17] - 2024-04-09



## 🐞 BUG FIXES
- Commission reports - unable to fetch flagged merchant accounts report.



## 🔧 SYSTEM IMPROVEMENTS
- Transaction Due date issue which was showing the transaction for PR and Invoices to be in Upcoming for One Time type of a payment.
- Monthly report - to show one extra column of monthly fee in fees assessed dropdown list



## 🧱 DATABASE UPDATE

- No updates in Database

# [1.17.16] - 2024-04-03



## 🐞 BUG FIXES
- Pagination page number search fix.


## 🔧 SYSTEM IMPROVEMENTS
- Sender Email updated.



## 🧱 DATABASE UPDATE (The previous migration which we added are not required for now)

- No updates in Database

# [1.17.15] - 2024-03-21



## 🐞 BUG FIXES
- Auto populating the information after entering the email id loading the wrong account/routing number.
- Wordpress - woo plugin does not show the payment method for https://goldenrulebotanicals.com/.


## 🔧 SYSTEM IMPROVEMENTS
- Remove the "Remove or call and number" from the email template.
- Shopify api version change.



## 🧱 DATABASE UPDATE (The previous migration which we added are not required for now)

- processing_institution_not_supported_sec_codes - new table added
- is_tel_enabled - new column added to the table payment_methods


# [1.17.15] - 2024-03-21



## 🐞 BUG FIXES
- Auto populating the information after entering the email id loading the wrong account/routing number.
- Wordpress - woo plugin does not show the payment method for https://goldenrulebotanicals.com/.


## 🔧 SYSTEM IMPROVEMENTS
- Remove the "Remove or call and number" from the email template.
- Shopify api version change.



## 🧱 DATABASE UPDATE (The previous migration which we added are not required for now)

- processing_institution_not_supported_sec_codes - new table added
- is_tel_enabled - new column added to the table payment_methods


# [1.17.14] - 2024-03-05


## 🐞 BUG FIXES
- Commission report - not calculating ACH transaction correctly for Commissions Reports



## 🔧 SYSTEM IMPROVEMENTS
- 
- 
- 





## 🧱 DATABASE UPDATE

- No updates in Database


# [1.17.13] - 2024-02-20

## 🔥 HOT FIXES

Below changes done in this release which were not specific to the code but those were requested from the backend admin team - 

- DB Data Update - Mark Harris Customer is not charged for recurring monthly PR on 16th Feb for merchant PageHub.



## 🐞 BUG FIXES
- Commission report - not calculating ACH transaction correctly for Commissions Reports



## 🔧 SYSTEM IMPROVEMENTS
- Merchant - Wordpress logo plugin validation services.



## 🧱 DATABASE UPDATE

- logo_on_plugin - new column added to the table merchant_accounts


# [1.17.12] - 2024-02-13




## 🐞 BUG FIXES
- Transactions - due_date affected by time on users local machine




## 🏗️ REFACTOR / CLEANUP
- Seed File updated with right email ids

# [1.17.11] - 2024-02-06




## 🐞 BUG FIXES
- Sales Reps - unable to access Monthly Statements from mobile view
- Monthly Statements - table not formatted correctly in mobile view
- Payment Requests - Edit causes validation service to be stored as 'Datax'
- Transactions - unable to cancel from mobile view
- Merchants - Add button is visible to users in mobile view
- Transactions - cancel payment plan modal does not display in mobile view
- Commissions Report - Returns or transactions processed on last day of the month not selected for commissions
- Monthly Statements - transactions processed on last day of the month not selected




## 🔧 SYSTEM IMPROVEMENTS
- Commissions Report - table not well formatted in mobile view
- Transactions - add a column for validation service
- Transactions - add validation service to the filter




# [1.17.10] - 2024-01-30




## 🐞 BUG FIXES
- Transactions Report - results grouped incorrectly if more than a year of data requested
- Transactions Reports - Sunday transactions not included in weekly Period




## 🔧 SYSTEM IMPROVEMENTS
- Shopify - front end changes
- Shopify - check plugin validation services
- Shopify - Yodlee error message when using invalid zipcode
- Shopify - improved flow for Chase Bank




## 🏗️ REFACTOR / CLEANUP
- User Mailer - update text for failed validation email


# [1.17.9] - 2024-01-23


## 🔥 HOT FIXES
- Consumers - status set to Disabled after a week




## 🐞 BUG FIXES
- Payment Requests/Invoices - Processed transactions not displayed correctly in Payment Schedule/Plan History after edit
- Nav bar - sub menu items display stuck open




## 🔧 SYSTEM IMPROVEMENTS
- SalesRep Users - merchant details page
- Sales Rep Users - page navigation
- Sales Rep Users - Admin
- Sales Rep Users - Monthly Statements




# [1.17.8] - 2024-01-16

## 🚀 NEW FEATURES
- Integrate OpenTimestamps into the backend
- Create Draft PDF with e-signature
- Verify Draft PDF with e-signature using OpenTimestamps
## 🐞 BUG FIXES
- System Users - unable to use filters
- Master Merchants - unable to use sort or select all
## 🔧 SYSTEM IMPROVEMENTS
- Training videos - remove option to download the videos
- Reports - select New transactions based on created_at date

# [1.17.7] - 2024-01-10

# Changes

## 🔥 HOT FIXES

- Payment Requests - unable to edit non-authorized PR
- Payment Reqs/Invoices - blank Routing and Account Number when editing a PR/Invoice that has not had bank details saved

# [1.17.6] - 2024-01-09

## 🔥 HOT FIXES
- Login - user can't log in as refresh token keeps using an expired token

## 🐞 BUG FIXES
- Login - OTP preference does not allow user login
- Users - address set to null after PR/Invoice is edited
- Users - shopify consumer being created with invalid zipcode

## 🔧 SYSTEM IMPROVEMENTS
- Training videos - Adjustments
- Training Videos - display videos according to user role

# [1.17.5] - 2024-01-05

### 🔥 HOT FIXES
- Login - error message displayed when resetting password

# [1.17.4] - 2024-01-03

### 🔥 HOT FIXES
- Login - user can't log in as refresh token keeps using an expired token

### 🐞 BUG FIXES
- PR/Invoice authorization - Yodlee window does not load if consumer goes back
- Nav bar - sub menu items displayed when the cursor is not hovering over
- Commissions - modal text contains undefined instead of month
- Commissions - Unable to load PDF file

### 🔧 SYSTEM IMPROVEMENTS
- Transactions - cancel Payment Plan/Subscription modal improvement
- Timestamps - add timezone

# [1.17.3] - 2023-12-27
### 🐞 BUG FIXES
- Fix shopify bug order status bug

# [1.17.2] - 2023-12-22
### 🔧 SYSTEM IMPROVEMENTS
- Update health-check method parameters

# [1.17.1] - 2023-12-21
### 🔧 SYSTEM IMPROVEMENTS
- Fix exposed controller endpoints

# [1.17.0] - 2023-12-20

### 🐞 BUG FIXES
- PR/Invoices - cancel and redistribute PP transaction for Yodlee
- Transactions - can't add a note
- Fix behavior inconsistencies in the system due to version incompatibilities

### 🔧 SYSTEM IMPROVEMENTS
- Payment Req/Invoice Authorization - improved flow for Chase Bank
- (Front-end) Update Node.js version to latest LTS without vulnerabilities
- (Front-end) Update NPM Packages to latest known versions without vulnerabilities
- (Back-end) Update Ruby Gems to latest known versions without vulnerabilities
- Add Unit Testing Workflow for GitHub Actions
- User message - You need to refresh your token
- Add Trivy Vulnerability Scan Workflow for GitHub Actions
- (Back-end) Update Ruby version to latest available without vulnerabilities



### 🧱 INFRASTRUCTURE
- Library Updates

# [1.16.17] - 2023-12-13

### 🐞 BUG FIXES
- Transactions - Draft updated and printed with truncated account number

# [1.16.16] - 2023-12-12

### 🐞 BUG FIXES
- Transactions - cannot cancel New transaction from Cancelled Subscription/Payment Plan
- Merchant Accounts - Industry is being removed
- DataX banks being loaded for Yodlee invoices
- PR/Invoices - internal server error if consumer bank details are deleted during authorization
- Payment Req./Invoices - memo can be copied in with carriage returns

### 🔧 SYSTEM IMPROVEMENTS
- Monthly Statements - Commissions - PDF report updates

# [1.16.15] - 2023-12-07

### 🐞 BUG FIXES

- Transactions - can't print drafts from multiple pages

# [1.16.14] - 2023-12-07

### 🐞 BUG FIXES
- Consumers - user status set to Deleted
- Payment Req./Invoices - fails to create when copying one that has been edited
- Create Merchant Account - internal server error when e-signatures feature flag is Off
- Undefined method url_for

### 🔧 SYSTEM IMPROVEMENTS
- Transactions - character limit for Memo
- PRs/Invoices - option to redistribute cancelled payment
- Monthly Statements - Commissions - Excel export
- Admin - System Users Disable if pending more than a week

# [1.16.13] - 2023-12-05

### 🚀 NEW FEATURES
- Add health-check method for api

### 🔧 SYSTEM IMPROVEMENTS
- Plugin API - return Chase accounts for use on Draft/Yodlee flow

# [1.16.12] - 2023-11-28

### 🚀 NEW FEATURES
- E-Signatures - Display sign pop-up for enabled only
- E-Signatures - Backend Implementation for Merchant Account Edit
- E-Signatures - Transactions Detail e-check only for signed drafts

### 🐞 BUG FIXES
- Edit Merchant Account - plugin validation services get reset to null
- Edit Merchant Account - blank screen when switching back to edited payment method
- Monthly Statements - Commissions - cost split not selected by payment method
- Monthly Statements - Commissions - report exists for for incorrect sales rep

### 🔧 SYSTEM IMPROVEMENTS
- Fees - New fee types for Monthly/Setup Fees

# [1.16.11] - 2023-11-21

### 🚀 NEW FEATURES

- e-Signatures - display check draft for consumer authorization
- e-Signatures - Transactions Layout
- e-Signatures - Merchant Account setup layout
- Help - Training videos

### 🐞 BUG FIXES

- CSV Upload - Failed Authorization merchant sent to Merchant
- Log In - Login button is occasionally frozen

### 🔧 SYSTEM IMPROVEMENTS
- PRs/Invoices - Increase the width so that (Needed for 2-Factor Authentication) fits on the page
- Reports/Monthly Statements - remove condition to display only Enabled merchants
- Payment Requests/Invoices - obscure Account number when copying a PR/Invoice

# [1.16.10] - 2023-11-16

### 🔧 SYSTEM IMPROVEMENTS

- Repopulate consumer bank details

# [1.16.9] - 2023-11-14

### 🚀 NEW FEATURES

- Transactions/PRs/Invoices - Autofill data for returning consumers
- PR/Invoice Authorization - Autofill Yodlee linked payment information for consumers
- Fees - Add filter for Processing Institution

### 🐞 BUG FIXES

- Fix ACH Only Merchants
- Refactor If Condition on Shopify Controller Method
- All Index screens - Count Is Not Displaying If All Items Selected
- Transactions - Inaccurate Data Populated When Using an Existing Email
- Payment Requests/Invoice Authorization - Payment Complete/Failed dialog box close
- Transactions - Exported data is not consistent with the screen display

### 🔧 SYSTEM IMPROVEMENTS

- Rearrange Daily Transactions Worker Time Zone
- Update Container Initialization process
- Payment Requests/Invoices - Phone Number Writing Logic on the Users Table
- Reports - Transactions - Export as Function Method Logic
- Transactions - Remove Ability to Cancel `CCC` Transactions

# [1.16.7] - 2023-11-13

### 🐞 BUG FIXES

- Refactor unnecessary if condition on Shopify controller method

# [1.16.6] - 2023-11-08

### 🐞 BUG FIXES

- Daily Transactions Worker Time Zone

# [1.16.5] - 2023-11-07

### 🚀 NEW FEATURES

- All Index screens - Add a shortcut key to select between rows
- Ticket 1947662165 - Merchant Account - On Hold Status
- Ticket 1930994049 - Merchant account - Plugin Validation Service

### 🐞 BUG FIXES

- Invoices - No Delivery is not being stored correctly
- Monthly Statements - Returns
- Upcoming payment Mailer - wrong data being populated in emails
- Loop request overloading back-end

### 🔧 SYSTEM IMPROVEMENTS

- Rewrite cron-jobs to handle multiple app containers
- Serializer Class Acting Like a Singleton

# [1.16.4] - 2023-10-31

### 🐞 BUG FIXES

- Transactions - Allow Print Draft from On Hold status
- Admin - Consumers - Restricted consumer
- Transactions Details - Merchant is able to cancel Received Drafts
- Ticket 1931004540 - Add Authorized Contact should not change the status of the account

### 🔧 SYSTEM IMPROVEMENTS

- Ability To Remove Merchant Account Logo
- Changes to the Edit Payment Request process
- Ticket 1956197386 - Merchant Accounts - Note and Business Description Fields
- Improve the speed of Search on Transactions page

### 🏗️ REFACTOR / CLEANUP

- Refactor unit testing with rspec

# [1.16.3] - 2023-10-24

### 🐞 BUG FIXES

- Consumer List filter restricted is not working
- Invoices - Don't send OTP is not working
- Monthly Statements - Commissions - Total commission incorrect
- Ticket 2007308351 - System inactivity logout


### 🔧 SYSTEM IMPROVEMENTS

- Ticket 1947662403 - Disabled Merchant Account - Cancel Upcoming Transactions, PR's, & Invoices
- Payment Request & Invoice details - display Authorization Data
- Receipt change for PRs and Invoices

# [1.16.2] - 2023-10-20

### 🐞 BUG FIXES

- Payment Requests - PR Details screen - Cancel not working

# [1.16.1] - 2023-10-17

### 🐞 BUG FIXES

- Revert Using Yodlee Bank Information When Pre-Loading Consumer On Transaction/PR/Inv Form

# [1.16.0] - 2023-10-17

### 🐞 BUG FIXES

- Ticket 1942052621 - Restricted Consumer not working
- Transactions are going over the limit when no limit has been exceeded
- Invoices - Remove the option to edit Amount
- Using Yodlee Bank Information When Pre-Loading Consumer On Transaction/PR/Inv Form

### 🔧 SYSTEM IMPROVEMENTS

- Fees - Remove all merchant user views
- Monthly Statements - Commissions - Adjustments
- Monthly Statements - Monthly Statements - Adjustments

# [1.15.9] - 2023-10-12

### 🐞 BUG FIXES
- Merchant's view of Fee Details changes

# [1.15.8] - 2023-10-11

### 🐞 BUG FIXES
- Monthly Statements - Supplementary costs using wrong values
- Revert Using Yodlee Bank Information When Pre-Loading Consumer On Transaction/PR/Inv Form

# [1.15.7] - 2023-10-10

### 🐞 BUG FIXES
- Using Yodlee bank information when pre-loading consumer on transaction/pr/invoice form
- Prevent Yodlee payment requests with no auth
### 🔧 SYSTEM IMPROVEMENTS
- Requested changes on transaction reports
- Display monthly statements for merchant users
- Implement redis cache for overloaded endpoints
