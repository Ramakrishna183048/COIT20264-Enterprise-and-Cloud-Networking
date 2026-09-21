# Week 4 – Azure Cost Management

## Overview

In this week's activity, I worked with Azure Cost Management in the Azure portal. I learned how to view cost information for a resource group, create a customized cost view, and create a monthly budget with a forecast alert.

The main activities I completed were:

- Viewed the Azure subscription used for the lab.
- Changed the Cost Analysis scope to the `AZ900RG` resource group.
- Reviewed the Cost Analysis page.
- Created a customized Daily costs view.
- Created a monthly budget for the resource group.
- Configured a forecasted cost alert at 80% of the budget.
- Added an email address to receive budget alerts.

---

## Task 1 – Review the Azure Subscription

I opened the **Subscriptions** page in the Azure portal and selected the subscription provided for the lab.

The subscription used during the activity was:

`Challenge Lab--lod53203202`

From the subscription page, I could view information such as the subscription ID, status, role and current cost.

### Evidence

![Azure Subscription](images/week4-task1-sub-page.png)

*Figure 1: Azure subscription used for the Cost Management activity.*

---

## Task 1.2 – Review Cost Analysis

I opened **Cost Management > Cost analysis** and changed the scope to the `AZ900RG` resource group.

This allowed me to review cost information specifically for the resources inside this resource group instead of looking at the whole subscription.

The **AccumulatedCosts** view was available on the Cost Analysis page.

Because this was a temporary lab environment, there was no meaningful accumulated cost data available.

### Evidence

![Accumulated Costs](images/Accumilated_costs.png)

*Figure 2: Cost Analysis page for the AZ900RG resource group.*

---

## Task 1.3 – Create a Daily Costs View

From the Cost Analysis page, I added a new customizable view and selected **Daily costs**.

I saved the view with the name:

`Daily costs view`

The new view appeared as a separate tab next to the AccumulatedCosts view.

The lab verification also confirmed that the Daily costs view was created successfully for the `AZ900RG` resource group.

### Evidence

![Daily Costs View](images/week4-task1-daily-cost.png)

*Figure 3: Daily costs view successfully created for the AZ900RG resource group.*

---

## Task 1.4 – Create a Monthly Budget

I then used the **Budgets** option in Azure Cost Management to create a budget for the `AZ900RG` resource group.

The budget was configured with the following settings:

| Setting | Value |
|---|---|
| Budget name | `My_RG_monthly_budget` |
| Scope | `AZ900RG` |
| Reset period | Monthly |
| Budget amount | `$20,000 USD` |
| Alert type | Forecasted cost |
| Alert threshold | `80%` |
| Alert amount | `$16,000` |

The monthly reset period means Azure evaluates the budget again for each monthly period.

### Evidence

![Create Azure Budget](images/create_budget_AZOORG.png)

*Figure 4: Configuration of the monthly budget for the AZ900RG resource group.*

---

## Task 1.5 – Configure the Budget Alert

For the budget alert, I selected **Forecasted cost** and configured the alert threshold to:

`80%`

Since the total monthly budget was `$20,000`, the 80% alert represented:

`$16,000`

I also added an email address as the alert recipient.

This means an alert can be sent when Azure forecasts that the configured budget threshold will be reached.

### Evidence

![Monthly Budget](images/MY-RG-monthly-budget.png)

*Figure 5: My_RG_monthly_budget showing the monthly budget and 80% forecasted cost alert.*

---

## What I Learned

This activity helped me understand how Azure Cost Management can be used to monitor cloud spending.

I learned that the scope can be changed so that costs can be viewed for a particular resource group. I also learned how customizable views can make it easier to check costs in different ways, such as viewing daily costs.

Creating the budget helped me understand that a budget does not stop resources from running when the amount is reached. Instead, it can be used to monitor spending and provide alerts when configured thresholds are reached.

The forecast alert was also useful because it can provide a warning based on expected spending before the full budget amount is reached.

---

## Problems Faced and How I Solved Them

While creating the budget, I initially had a problem when adding the alert recipient email address. Azure showed an error saying that an alert threshold percentage was required.

At first, it looked like there was a problem with the email address, but the actual issue was that the alert condition had not been fully configured.

I went back to the alert conditions and selected **Forecasted cost** with an **80%** threshold. After completing the alert condition, I was able to add the email recipient and save the budget successfully.

This helped me understand that Azure validates the complete alert configuration before allowing the budget to be created.

---

## Reflection

This week's activity gave me a better understanding of how costs can be monitored and controlled in Azure.

Before doing this activity, I mainly focused on creating and configuring Azure resources. This lab showed me that managing the cost of those resources is also an important part of cloud management.

I found the Daily costs view useful because it provides a simple way to monitor how costs change over time. The budget and forecast alert also showed me how an administrator can keep track of spending and receive an early warning when costs are expected to reach a certain level.  

Overall, this activity helped me understand the basic Azure tools available for cost monitoring, budgeting and cost alerts.
