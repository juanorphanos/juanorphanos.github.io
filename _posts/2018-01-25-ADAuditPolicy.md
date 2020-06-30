---
layout: post
title: Domain Controllers Audit Policy Best Practices
---

In our daily job as PFEs one of the most common questions we are asked in the Active Directory field, is what is the recommended Audit Policy to have in our Domain Controllers.


As always we recommend first going to docs.microsoft.com to find the documented recommendations and best practices for our products.

## Question 1: Audit Policy vs Advanced Audit Policy, which one to use?

Audit Policies come with Windows since Windows 2000 times. These are the original nine categories that can be used for every Windows version. Beginning in Windows Vista/2008, we introduced the Advanced Audit Policy categories, to enhance the granularity of the events being recorded.

We can find these settings in these sections:

 - 'Legacy' Audit Policy: Computer Configuration\Windows Settings\Security Settings\Local Policies\Audit Policy
 - Advanced Audit Policy: Computer Configuration\Windows Settings\Security Settings\Advanced Audit Policy Configuration

We don't recommend using both categories at the same time, since it might lead to unexpected resultant settings being applied. As a best practice we recommend to enable this setting: Audit: Force audit policy subcategory settings (Windows Vista or later) to override audit policy category settings policy setting under Local Policies\Security Options.

> Best Practice #1: Always use the Advanced Audit Policy settings instead of legacy settings

> Best Practice #2: Always use the **Audit: Force audit policy subcategory settings (Windows Vista or later) to override audit policy category settings** policy setting

## Question 2: Too many categories to choose from, don't know what to select

A detailed process on what event categories
