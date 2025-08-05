# HR Onboarding Automation

Integrated **ServiceNow HR Service Delivery (HRSD)** with **Workday** and **Azure Active Directory** to fully automate employee onboarding and offboarding workflows across **three regions**. This solution eliminates manual HR and IT steps, accelerates provisioning, improves CMDB accuracy, and expands ITOM Discovery capabilities for hybrid and cloud environments.

---

## 📌 Overview

The **HR Onboarding Automation** project streamlines the complete employee lifecycle — from Day‑0 onboarding to secure offboarding — by connecting HR, IT, and identity systems.

Key initiatives delivered:

* **Onboarding/Offboarding Automation** – Integrated HRSD, Workday, and Azure AD to trigger and manage workflows automatically.
* **CMDB Optimization Project** – Redesigned CMDB structure, applied normalization rules, and improved data completeness from **45% → 90%** in 6 months.
* **ITOM Discovery Expansion** – Customized MID Server probes to improve asset coverage and accuracy across AWS and hybrid infrastructure.

---

## # Prerequisites

* ServiceNow instance with:

  * HR Service Delivery (HRSD)
  * IT Operations Management (ITOM)
  * IntegrationHub
* Workday tenant with API access
* Azure Active Directory with Microsoft Graph API permissions
* At least one configured ServiceNow MID Server
* Administrator access to ServiceNow
* Access to CMDB normalization and reconciliation rules

---

## # Deployment Guide

This document provides **step‑by‑step** instructions for deploying the HR Onboarding Automation solution. The high‑level setup has three major phases:

1. **ServiceNow HRSD & Integration Setup**
2. **CMDB Optimization**
3. **ITOM Discovery Expansion**

---

## Step 1: ServiceNow HRSD & Integration Setup

This phase connects Workday and Azure AD to ServiceNow HRSD to enable automated onboarding and offboarding workflows.

### Step 1.1: Ensure License & Plugin Availability

Ensure your ServiceNow instance has:

* HR Service Delivery
* IntegrationHub ETL or Spokes for Workday and Azure AD
* Flow Designer enabled

### Step 1.2: Configure Workday Integration

1. In ServiceNow, navigate to **IntegrationHub → Spokes → Workday**.
2. Configure Workday API credentials:

   * **Tenant** – Your Workday tenant name.
   * **Username / Password** – Workday integration account.
   * **WSDL URL** – Workday SOAP endpoint.
3. Test connection to confirm ServiceNow can pull employee hire/termination events.

### Step 1.3: Configure Azure AD Integration

1. In ServiceNow, open **IntegrationHub → Spokes → Azure AD**.
2. Provide Microsoft Graph API credentials from your Azure AD app registration.
3. Grant required permissions for:

   * User create/update/delete
   * Group membership management
4. Test connection.

### Step 1.4: Create Onboarding & Offboarding Flows

1. Use **Flow Designer** to create two main flows:

   * **Onboarding Flow** – Triggered when Workday sends a new hire event.
   * **Offboarding Flow** – Triggered when Workday sends a termination event.
   Dashboard:C:\Users\Talha Rafique\OneDrive\Desktop\Projects\Jayemalik\agent-for-hr-service-solution-accelerator-main\Deployment\Images\architecture.png
2. Actions in the Onboarding Flow:

   * Create HR case in HRSD
   * Provision Azure AD account
   * Assign groups/licenses
   * Generate welcome email
3. Actions in the Offboarding Flow:

   * Disable Azure AD account
   * Remove group memberships
   * Reclaim assets
   * Close HR case

---

## Step 2: CMDB Optimization Project

### Step 2.1: Assess Current CMDB State

* Review **CMDB Health Dashboard** for completeness, correctness, and compliance.
* Identify duplicate or unclassified CIs.

### Step 2.2: Implement Normalization & Reconciliation

1. Enable **CMDB Identification and Reconciliation** engine.
2. Configure **Normalization Data Services (NDS)** to standardize vendor and product names.
3. Apply reconciliation rules to prevent data overwrites from unauthorized sources.

### Step 2.3: Validate Improvement

* Run CMDB Health reports.
* Verify improvement from **45% to 90% completeness** over the optimization period.

---

## Step 3: ITOM Discovery Expansion

### Step 3.1: Prepare MID Servers

* Ensure MID Servers have network reach to AWS, VMware, and on‑prem systems.
* Update MID Server configurations for proxy or authentication requirements.

### Step 3.2: Customize Probes

* Modify existing **AWS Cloud Discovery** patterns to capture additional metadata.
* Enhance **on‑prem probes** for more accurate OS and software inventory.

### Step 3.3: Run Discovery & Validate

* Schedule Discovery for hybrid environments.
* Validate new CIs appear in CMDB with correct relationships and attributes.

---

## Results Achieved

* **Reduced onboarding cycle time** from days to hours.
* **90%+ CMDB data completeness** within 6 months.
* **Expanded AWS & hybrid discovery coverage** with higher probe accuracy.
* **Improved compliance** with regional labor and security requirements.
* **Seamless identity lifecycle management** with Workday → HRSD → Azure AD automation.

---

## Roadmap

* Extend onboarding to contractors and third‑party vendors.
* Integrate Microsoft Teams for onboarding communications.
* Add predictive SLA analytics for onboarding tasks.
