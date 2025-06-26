# Salesforce-Slack-Integration
This project integrates Salesforce with Slack to send real-time alerts whenever:

- A new Case is **created**
- An existing Case's **Priority** is updated to **"High"**

Slack messages include case details and a direct link to the record in Salesforce.

---

## 📌 Features

- Apex trigger-based Slack alerts
- Slack Incoming Webhook integration
- Asynchronous Queueable Apex callout
- Custom object logging: `Slack_Message_Log__c`
- Captures success/failure status of each notification

---

## ⚙ Technologies Used

- Salesforce Apex (Trigger + Queueable Class)
- Slack Webhooks API
- Remote Site Settings
- Custom Object & Fields
- JSON formatting (Slack Blocks)
- Future-proof structure for enterprise workflows

---

## 🔑 Slack App & Webhook Setup

1. Go to: [https://api.slack.com/apps](https://api.slack.com/apps)
2. Create a new app → From Scratch  
   - **App Name:** `Salesforce Case Alerts`  
   - **Workspace:** `Flacrev`
3. Under **Features**, enable **Incoming Webhooks**
4. Click **Add New Webhook to Workspace**
5. Choose your target channel
6. Copy the generated Webhook URL:

https://hooks.slack.com/services/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
## 🧾 Salesforce Custom Object

### Slack_Message_Log__c

| Field Label       | API Name            | Data Type       |
|-------------------|---------------------|------------------|
| Case              | Case__c             | Lookup (Case)    |
| Message Sent      | Message_Sent__c     | Long Text Area   |
| Status            | Status__c           | Picklist         |
| Timestamp         | Timestamp__c        | DateTime         |

---
## 🧯 Common Errors & Fixes

| Error                              | Fix                                                                 |
|------------------------------------|----------------------------------------------------------------------|
|Unauthorized                             |Check if webhook URL is correct and authorized|
|Alert not received                       |Check your profile has API access|
|Alert did not receive on case creation   |Update trigger to receive alerts on both update and create|
