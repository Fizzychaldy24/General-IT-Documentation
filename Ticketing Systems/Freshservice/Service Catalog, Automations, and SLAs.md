[General IT Documentation](/README.md) 
# Service Catalog, Automations, and SLAs

## Table of Contents
- [Overview](#overview)
- [Service Catalog Management](#service-catalog-management)
  - [Configuring Service Catalog](#configuring-service-catalog)
  - [Managing Service Items](#managing-service-items)
- [Automations and Workflow Rules](#automations-and-workflow-rules)
  - [Creating Automations](#creating-automations)
  - [Workflow Rules](#workflow-rules)
- [SLA Management](#sla-management)
  - [Defining SLAs](#defining-slas)
  - [Enforcing SLAs](#enforcing-slas)
- [Summary](#summary)

---

## Overview

This section provides detailed instructions on how to configure **service catalogs**, set up **automations** for task management, and define and enforce **Service Level Agreements (SLAs)** in **Freshservice**. These features are critical for managing customer requests and ensuring timely resolutions.

---

## Service Catalog Management

### Configuring Service Catalog

The **service catalog** in Freshservice is a self-service portal where users can request IT services and support. To configure a service catalog:

1. Go to the **Admin** section and select **Service Catalog**.
2. Click **Add New Service** to create a new catalog item.
3. Provide the following details for the service:
   - **Service Name**: A descriptive title for the service (e.g., "Laptop Repair").
   - **Category**: Choose a category for the service (e.g., Hardware, Software, IT Support).
   - **Description**: Provide a detailed description of the service.
   - **Request Fulfillment Time**: Set the expected time to fulfill the request.

You can also define custom fields that will be required for users to fill out when requesting the service.

### Managing Service Items

Once a service is created, you can:
- **Edit** the service details as needed.
- **Enable** or **Disable** services based on availability.
- **Organize services** into categories for easier navigation.

Services in the catalog can be linked to specific workflows, SLAs, and ticket types to ensure that they are processed efficiently.

---

## Automations and Workflow Rules

### Creating Automations

**Automations** in Freshservice can help streamline repetitive tasks such as assigning tickets, sending notifications, or escalating issues. To create an automation:

1. Go to the **Admin** section and click **Automations** under the **Helpdesk Productivity** section.
2. Choose from available automation types:
   - **Ticket Creation Automation**: Automatically assign tickets based on criteria like issue type or priority.
   - **Ticket Updates**: Trigger notifications or actions when a ticket is updated or resolved.
   - **Time-Based Actions**: Set rules for ticket escalation after a certain time period.

When creating an automation rule, you can specify the conditions (e.g., when a ticket is created by a certain user) and the actions (e.g., assign to a specific team or send an email notification).

### Workflow Rules

**Workflow Rules** define how tickets move through different stages of the support process. To set up workflow rules:

1. Go to **Admin** > **Workflow Automator**.
2. Create a new rule by selecting a **Trigger** (e.g., ticket creation, status change) and **Actions** (e.g., notify agent, assign ticket).
3. Configure the **Conditions** that must be met for the rule to execute.

Workflow rules help automate processes like ticket routing, approvals, and escalations, ensuring consistent and timely support.

---

## SLA Management

### Defining SLAs

**Service Level Agreements (SLAs)** define the expected response and resolution times for tickets based on their priority and type. To define SLAs:

1. Go to **Admin** > **SLA Policies**.
2. Click **Add SLA Policy** to create a new policy.
3. Provide details such as:
   - **SLA Name**: A descriptive title for the SLA policy (e.g., "High Priority SLA").
   - **Response Time**: Define the maximum response time for each priority level.
   - **Resolution Time**: Define the maximum time to resolve tickets.
   - **Business Hours**: Specify the business hours during which the SLA is applicable.

SLAs can be tied to different ticket priorities (e.g., High, Medium, Low) and can be applied to specific ticket categories or service items.

### Enforcing SLAs

Once SLAs are defined, they will be automatically enforced by Freshservice. The system will track SLA performance based on the conditions set in the SLA policy:
- **SLA Breaches**: Freshservice will notify agents if an SLA breach is imminent or has occurred.
- **Escalations**: If an SLA is about to breach, tickets can be escalated to higher-level agents or teams.
- **Alerts**: Both agents and customers can receive reminders of SLA status through notifications.

You can track SLA performance on **dashboards** and generate **reports** to measure team efficiency and identify bottlenecks.

---

## Summary

This section covered the following key aspects:
- **Service Catalog Management**: How to configure, manage, and organize service catalogs for user requests.
- **Automations and Workflow Rules**: How to set up automations to streamline tasks and configure workflows to ensure tickets are processed efficiently.
- **SLA Management**: How to define and enforce SLAs to ensure timely responses and resolutions to tickets.

By leveraging these features, Freshservice enables your team to automate processes, maintain high service standards, and meet customer expectations efficiently.
