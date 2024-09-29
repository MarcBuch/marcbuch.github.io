---
title: "Where To Deploy Web Applications"
date: 2024-09-29T13:00:38+01:00
tags:
  - Infrastructure
draft: false
---

# The Task of Making Infrastructure Easier for Developers

I was hired at a large corporation with the goal to make infrastructure easier for developers. Unlike major software companies, this company had your typical IT department, with a bunch of helpdesk, networking and server guys. Luckily the development teams were allowed to use cloud services to quickly deploy applications autonomously. Most of these applications were rather simple web applications. However, this autonomy led to a concerning outcome: many backend applications and databases were exposed to the public Internet. Only secured by authentication.

While this autonomy did shorten the time required to deploy new environments for applications, it still took several weeks to set up development, QA and production environments, and to release the first production version.

## The Limits of IaC and Shift Left: Why Misconfigurations Persist

Development teams frequently utilize Infrastructure as Code tools to define their cloud environments. However, these tools often fall short in fully addressing the complexities of infrastructure configuration. Even if we adopt the _Shift Left_ approach, allowing developers to define infrastructure through IaC, the result frequently remains the same - misconfigured environments. The only difference lies in the method of execution, not the outcome.

It could be argued that providing a curated set of modules or templates with sensible defaults might solve this issue. However, much like in-house SDKs and shared libraries, these modules and templates still demand comprehensive documentation to ensure proper usage. In my experience, unless public access to cloud resources is strictly disabled, developers often find ways to introduce misconfigurations for the sake of convenience. This is particularly true when dealing with more complex tasks, such as integrating cloud resources into private networks, which increases the level of complexity.

To address these challenges, companies often hire Cloud or DevOps engineers and embed them with the development teams, tasking them with the continuous configuration and management of infrastructure.

## Offering a better way

Looking at how software companies address this challenge, there are valuable practices we can adopt. For instance, Slack utilizes an internal compute platform called _Bedrock_, which enables developers to define their applications using a single YAML file. The application then gets rolled out to shared [[Kubernetes]] clusters managed by the infrastructure team. This approach offers several advantages: it seamlessly integrates applications into the infrastructure defined by the infrastructure team, while preserving the agility of autonomous deployments by development teams.
