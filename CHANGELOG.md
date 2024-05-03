# 𝌡 Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- HOOK:APPEND_TO_CHANGELOG -->

# [1.17.19] - 2024-05-03
## :rocket: NEW FEATURES
- Merchant - Restrict Consumer
## :bricks: DATABASE UPDATE
- restricted_reasons - new table added
- restricted_reason_id - added new column to the table restricted_consumers

# [1.17.18] - 2024-05-02



## 🐞 BUG FIXES
- Amount humanize issue amount showing wrong in text.




## 🧱 DATABASE UPDATE

- No updates in Database

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
