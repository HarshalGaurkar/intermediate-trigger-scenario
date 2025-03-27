# intermediate-trigger-scenario
This repository will be having intermediate trigger scenario which can we used in salesforce for business need

**Below Are the details description of the trigger with there name and usecase**

**Trigger_Name: SyncIndustryToParentAccount**
- Scenario: Update Parent Account Industry Based on Child Account
- Use Case: A business want to populate the child account industry to the parent account.
- Triggering Object: Account
- Event: After Insert, After Update
- Action: Sync Industry of child accounts with the parent account.

**Trigger_Name: CreateTaskOnLeadConversion**
- Scenario: Create a Follow-up Task When Lead is Converted
- Use Case: A business whant to take a follow up by creating the task when lead is converted
- Triggering Object: Lead
- Event: after update
- Action: Create a follow-up task when the Lead is converted

**Trigger_Name: CalculateBirthdate**
- Scenario: Auto-Populate Contact Birthdate Based on Custom Age Field
- Use Case: A business whant to capture the birthdate of the applicant when user enter the age on record or update on record.
- Triggering Object: Contact
- Event: before insert, before update
- Action: Calculate Birthdate from Age__c.

**Trigger_Name: UpdateAccountBirthday**
- Scenario: Auto-Populate Contact Birthdays to Account Level
- Use Case: If a Contact's birthday is updated, update the Earliest Birthday field on the Account.
- Triggering Object: Contact
- Event: After Insert, After Update, After Delete
- Action: Update the earliest birthday on the Account when a related Contact's birthday changes.

**Trigger_Name: UpdateAccountIndustry**
- Scenario: Auto-Update Account Industry Based on Most Common Contact Title
- Use Case: If most Contacts in an Account have a similar job title (e.g., Engineers), update the Industry field accordingly.
- Triggering Object: Contact 
- Event: After Insert, After Update, After Delete
- Action: Set the Account Industry based on Contact job titles.

**Trigger_Name: ReopenCaseOnCustomerResponse**
- Scenario: Automatically Reopen a Case if the Customer Responds After Closure
- Use Case: If a customer replies to a closed case (by adding a new comment), the case should be reopened to ensure the support team addresses their concerns.
- Triggering Object:  CaseComment
- Event: After Insert
- Action: If a new CaseComment is added to a Closed Case, update the Case Status to "Reopened."

**Trigger_Name: AutoTagFileBasedOnRecordType**
- Scenario: Auto-Tag Files Based on Record Type
- Use Case: When a user uploads a file (ContentDocumentLink) related to an Opportunity, Case, or Account, the file should be automatically tagged based on the record type for easier organization.
- Triggering Object:  ContentDocumentLink
- Event: After Insert
- Action: 
    - If the file is uploaded to an Opportunity, tag it as "Sales Document"
    - If uploaded to a Case, tag it as "Support Document"
    - If uploaded to an Account, tag it as "Customer Document"
 
**Trigger_Name: StandardizeAttachmentName**
- Scenario: Rename Attachments to Follow a Standard Naming Convention
- Use Case: All uploaded attachments should follow a standard naming format:
- RecordType_RecordName_Timestamp.pdf
- Triggering Object:  Attachment
- Event: Before Insert
- Action: Rename attachments based on the related record type and name

**Trigger_Name: PreventRestrictedFileTypes**
- Scenario: Prevent Uploading Attachments With Certain File Types (e.g., EXE, ZIP, BAT)
- Use Case: To ensure security, block attachments with potentially malicious file types like .exe, .zip, .bat, etc.
- Triggering Object:  Attachment
- Event: Before Insert
- Action: Restrict file uploads with certain extensions

**Trigger_Name: RollupContactCountOnAccount**
- Scenario: Count the Number of Contacts for Each Account
- Use Case: A company wants to track how many Contacts are associated with each Account, even though Accounts and Contacts have a Lookup relationship instead of - Master-Detail.
- Triggering Object:  Contact
- Event: After Insert, After Update, After Delete, After Undelete
- Action: Whenever a Contact is created, updated, or deleted, update the Contact_Count__c field on the related Account

**Trigger_Name: RollupOpportunityRevenueOnAccount**
- Scenario: Sum Total Revenue from Opportunities to Account
- Use Case: The company wants to track Total Revenue (Total_Revenue__c) on an Account by summing the Amount of all its Opportunities
- Triggering Object:  Opportunity
- Event: After Insert, After Update, After Delete, After Undelete 
- Action: Whenever an Opportunity is created, updated, or deleted, update the Total Revenue on the related Account

**Trigger_Name: RollupLatestTaskDateOnOpportunity**
- Scenario: Calculate the Latest Task Completion Date on Opportunity
- Use Case: A sales team wants to track the Latest Task Completion Date (Latest_Task_Date__c) on an Opportunity based on the most recently completed Task
- Triggering Object:  Task
- Event: After Insert, After Update, After Delete
- Action: Whenever a Task is completed for an Opportunity, update the Latest Task Completion Date on the related Opportunity

**Trigger_Name: RollupTotalDiscountOnQuote**
- Scenario: Calculate the Total Discount Applied on Quotes
- Use Case: The finance team wants to track the Total Discount Applied (Total_Discount__c) on a Quote by summing the Discount__c field from all Quote Line Items
- Triggering Object:  QuoteLineItem
- Event: After Insert, After Update, After Delete, After Undelete
- Action: Whenever a QuoteLineItem is created, updated, or deleted, update the Total Discount Applied on the related Quote

**Trigger_Name: AccountInsertNotificationTrigger**
- Scenario: Write a trigger on Account, when an account is inserted, notify the admin
- Use Case: Ensure System Admin gets notified upon Account creation.
- Triggering Object: Account
- Event: After Insert
- Action: Account Insert.

**Trigger_Name: AccountUpdateTrigger**
- Scenario: Update all related Opportunities' Stage to 'Closed Lost' if the Opportunity was created more than 30 days ago and is not 'Closed Won'.
- Use Case: When an Account is updated, check its related Opportunities and update their stage accordingly.
- Triggering Object: Account
- Event: after update
- Action: Update Opportunity stages.

**Trigger_Name: AccountInsertEmailTrigger**
- Scenario: When a new Account is inserted, an email notification is sent to all System Admin users.
- Use Case: Ensure System Admin gets notified upon Account creation.
- Triggering Object: Account
- Event: after insert
- Action: Account Insert.

**Trigger_Name: AccountUpdateTotalOpportunityAmountTrigger**
- Scenario: Update Account’s 'Total Opportunity Amount' field with the sum of all related Opportunities' Amount when the Account is updated.
- Use Case: Ensure the Account reflects the total revenue from all its Opportunities.
- Triggering Object: Account
- Event: after update
- Action: Calculate and update 'Total Opportunity Amount'.

**Trigger_Name: AccountCreateClientContactTrigger**
- Scenario: When an Account is inserted, create a Contact with the Account Name and update the Account’s 'Client Contact' lookup field.
- Use Case: Automatically assign a default Client Contact to newly created Accounts.
- Triggering Object: Account
- Event: after insert
- Action: Create a Contact and link it to the Account.

**Trigger_Name: OpportunityLineItemSerialNoTrigger**
- Scenario: Assign an incremented Serial Number to each Opportunity Line Item, even if previous records are deleted.
- Use Case: Ensure a unique and sequential serial number is assigned to Opportunity Line Items for tracking.
- Triggering Object: OpportunityLineItem
- Event: before insert
- Action: Assign incremented Serial No.

**Trigger_Name: RestrictTaskDeletionTrigger**
- Scenario: Restrict task deletion to only System Administrators.
- Use Case: Prevent unauthorized task deletions by non-admin users.
- Triggering Object: Task
- Event: before delete
- Action: Check user profile and restrict deletion if the user is not a System Administrator.

**Trigger_Name: SendPDFToLeadTrigger**
- Scenario: Send an email with an attached PDF when a Lead is created.
- Use Case: Automatically send a welcome email with an informational PDF to new leads.
- Triggering Object: Lead
- Event: after insert
- Action: Fetch the pre-uploaded PDF from Documents and email it to the new Lead.

**Trigger_Name: SendEmailToNewContactTrigger**
- Scenario: Send an email to a Contact when inserted using a predefined email template.
- Use Case: Automatically send a welcome email to every new Contact.
- Triggering Object: Contact
- Event: after insert
- Action: Fetch the email template and send an email to the new Contact.

**Trigger_Name: SendEmailToClientContactTrigger**
- Scenario: Send an email to the Opportunity's Account Client Contact when an Opportunity Line Item is created.
- Use Case: Automatically notify the Client Contact when a new product is added to an Opportunity.
- Triggering Object: OpportunityLineItem
- Event: after insert
- Action: Fetch the email template and send an email to the Client Contact.

**Trigger_Name: AutoAddOpportunityLineItemTrigger**
- Scenario: Automatically add a default Opportunity Line Item when an Opportunity is created.
- Use Case: Ensure every new Opportunity has at least one product assigned.
- Triggering Object: Opportunity
- Event: after insert
- Action: Fetch a product from the standard price book and create an Opportunity Line Item.


**Trigger_Name: SendEmailOnAccountTypeChangeTrigger**
- Scenario: When an Account's Type changes, notify all associated Contacts via email.
- Use Case: Ensure that Contacts are informed when their associated Account undergoes a Type change.
- Triggering Object: Account
- Event: after update
- Action: Fetch all Contact and send email

**Trigger_Name: DeleteOpportunityOnLineItemDeleteTrigger**
- Scenario: When an Opportunity Line Item is deleted, its related Opportunity should also be deleted.
- Use Case: Ensure that an Opportunity is removed if it no longer has any associated products.
- Triggering Object: OpportunityLineItem
- Event: after delete
- Action: Collect all related Opportunity IDs and delete the corresponding Opportunities.

**Trigger_Name: CreateQuoteOnOpportunityLineItemInsertTrigger**
- Scenario: When an Opportunity Line Item is created, a related Quote should be automatically inserted.
- Use Case: Ensure that a Quote is generated whenever a new Opportunity Line Item is added.
- Triggering Object: OpportunityLineItem
- Event: after insert
- Action: Create a Quote linked to the same Opportunity as the inserted Opportunity Line Item.

**Trigger_Name: UpdateContactMailingCityOnAccountBillingCityChangeTrigger**
- Scenario: When an Account's BillingCity is updated, update all related Contacts' MailingCity with the new BillingCity.
- Use Case: Ensure that a Contact's MailingCity stays in sync with the associated Account's BillingCity.
- Triggering Object: Account
- Event: after update
- Action: Identify updated Accounts, check if BillingCity has changed, fetch related Contacts, and update their MailingCity.

**Trigger_Name: SyncMultiSelectPicklistOnOpportunityTrigger**
- Scenario: When an Opportunity's Multi-select Picklist is updated, update the same field on the related Account.
- Use Case: Ensure that the Multi-select Picklist values remain in sync between Opportunity and Account.
- Triggering Object: Opportunity
- Event: after update
- Action: Identify updated Opportunities, check if Multi-select Picklist has changed, fetch related Accounts, and update their Multi-select Picklist field.

**Trigger_Name: UpdateAccountClientContactTrigger**
- Scenario: When the Client Contact field on an Opportunity is updated, update the Client Contact field on the related Account.
- Use Case: Ensure that Client Contact information remains consistent between Opportunity and Account.
- Triggering Object: Opportunity
- Event: after update
- Action: Identify updated Opportunities, check if the Client Contact field has changed, fetch related Accounts, and update their Client Contact field.

**Trigger_Name: CreateAssetOnOpportunityLineItemTrigger**
- Scenario: When an OpportunityLineItem is created, an Asset should be automatically created for the opportunity
- Use Case: When an OpportunityLineItem is created, an Asset should be automatically created for the newly created opportunity
- Triggering Object: Opportunity
- Event: after insert
- Action: Create Asset once opportunity is created

**Trigger_Name: UpdateTotalOpportunityAmountOnContactUpdate**
- Scenario: When a Contact is updated, retrieve the total Opportunity Amount for its Account and update the field "Total Opportunity Amount" on the Account.
- Use Case: Maintain real-time updates of Opportunity revenue linked to an Account whenever related Contacts are modified.
- Triggering Object: Contact
- Event: after update
- Action: Fetch Opportunities related to the updated Contact’s Account, sum up their amounts, and update the Account’s Total Opportunity Amount.

**Trigger_Name: NotifyManagerOnUserUpdate**
- Scenario: When a User is updated, send an email to their Manager listing the total Accounts they own and the number of Contacts in each Account.
- Use Case: Ensure Managers are informed about their team’s Account assignments and related Contacts in real-time.
- Triggering Object: User
- Event: after update
- Action: Retrieve Accounts owned by the updated User, count related Contacts, and send an email to the User’s Manager.

**Trigger_Name: ValidateProductFamilyOnLineItem**
- Scenario: Validate that the Opportunity Product Type matches the Opportunity Line Item Product Family.
- Use Case: Prevent mismatched product selections in Opportunities.
- Triggering Object: OpportunityLineItem
- Events: before insert, before update
- Action: Compare Opportunity.Product_Type__c with Product2.Family, and restrict mismatches with an error.

**Trigger_Name: UpdateProductQuantityOnLineItem**
- Scenario: Deduct Opportunity Line Item quantities from the Product2 available stock.
- Use Case: Ensure real-time stock updates when products are added/removed from Opportunities.
- Triggering Object: OpportunityLineItem
- Events: after insert, after update, after delete, after undelete
- Action: Recalculate and update Available_Quantity__c on Product2 based on total quantities in Opportunity Line Items.


