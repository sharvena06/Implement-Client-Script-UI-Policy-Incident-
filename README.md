# Implement-Client-Script-UI-Policy-Incident-
Implementation of Client Scripts and UI Policies on the ServiceNow Incident form to improve user experience, enforce field behavior, and reduce incorrect data entry. The implementation dynamically controls form fields based on user actions and incident conditions without requiring the form to be submitted.

# ServiceNow Incident – Client Scripts & UI Policies

## Project Overview

This project demonstrates the implementation of **Client Scripts and UI Policies** in the ServiceNow **Incident Management** module.

The configuration is designed to control Incident form behavior, validate important fields, automate field values, and prevent incorrect updates.

## Objectives

* Implement UI Policies for the Incident table.
* Dynamically control field behavior based on Incident conditions.
* Automatically set Urgency for High Impact Incidents.
* Ensure Assigned To is provided before saving High Impact Incidents.
* Prevent State changes through list editing.
* Test and verify the implemented configurations.

## Features Implemented

### 1. High Impact Control – UI Policy

A UI Policy named **High Impact Control** was created for the Incident table.

**Condition:** Impact is High

When the Impact is set to High, the configured UI Policy Actions are applied. The **Reverse if false** option is enabled so that the changes are reverted when the condition is no longer satisfied.

### 2. Urgency Field Control

A UI Policy Action was configured for the **Urgency** field.

When Impact is High, the Urgency field becomes **read-only**, preventing users from manually changing it.

### 3. Automatic Urgency Update

An **onChange Client Script** was created for the Impact field.

When Impact is changed to High, the script automatically sets **Urgency to High** and displays an informational message to the user.

### 4. Assigned To Validation

An **onSubmit Client Script** was implemented to validate the **Assigned To** field.

For High Impact Incidents, the record cannot be saved when Assigned To is empty. An error message is displayed and the user is required to provide an Assigned To value.

### 5. State Change Restriction

An **onCellEdit Client Script** was implemented for the **State** field.

When a user attempts to change the Incident State directly from the list view, the update is blocked and the user is instructed to open the Incident record.

## Testing

The implemented configurations were tested using the following scenarios:

* High Impact Incident field behavior
* Automatic Urgency update
* Assigned To mandatory validation
* Successful Incident save
* UI Policy reverse condition
* State list-edit blocking
* Form-based Incident update

All configured behaviors were verified successfully in the ServiceNow instance.

## Technologies Used

* ServiceNow
* Incident Management
* Client Scripts
* UI Policies
* UI Policy Actions
* JavaScript
* GitHub

## Screenshots

Screenshots of the ServiceNow configuration and testing results are included in this repository as project evidence.

## Conclusion

The project successfully demonstrates the use of **ServiceNow Client Scripts and UI Policies** to improve Incident form behavior, enforce validation rules, automate field updates, and prevent incorrect data entry.

