
# 💻 Laptop Request Catalog Item

This repository contains all documentation and configuration details for the **Laptop Request Catalog Item** project implementation.

---

## 📅 Important Dates

**NOTE:** All dates referenced within the project documents reflect the time of this GitHub repository's final submission for faculty evaluation.

---

## 👥 Team Details

**Team ID:** NM2025TMID04313  
**Team Size:** 4  
**Team Leader:** Lekha Shree B  
**Team Members:**  
- Aarthi B
- Harini S
- Nandhini A  

---

## 📘 Project Overview

This initiative focuses on deploying a **dynamic Service Catalog Item** within the **ServiceNow** platform. The core goal is to **modernize and automate** the existing, time-consuming manual workflow for requesting work laptops within an organization. The resulting solution provides a **fast, guided digital experience**, significantly improving data accuracy and establishing a robust governance structure for deployment.

This solution was developed through the **SmartInternz NME program** in collaboration with **ServiceNow** and **SmartBridge**.

---

## 🎯 Problem Statement

Employees require an efficient, rapid process for securing essential work equipment. The existing manual procedure frequently led to **delays, confusion, and inaccurate data capture** because it lacked dynamic form behavior and clear user guidance.

The objective was to create a Catalog Item that provides:
1.  **Unified Digital Intake:** A single, centralized point for all submission requests.
2.  **Guided User Experience:** Dynamic field changes and contextual instructions to simplify the user journey.
3.  **Enhanced Usability:** Inclusion of a form reset capability to improve the overall user experience (UX).
4.  **Configuration Integrity:** Ensuring all changes are meticulously recorded for secure deployment and robust governance.

---

## 🛠️ Implementation Steps

The following steps detail the required configuration sequence to successfully deploy this automated solution within a ServiceNow instance:

### Step 1: Governance Setup
* A **Local Update Set** named **"Laptop Request"** was created and activated to systematically track all configuration changes.

### Step 2: Service Catalog Item Creation
* The primary catalog item, **Laptop Request**, was created.
* It was correctly organized under the **Service Catalog** and the **Hardware** category.

### Step 3: Variables Definition

The following variables were defined to capture request data:

| Variable Name | Type | Technical Name |
| :--- | :--- | :--- |
| Laptop Model | Single Line Text | `laptop_model` |
| Justification | Multi Line Text | `justification` |
| Additional Accessories | Checkbox | `additional_accessories` |
| Accessories Details | Multi Line Text | `accessories_details` |

### Step 4: Dynamic Behavior Implementation
* A **Catalog UI Policy** (*Show Accessories Details*) was implemented to control field visibility.
* **Condition:** The `accessories_details` field is displayed when `additional_accessories` is set to `true`.
* **Action:** The policy ensures that `accessories_details` is set to **Visible: True** and is **Mandatory: True** under this condition.

### Step 5: User Experience Action
* A **Client UI Action** titled **"Reset Form"** was created to enhance UX.
* **Table:** Configured on the `sc_cart` table.
* **Script:** Utilizes the `g_form.clearForm()` function to clear all fields, preceded by an alert for user confirmation.

### Step 6: Deployment & Migration
* The Update Set was completed (**Marked Complete**) and then **Exported to XML**.
* The exported XML was subsequently Imported, Previewed, and **Committed** in the target production or test environment.

---

## 🔐 Instance Access & Security

For platform compliance and security reasons, the **ServiceNow instance link is not publicly available** in this repository.

This practice adheres to the ServiceNow Developer Program Terms of Use, which state:
> “Developer instances are intended for personal use and learning. Sharing access or exposing instance links publicly may result in suspension or termination of access.”

To ensure responsible usage and protection of the intellectual property, instance access remains private.

For the working demonstration, please refer to the **SmartInternz project workspace** and locate the **DEMO LINK** section. The verified ServiceNow instance link is provided there for evaluator access.
