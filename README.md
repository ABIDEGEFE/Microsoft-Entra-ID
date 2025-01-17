# SkillB Azure Cloud Migration Documentation

This documentation outlines the steps and strategies for migrating SkillB's infrastructure to **Azure Cloud**. The document is written from the perspective of a **cloud engineer** managing **Microsoft Entra ID** and related Azure services for SkillB, an organization with two branches: one in **London** and another in **New York**.

### Key Features and Services Covered:

- **Entra ID Tenant**
- **Custom Domain Name Configuration**
- **Entra ID Domain Services**
- **Enterprise Applications**
- **Administrative Units**

## Table of Contents

1. [Entra ID Tenant](#entra-id-tenant)
2. [Customize Domain Name](#customize-domain-name)
3. [Entra ID Domain Services](#entra-id-domain-services)
4. [Enterprise Applications](#enterprise-applications)
5. [Administrative Units](#administrative-units)

---

## Entra ID Tenant

SkillB has two branches in London and New York. To manage users and groups in these two branches, I decided to create two separate **Entra ID tenants**:

- **London_tenant** (Default)
- **New-York_tenant**

### Steps to Create an Additional Tenant:

1. Navigate to **Microsoft Entra ID** > **Manage Tenant IDs** > **Create**.
2. Select the tenant type:
   - **Microsoft Entra ID** (for licensed customers)
   - **Azure AD B2C** (for customer-facing applications)
3. Fill in all necessary fields during configuration (tenant name, domain name, subscription).
4. Click **Review + Create** to finalize the tenant setup.

---

## Customize Domain Name

Customizing the domain name (changing from the default *onmicrosoft.com*) is crucial for SkillB to maintain a unique brand identity and provide distinct accounts for users.

### Steps to Customize the Domain Name:

1. Register the custom domain with an official domain name registrar.
2. Navigate to **Microsoft Entra ID** > **Custom Domain Names** > **Add Custom Domain**.
3. Enter the custom domain name (e.g., `SkillB.com`).
4. Copy the Microsoft verification code and add it as a DNS record at the registrar.
5. Once verified, users' accounts will use the new domain format: `username@SkillB.com`.

---

## Entra ID Domain Services

Entra ID Domain Services enable legacy applications relying on traditional Active Directory (AD) features to function in the cloud. This service allows SkillB to keep using existing applications that require AD-like features.

### Steps to Configure Entra ID Domain Services:

1. Navigate to **entra.microsoft.com**.
2. Search for **"Domain Services"** and select **Microsoft Entra Domain Services**.
3. Click **Create**.
4. Configure the settings, including selecting the virtual network.
5. Click **Review + Create** to complete the deployment.

---

## Enterprise Applications

The **Enterprise Application** feature in **Microsoft Entra ID** enables SkillB to manage SaaS applications. Through this feature, SkillB can assign users, groups, and devices to applications while also customizing and configuring integrations and identity behaviors.

### Steps to Create an Enterprise Application:

1. Navigate to **Microsoft Entra ID** > **Enterprise Applications** > **New Application**.
2. Browse the application gallery and select the desired application.
3. Add users, groups, and devices for access to the selected application.

---

## Administrative Units

To manage SkillB's software developers who are working on a full-stack e-commerce website for another organization, I used **Administrative Units** to organize and assign resources based on their roles.

### Steps to Create an Administrative Unit:

1. Navigate to **Microsoft Entra ID** > **Administrative Units** > **Add**.
2. Enter the name of the administrative unit (e.g., `Front_End_e-commerce`).
3. Assign roles and permissions at the administrative unit level.
4. Click **Review + Create** to complete the process.

---

## Final Notes

This documentation demonstrates how **Microsoft Entra ID** and related Azure services can support SkillB's migration to Azure Cloud by organizing and managing resources across regions, domains, and applications. By using tenants, domain services, enterprise applications, and administrative units, SkillB achieves an organized and secure cloud infrastructure.

## NOTE THAT SKILLB IS NOT EXISTED COMPANY, IT IS JUST FOR PRACTICAL UNDERSTANDING OF ENTRA ID TENANT

-
