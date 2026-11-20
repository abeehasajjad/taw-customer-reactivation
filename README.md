# AI-Powered Customer Reactivation Campaign

An automated customer reactivation workflow designed to help gyms and salons reconnect with inactive customers through personalized email outreach.

## Project Overview

Businesses often lose touch with customers who have not visited for several weeks. Manually identifying these customers and writing follow-up messages takes time and can lead to missed opportunities.

This project automates the reactivation process using a simulated CRM in Google Sheets, Make.com, Google Gemini, and Gmail.

The workflow identifies eligible inactive customers, generates personalized reactivation emails, sends test emails, and updates customer records.

## Objectives

- Identify inactive customers who meet the reactivation criteria.
- Respect customer consent before sending outreach.
- Generate personalized messages using AI.
- Automate email delivery.
- Update CRM records after successful email sending.

## Technology Stack

| Tool | Purpose |
|---|---|
| Google Sheets | Simulated CRM and customer database |
| Make.com | Workflow automation |
| Google Gemini 2.5 Flash | Personalized email generation |
| Gmail | Email delivery and testing |

**Note:** Google Sheets is used as a simulated CRM instead of a live GoHighLevel integration.

## Workflow Architecture

1. **Google Sheets CRM:** Stores customer details, consent, activity status, campaign status, and last visit date.
2. **Eligibility Logic:** Identifies customers who meet all campaign conditions.
3. **Make.com:** Searches for customer records marked as `Ready`.
4. **Google Gemini:** Generates a personalized reactivation email.
5. **Gmail:** Sends the generated email to the configured test recipient.
6. **Google Sheets:** Updates the customer record with the generated message, campaign status, and last-contacted date.

## Customer Eligibility Rules

A customer is eligible when all of the following conditions are met:

- Consent is `TRUE`.
- Customer status is `Inactive`.
- Campaign status is `Pending`.
- Last visit was more than 60 days ago but less than 90 days ago.

The Google Sheets `Process` column automatically identifies eligible records as `Ready`. Other records are marked `Not Ready`.

## AI Email Generation

Google Gemini 2.5 Flash generates personalized reactivation email content using customer information, including:

- Customer's first name
- Business type (Gym or Salon)
- Last visit date
- Available offer

The prompt instructs the AI to use a warm, friendly, and natural tone, avoid guilt-based messaging, and not invent discounts, services, or promises.

## CRM Data Structure

The Google Sheets CRM includes the following fields:

| Column | Field |
|---|---|
| A | contact_id |
| B | first_name |
| C | email |
| D | phone |
| E | business_type |
| F | last_visit_date |
| G | consent |
| H | customer_status |
| I | campaign_status |
| J | offer |
| K | generated_message |
| L | reply_category |
| M | last_contacted |
| N | Process |

## Testing and Validation

The workflow was tested using 22 simulated customer records.

Testing covered:

- Eligible and ineligible customer identification.
- Exclusion of customers without consent.
- Exclusion of active customers.
- Exclusion of customers outside the 60–90 day inactivity window.
- AI-generated personalized email content.
- Gmail test email delivery.
- CRM record updates after processing.

The test dataset included both gym and salon customers.

## Project Limitations

- GoHighLevel was not connected; Google Sheets was used as a simulated CRM.
- Gmail was used for test email delivery rather than a live customer email campaign.
- The project uses sample customer data, not real business customer records.
- A production deployment would require connecting the actual CRM, configuring email delivery, and validating consent and campaign safeguards.

## Key Learning Outcomes

- Designing multi-step automation workflows in Make.com.
- Connecting Google Sheets, AI models, and Gmail.
- Applying business rules to customer data.
- Using AI for personalized customer communication.
- Updating CRM records through automated workflows.
- Testing and validating automation scenarios.

## Project Information

**Project:** P2 – Customer Reactivation Campaign  
**Internship:** Think AI Works – AI Automation Engineer Internship  
**Status:** Implemented and tested  
**Developer:** Abeeha Sajjad

## Demo and Project Files

- **Loom Demo:** To be added.
- **Make.com Workflow Export (JSON):** added.
- **Screenshots:** added.


