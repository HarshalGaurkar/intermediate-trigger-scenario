# intermediate-trigger-scenario
This repository will be having intermediate trigger scenario which can we used in salesforce for business need

**Trigger_1: SyncIndustryToParentAccount**
- Scenario: Update Parent Account Industry Based on Child Account
- Use Case: A business want to populate the child account industry to the parent account.
- Triggering Object: Account
- Event: After Insert, After Update
- Action: Sync Industry of child accounts with the parent account.

**Trigger_2: CreateTaskOnLeadConversion**
- Scenario: Create a Follow-up Task When Lead is Converted
- Use Case: A business whant to take a follow up by creating the task when lead is converted
- Triggering Object: Lead
- Event: after update
- Action: Create a follow-up task when the Lead is converted

**Trigger_3: CalculateBirthdate**
- Scenario: Auto-Populate Contact Birthdate Based on Custom Age Field
- Use Case: A business whant to capture the birthdate of the applicant when user enter the age on record or update on record.
- Triggering Object: Contact
- Event: before insert, before update
- Action: Calculate Birthdate from Age__c.

**Trigger_4: UpdateAccountBirthday**
- Scenario: Auto-Populate Contact Birthdays to Account Level
- Use Case: If a Contact's birthday is updated, update the Earliest Birthday field on the Account.
- Triggering Object: Contact
- Event: After Insert, After Update, After Delete
- Action: Update the earliest birthday on the Account when a related Contact's birthday changes.

**Trigger_5: UpdateAccountIndustry**
- Scenario: Auto-Update Account Industry Based on Most Common Contact Title
- Use Case: If most Contacts in an Account have a similar job title (e.g., Engineers), update the Industry field accordingly.
- Triggering Object: Contact 
- Event: After Insert, After Update, After Delete
- Action: Set the Account Industry based on Contact job titles.

**Trigger_6: ReopenCaseOnCustomerResponse**
- Scenario: Automatically Reopen a Case if the Customer Responds After Closure
- Use Case: If a customer replies to a closed case (by adding a new comment), the case should be reopened to ensure the support team addresses their concerns.
- Triggering Object:  CaseComment
- Event: After Insert
- Action: If a new CaseComment is added to a Closed Case, update the Case Status to "Reopened."

**Trigger_7: AutoTagFileBasedOnRecordType**
- Scenario: Auto-Tag Files Based on Record Type
- Use Case: When a user uploads a file (ContentDocumentLink) related to an Opportunity, Case, or Account, the file should be automatically tagged based on the record type for easier organization.
- Triggering Object:  ContentDocumentLink
- Event: After Insert
- Action: 
    - If the file is uploaded to an Opportunity, tag it as "Sales Document"
    - If uploaded to a Case, tag it as "Support Document"
    - If uploaded to an Account, tag it as "Customer Document"
 
**Trigger_8: StandardizeAttachmentName**
- Scenario: Rename Attachments to Follow a Standard Naming Convention
- Use Case: All uploaded attachments should follow a standard naming format:
- RecordType_RecordName_Timestamp.pdf
- Triggering Object:  Attachment
- Event: Before Insert
- Action: Rename attachments based on the related record type and name

**Trigger_9: PreventRestrictedFileTypes**
- Scenario: Prevent Uploading Attachments With Certain File Types (e.g., EXE, ZIP, BAT)
- Use Case: To ensure security, block attachments with potentially malicious file types like .exe, .zip, .bat, etc.
- Triggering Object:  Attachment
- Event: Before Insert
- Action: Restrict file uploads with certain extensions

**Trigger_10: RollupContactCountOnAccount**
- Scenario: Count the Number of Contacts for Each Account
- Use Case: A company wants to track how many Contacts are associated with each Account, even though Accounts and Contacts have a Lookup relationship instead of - Master-Detail.
- Triggering Object:  Contact
- Event: After Insert, After Update, After Delete, After Undelete
- Action: Whenever a Contact is created, updated, or deleted, update the Contact_Count__c field on the related Account

**Trigger_11: RollupOpportunityRevenueOnAccount**
- Scenario: Sum Total Revenue from Opportunities to Account
- Use Case: The company wants to track Total Revenue (Total_Revenue__c) on an Account by summing the Amount of all its Opportunities
- Triggering Object:  Opportunity
- Event: After Insert, After Update, After Delete, After Undelete 
- Action: Whenever an Opportunity is created, updated, or deleted, update the Total Revenue on the related Account

**Trigger_12: RollupLatestTaskDateOnOpportunity**
- Scenario: Calculate the Latest Task Completion Date on Opportunity
- Use Case: A sales team wants to track the Latest Task Completion Date (Latest_Task_Date__c) on an Opportunity based on the most recently completed Task
- Triggering Object:  Task
- Event: After Insert, After Update, After Delete
- Action: Whenever a Task is completed for an Opportunity, update the Latest Task Completion Date on the related Opportunity

**Trigger_13:RollupTotalDiscountOnQuote**
- Scenario: Calculate the Total Discount Applied on Quotes
- Use Case: The finance team wants to track the Total Discount Applied (Total_Discount__c) on a Quote by summing the Discount__c field from all Quote Line Items
- Triggering Object:  QuoteLineItem
- Event: After Insert, After Update, After Delete, After Undelete
- Action: Whenever a QuoteLineItem is created, updated, or deleted, update the Total Discount Applied on the related Quote

