---
title: "Where To Deploy Web Applications"
date: 2022-10-30T13:00:38+01:00
tags:
  - Infrastructure
draft: false
---

For my part, I quickly get confused with all those choices on where to deploy an app. I've heard a lot about Vercel (lambda), Container as a Service, Kubernetes, ... and want to clarify on when to use what.

![Web App Complexity](./complexity.png)

## Hosting a Website

Options include:

- Github Pages
- Netlify
- Vercel
- Render.com
- Cloudflare
- AWS / GCP

## Hosting a Database

Hosting a database can be even more scary than picking a provider for your website & containers.

Easy:

- Railway

Medium:

- Planetscale
- Supabase
- MongoDB Atlas

Advanced:

- AWS
- GCP

## But When To Use Kubernetes?!

Container services often only expose a bare minimum set of configuration. This allows developers to quickly get started, but is unusable once you require more advanced configuration, such as:

- Networking with Service Mesh
- Storage
- Advanced Scaling

Small teams quickly think about the need for a Kubernetes cluster, but it only slows them down. Instead they should focus on market fit & the actual product.

### Fully Managed Kubernetes

GCP was the first cloud vendor to release its Autopilot function to truly manage your Kubernetes cluster. AWS also offers a similar service to attach Fargate to your cluster. But Fargate only manages pre-defined namespaces, not your whole cluster.

### Cloud Kuberentes Providers
